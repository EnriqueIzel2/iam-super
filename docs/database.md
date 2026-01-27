erDiagram
USERS ||--o{ SECTORS : "belongs to"
SECTORS ||--o{ SECTOR_PROCESSES : "has"
PROCESSES ||--o{ SECTOR_PROCESSES : "included in"
USERS ||--o{ USERS : "created/updated by"

    USERS {
        uuid id PK
        string name
        string email UK
        string password_hash
        string access_level
        uuid sector_id FK
        timestamp created_at
        timestamp updated_at
        uuid created_by FK
        uuid updated_by FK
    }

    SECTORS {
        uuid id PK
        string name UK
        string description
        timestamp created_at
        timestamp updated_at
    }

    PROCESSES {
        uuid id PK
        string name
        string description
        string url
        timestamp created_at
        timestamp updated_at
    }

    SECTOR_PROCESSES {
        uuid sector_id PK, FK
        uuid process_id PK, FK
    }