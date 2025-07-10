```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types note and clicks Save

    browser->>server: POST /new_note_spa with note content
    activate server
    server-->>browser: 200 OK
    deactivate server

    Note right of browser: JS updates state with new note

    Note right of browser: DOM is updated to show new note without reloading the page
