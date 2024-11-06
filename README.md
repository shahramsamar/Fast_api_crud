# FastAPI CRUD Application

A FastAPI project that implements basic **CRUD (Create, Read, Update, Delete)** operations for managing resources in an API. This project includes simple endpoints for handling resource data with validation, error handling, and data persistence using SQLAlchemy.

## Features

- **Create**: Add new resources to the database.
- **Read**: Retrieve a list of all resources or a single resource by its ID.
- **Update**: Modify existing resources in the database.
- **Delete**: Remove resources from the database.
- **Data Validation**: Ensures proper data formats using Pydantic models.
- **Error Handling**: Handles common HTTP errors and validation issues.
- **Database Integration**: Uses SQLAlchemy for ORM-based interactions with the SQLite database.

## Requirements

- **Python 3.x**
- **FastAPI**: Web framework for building APIs.
- **Uvicorn**: ASGI server for serving the FastAPI app.
- **SQLAlchemy**: ORM for interacting with the database.
- **Pydantic**: Data validation library.
- **SQLite**: The default database used for this project.

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/shahramsamar/Fast_api_crud.git
    cd Fast_api_crud
    ```

2. **Install Dependencies:**

    If you're using `pip`, run:

    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Application:**

    To run the FastAPI app using Uvicorn:

    ```bash
    uvicorn main:app --reload
    ```

    This will start the server at `http://127.0.0.1:8000`.

### How to Use

1. **Create a Resource**:
    - Send a `POST` request to `/items/` with the required data to create a new resource.

    Example request body:
    ```json
    {
        "name": "New Item",
        "description": "A description of the new item."
    }
    ```

2. **Read Resources**:
    - Send a `GET` request to `/items/` to retrieve all resources.
    - Send a `GET` request to `/items/{item_id}/` to retrieve a specific resource by its ID.

3. **Update a Resource**:
    - Send a `PUT` request to `/items/{item_id}/` with the updated data to modify an existing resource.

    Example request body:
    ```json
    {
        "name": "Updated Item",
        "description": "Updated description of the item."
    }
    ```

4. **Delete a Resource**:
    - Send a `DELETE` request to `/items/{item_id}/` to delete the resource by ID.

### Example Endpoints

- **Create Item**: `POST /items/`
- **Get All Items**: `GET /items/`
- **Get Item by ID**: `GET /items/{item_id}/`
- **Update Item**: `PUT /items/{item_id}/`
- **Delete Item**: `DELETE /items/{item_id}/`

### Project Structure

- `main.py`: Contains the FastAPI application, route handlers, and database setup.
- `models.py`: Defines SQLAlchemy ORM models, e.g., `Item`.
- `schemas.py`: Contains Pydantic models for validation and response formatting.
- `database.py`: Configures database connection and session handling.
- `requirements.txt`: Lists the necessary libraries and dependencies for the project.

### API Documentation

FastAPI automatically generates interactive API documentation:

- **Swagger UI**: `http://127.0.0.1:8000/docs`
- **ReDoc**: `http://127.0.0.1:8000/redoc`

### Example Requests

1. **Create Item** (POST):
    ```bash
    curl -X 'POST' \
    'http://127.0.0.1:8000/items/' \
    -H 'Content-Type: application/json' \
    -d '{
        "name": "Sample Item",
        "description": "This is a sample item"
    }'
    ```

2. **Get All Items** (GET):
    ```bash
    curl -X 'GET' 'http://127.0.0.1:8000/items/'
    ```

### Contributing

Feel free to fork the project and submit pull requests for new features, improvements, or bug fixes.

## License

This project is open-source and available for educational purposes.
