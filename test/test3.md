# 複雑な Mermaid 図テスト

## シーケンス図

```mermaid
sequenceDiagram
    participant Client
    participant Server
    participant Database
    participant Cache

    Client->>Server: HTTP GET /api/data
    activate Server
    Server->>Cache: HGET user:123
    Cache-->>Server: data (hit)
    Server->>Client: 200 OK
    deactivate Server
```

## クラス図

```mermaid
classDiagram
    class Animal {
        +String name
        +eat()
        +sleep()
    }

    class Bird {
        +fly()
        +layEggs()
    }

    class Fish {
        +swim()
        +gills()
    }

    Animal <|-- Bird
    Animal <|-- Fish
```

## 状態図

```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

## エラーハンドリングの例

```mermaid
flowchart TD
    A[Start] --> B{Check Error?}
    B -->|Yes| C[Log Error]
    C --> D[Show Message]
    D --> E[Return Null]
    B -->|No| F[Process Data]
    F --> G{Success?}
    G -->|Yes| H[Return Result]
    G -->|No| C
```

## ganttチャート（beautiful-mermaid非対応）

```mermaid
gantt
    title Project Development
    dateFormat  YYYY-MM-DD
    section Section
    Task 1           :a1, 2024-01-01, 30d
    Task 2           :after a1  , 20d
    section Another
    Task 3           :2024-01-12  , 12d
    Task 4           : 24d
```

## テキスト本文

これは mermaid 図の間に挟まれた通常のテキストです。

- ポイント1
- ポイント2
- ポイント3

`インラインコード` も含められます。

**太字** と *斜体* も問題ありません。

## flowchart LR のテスト

```mermaid
flowchart LR
    A[Starting Point] --> B{Decision}
    B -->|Yes| C[Action 1]
    B -->|No| D[Action 2]
    C --> E[End]
    D --> E
```

```mermaid
flowchart LR
    DB[(Database)] --> Auth[Authentication]
    Auth --> API[API Server]
    API --> Cache[(Redis)]
    API --> DB
    Cache --> API
```
