# 0.6: New Note in SPA Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Enter note and click Save
    Browser->>Server: POST /new_note with note data (AJAX)
    activate Server
    Server-->>Browser: JSON response with success status
    deactivate Server
    Browser->>Browser: Update note list dynamically without reloading
    Browser->>Server: GET /data.json (Optional: Refresh data)
    Server-->>Browser: Updated JSON with new note
    Browser->>Browser: Re-render notes list if data was refreshed
