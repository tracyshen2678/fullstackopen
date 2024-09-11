# 0.5: Single Page App (SPA) Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Navigate to /spa
    Browser->>Server: GET /spa
    activate Server
    Server-->>Browser: HTML document
    deactivate Server
    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Browser->>Server: GET /spa.js
    Server-->>Browser: JavaScript file
    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: JSON with notes data
    deactivate Server
    Browser->>Browser: Render notes using JavaScript

