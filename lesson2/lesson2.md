```mermaid
erDiagram

  reservations {
    int id PK
    datetime requested_at
    string contact_required
    string contact_phone_number
    string title_notification_allowed
    int user_id FK
    int book_id FK
    int contact_method_id FK
    int location_id FK
    int discovery_method_id FK
    datetime created_at
    datetime updated_at
  }

  users {
    int id PK
    int card_number
    string name
    string name_kana
    datetime created_at
    datetime updated_at
  }

  books {
    int id PK
    string name
    string author_name
    int publisher_id FK
    datetime publication_year
    int price
    datetime created_at
    datetime updated_at
  }

  publishers {
    int id PK
    string name
    datetime created_at
    datetime updated_at
  }

  contact_methods {
    int id PK
    string name
    datetime created_at
    datetime updated_at
  }

  locations {
    int id PK
    string name
    datetime created_at
    datetime updated_at
  }


  discovery_methods {
    int id PK
    string name
    datetime created_at
    datetime updated_at
  }

  users ||--o{ reservations : makes
  books ||--o{ reservations : reserved_by
  publishers ||--o{ books : publishes
  contact_methods ||--o{ reservations : used_by
  locations ||--o{ reservations : selected_for
  discovery_methods ||--o{ reservations : referenced_by
```
