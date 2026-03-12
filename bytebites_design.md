# ByteBites Revised Class Design

This UML-style class diagram reflects the four required backend classes and their core relationships.

```mermaid
classDiagram
    direction LR

    class Customer {
        +name: String
        +purchase_history: List~Transaction~
        +is_real_flag: bool
    }

    class FoodItem {
        +name: String
        +price: float
        +category: String
        +popularity_rating: float
    }

    class Menu {
        +items: List~FoodItem~
        +filter_by_category(category: String): List~FoodItem~
    }

    class Transaction {
        +selected_items: List~FoodItem~
        +total_cost: float
        +compute_total(): float
    }

    Customer "1" --> "0..*" Transaction : stores
    Menu "1" o-- "0..*" FoodItem : contains
    Transaction "1" o-- "1..*" FoodItem : groups
```

## Relationship Notes

- A `Customer` keeps a purchase history made up of zero or more `Transaction` objects.
- A `Menu` manages a collection of `FoodItem` objects and supports category-based filtering.
- A `Transaction` groups one or more `FoodItem` objects.
- `total_cost` is derived from the prices of the `selected_items` in a transaction.