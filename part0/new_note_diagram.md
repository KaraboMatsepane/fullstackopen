sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note right of server: Server adds the new note to the list of notes
    server-->> browser: 302 Redirect to /notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    Note right of server: Note right of server: Server returns the HTML page structure
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    Note right of server: server retrieves the main.css file
    server-->>browser: main.css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    Note right of server: server retrieves the main.js file
    server-->>browser: main.js file
    deactivate server

    Note right of browser: The browser executes the code in the main.js file. Inside the file, there is a GET request that fetches the JSON of notes from the server.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    Note right of server: server retrieves the list of notes stored in a JSON file
    server-->>browser: JSON data containing notes
    deactivate server

    Note right of browser: the browser executes the callback function that renders the notes.


