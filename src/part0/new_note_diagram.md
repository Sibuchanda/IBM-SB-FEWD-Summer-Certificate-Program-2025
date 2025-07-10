```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: 302 redirect to /notes
    deactivate server

    browser->>server: GET /notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /main.css
    activate server
    server-->>browser: CSS
    deactivate server

    browser->>server: GET /main.js
    activate server
    server-->>browser: JavaScript
    deactivate server

    Note right of browser: JS fetches data.json again

    browser->>server: GET /data.json
    activate server
    server-->>browser: updated notes
    deactivate server

    Note right of browser: New note appears on the page
