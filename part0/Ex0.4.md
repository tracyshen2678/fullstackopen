sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Enter note and click Save
    Browser->>Server: POST /new_note with note data
    activate Server
    Server-->>Browser: 302 Redirect to /notes
    deactivate Server
    Browser->>Server: GET /notes
    activate Server
    Server-->>Browser: HTML document with updated notes list
    deactivate Server
    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript file
    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: JSON with updated notes
    deactivate Server
    Browser->>Browser: Render updated notes list

