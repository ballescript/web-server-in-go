# Web server in go
Made following [Akhil Sharma's tutorial](https://www.youtube.com/watch?v=ASBUp7stqjo)

## Available Endpoints

This Go web server serves the following endpoints:

- **`/`** (GET)
  - **Description**: Serves the `index.html` file as the home page.
  - **Example**: 
    ```
    GET http://localhost:8080/
    ```
  - **Response**: Returns the content of `index.html`

- **`/hello`** (GET)
  - **Description**: Returns a "Hello, World!" message.
  - **Example**: 
    ```
    GET http://localhost:8080/hello
    ```
  - **Response**:
    ```json
    {
      "message": "Hello, World!"
    }
    ```

- **`/form.html`** (GET)
  - **Description**: Serves an HTML form page (`form.html`) where users can input data.
  - **Example**: 
    ```
    GET http://localhost:8080/form.html
    ```
  - **Redirects to**: `/form` when the form is submitted.

- **`/form`** (POST)
  - **Description**: Handles form submissions from `form.html` and processes the input.
  - **Example**: 
    ```
    POST http://localhost:8080/form
    ```
  - **Request Body**:
    ```json
    {
      "name": "John Doe",
      "address": "Right here"
    }
    ```
  - **Response**:
    ```json
    {
      "message": "Form submitted successfully"
    }
    ```

### Static Files
The server serves static files like `index.html` and `form.html` directly when accessed via their paths (`/` for `index.html` and `/form.html` for `form.html`). These files are located in the `static` directory.

