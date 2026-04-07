sequenceDiagram
    participant browser
    participant server

    Note right of browser: User submits a new note; JavaScript intercepts the submission

    Note right of browser: JavaScript immediately updates the notes list on the page

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: Server saves the new note and responds with 201 Created
    server-->>browser: 201 Created
    deactivate server