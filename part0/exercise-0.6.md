```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types a note and clicks Save.
    Note right of browser: Java script prevents default, updates the list locally, and sends the JSON payload to the server.
    
    browser->>server: POST [https://studies.cs.helsinki.fi/exampleapp/new_note_spa]
    activate server
    Note left of server: Server pushes the new note to the notes array.
    server-->>browser: HTTP 201 Created
    deactivate server
    
    Note right of browser: The browser stays on the same page. No further HTTP requests are made.
