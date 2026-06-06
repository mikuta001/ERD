```mermaid
erDiagram

    products {
        int id PK
        string product_name
        int price_excluding_tax
        int price_including_tax
        int product_category_id FK
        datetime created_at
        datetime updated_at
    }

    product_categories {
        int id PK
        string product_category_name
        datetime created_at
        datetime updated_at
    }

    orders {
        int id PK
        int order_method_id FK
        int customer_id FK
        datetime order_date_time
        int total_amount
        datetime created_at
        datetime updated_at
    }

    order_details {
        int id PK
        int order_id FK
        int product_id FK
        int order_quantity
        datetime created_at
        datetime updated_at
    }

    customers {
        int id PK
        string full_name
        string phone_number
        datetime created_at
        datetime updated_at
    }

    order_methods {
        int id PK
        string order_method_name
        datetime created_at
        datetime updated_at
    }

    product_categories ||--o{ products : categorizes
    customers ||--o{ orders : places
    order_methods ||--o{ orders : used_by
    orders ||--o{ order_details : includes
    products ||--o{ order_details : references
```
