# Mermaid ERD Diagram

You can render entity-relationship diagrams in markdown using Mermaid.  It works in both Visual Studio Code and GitHub.

---

The following code renders the diagram below it:

``````
``` mermaid
erDiagram
    User ||--o{ Task : plans
    User {
        int user_id PK
        string name
        string email
        string first_name
        string last_name
    }
    Task }|--|| Category : member
    Task {
        int task_id PK
        string title
        string description
        int user_id FK
        int category_id FK
    }
    Category {
        int category_id PK
        string name
    }
```
``````

---

``` mermaid
erDiagram
    User ||--o{ Booking : plans
    User {
        int user_id PK
        string name
        string email
        string first_name
        string last_name
    }
    Booking {
        int booking_id PK
        string date
        string time
        int guest_count
        string status
    }
```

---

The most obscure bit is the relationship syntax.  I copied this table from [the Mermaid docs](https://mermaid.ai/open-source/syntax/entityRelationshipDiagram.html).

|Value (left)|Value (right)|Meaning|
|:-:|:-:|---|
|\|o|o\||Zero or one|
|\|\||\|\||Exactly one|
|}o|o{|Zero or more (no upper limit)|
|}\||\|{|One or more (no upper limit)|
