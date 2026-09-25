# Event Management API

A simple RESTful API built with Flask for managing events. Supports creating, updating, and deleting events using an in-memory data store.

## Routes

### Create an Event
`POST /events`

**Request body:**
```json
{ "title": "Hackathon" }
```

**Response (201 Created):**
```json
{ "id": 3, "title": "Hackathon" }
```

### Update an Event
`PATCH /events/<id>`

**Request body:**
```json
{ "title": "Hackathon 2025" }
```

**Response (200 OK):**
```json
{ "id": 3, "title": "Hackathon 2025" }
```

**If the event doesn't exist (404 Not Found):**
```json
{ "error": "Event with id 3 not found" }
```

### Delete an Event
`DELETE /events/<id>`

**Response (204 No Content)** — empty body on success.

**If the event doesn't exist (404 Not Found):**
```json
{ "error": "Event with id 3 not found" }
```

## Running the App

```bash
pipenv shell
pipenv install
python app.py
```

The server runs at `http://127.0.0.1:5000`.

## Testing

```bash
pytest
```