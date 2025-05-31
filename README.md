# FastAPI To-Do Items API

This project is a simple FastAPI application for managing a list of to-do items. It demonstrates basic CRUD operations using FastAPI and Pydantic.

## Features
- Add new to-do items
- List all to-do items (with optional limit)
- Retrieve a specific to-do item by its ID

## Endpoints

### `GET /`
Returns a welcome message.

### `POST /items`
Create a new to-do item.
- **Request Body:**
  - `text` (string): The description of the to-do item
  - `is_done` (boolean, optional): Completion status (default: `false`)
- **Response:** List of all items

### `GET /items?limit=10`
List to-do items, with an optional `limit` query parameter (default: 10).

### `GET /items/{item_id}`
Retrieve a specific to-do item by its index in the list.
- Returns 404 if the item does not exist.

## Requirements
- Python 3.7+
- FastAPI
- Uvicorn
- Pydantic

## Setup
1. **Create a virtual environment (recommended):**
   ```zsh
   python3 -m venv venv
   source venv/bin/activate
   ```
2. **Install dependencies:**
   ```zsh
   pip install fastapi uvicorn pydantic
   ```

## Running the App
Start the server with:
```zsh
uvicorn main:app --reload
```

Visit [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) for the interactive API documentation (Swagger UI).

## Notes
- This app uses an in-memory list to store items. Data will be lost when the server restarts.
- For production, consider using a database for persistent storage.
