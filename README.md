# fullstackopen_part0

Exercise 4: Adding notes (`https://studies.cs.helsinki.fi/exampleapp/notes`)
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server -->> browser: HTML document
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server -->> browser: CSS file
    deactivate server 

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server -->> browser: JS file
    deactivate server 

    Note right of browser: the browser starts executing the JavaScript code that
    fetches data.json using AJAX after the page load;

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server -->> browser: data.json file
    deactivate server  

    Note right of browser: the browser starts rendering all notes on the page

    browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server -->> browser: 302 Redirect to /notes
    deactivate server  

    Note right of browser: browser follows redirect and reloads the page to fetch 
    updated notes

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server -->> browser: HTML document
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server -->> browser: CSS file
    deactivate server 

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server -->> browser: JS file
    deactivate server 

    Note right of browser: the browser starts executing the JavaScript code that
    fetches data.json using AJAX after loading the page

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server -->> browser: data.json file
    deactivate server  

    Note right of browser: the browser starts rendering all notes (including the note that has
    been submitted via form) on the page
```

Exercise 5: Opening website `https://studies.cs.helsinki.fi/exampleapp/spa`
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server -->> browser: HTML document
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server -->> browser: CSS file
    deactivate server 

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server -->> browser: JS file
    deactivate server 

    Note right of browser: the browser starts executing the JavaScript code that
    fetches data.json using AJAX after loading the page

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server -->> browser: data.json file
    deactivate server  

    Note right of browser: the browser executes the callback function that 
    renders the notes
```

Exercise 6: Adding notes (`https://studies.cs.helsinki.fi/exampleapp/spa`)
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server -->> browser: HTML document
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server -->> browser: CSS file
    deactivate server 

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server -->> browser: JS file
    deactivate server 

    Note right of browser: the browser starts executing the JavaScript code that
    fetches data.json using AJAX after loading the page

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server -->> browser: data.json file
    deactivate server  

    Note right of browser: the browser executes the callback function that 
    renders the notes

    Note right of browser: adding a new note requires submitting it via form on the page 
    preventing its default behaviour after which browser executes code that makes POST 
    request to the server

    browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa (JSON note data)
    activate server
    server -->> browser: 201 Created (JSON Confirmation)
    deactivate server

    Note right of browser: JavaScript updates local notes list and re-renders UI without
    reloading the page
```
