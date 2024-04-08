# BasketSplitter Library

The `BasketSplitter` library efficiently divides items in a shopping basket into delivery groups based on predefined delivery methods for each product. Designed to minimize the number of delivery groups and maximize the number of items per group, it offers a practical solution for e-commerce platforms seeking optimized delivery management.

## Features

- **Minimal Grouping**: Algorithmically splits items into the least number of delivery groups.
- **Maximum Capacity**: Ensures the largest group contains as many products as possible.
- **Configurable**: Utilizes a JSON configuration file for flexible delivery methods mapping.

## Requirements

- Java 17 or 21
- Maven for building the project

## Getting Started

### Configuration

1. **JSON Configuration**: Prepare a JSON file containing the delivery methods available for each product. Format as follows:

    ```json
    {
      "Carrots (1kg)": ["Express Delivery", "Click&Collect"],
      "Cold Beer (330ml)": ["Express Delivery"],
      "Steak (300g)": ["Express Delivery", "Click&Collect"]
    }
    ```

2. **Place the JSON Config**: Store the configuration file within the `src/main/resources` directory for easy access or any other accessible directory.

### Building the Library

1. **Clone the Repository**: Clone or download the project source code to your local machine.

2. **Build with Maven**: Navigate to the project root directory and run:

    ```bash
    mvn clean package
    ```

    This will generate a "fat JAR" in the `target` directory, containing all necessary dependencies.

### Using the Library

1. **Instantiate `BasketSplitter`**: Provide the absolute path to the JSON configuration file when creating a `BasketSplitter` instance.

    ```java
    BasketSplitter splitter = new BasketSplitter("/path/to/config.json");
    ```

2. **Split the Basket**: Call the `split` method with a list of item names to divide them into delivery groups.

    ```java
    List<String> items = List.of("Steak (300g)", "Carrots (1kg)");
    Map<String, List<String>> deliveryGroups = splitter.split(items);
    ```

### created with love by playfulCloud