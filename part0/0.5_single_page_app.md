sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    Note right of server: Server returns the HTML page structure
    server-->> browser: html document
    deactivate server

