```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    server-->>browser: HTML page
    deactivate server

    browser->>server: GET /main.css
    activate server
    server-->>browser: CSS
    deactivate server

    browser->>server: GET /main.js
    activate server
    server-->>browser: JavaScript
    deactivate server

    Note right of browser: JS executes and fetches notes data

    browser->>server: GET /data.json
    activate server
    server-->>browser: notes in JSON format
    deactivate server

    Note right of browser: JS renders notes without full reload
