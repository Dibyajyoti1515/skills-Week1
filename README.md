
---

# To-Do List API (Express.js)

A simple REST API server built with **Express.js** to manage to-do items using in-memory storage. No database is used.

---

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Getting Started](#getting-started)  
- [Usage](#usage)  
- [API Endpoints](#api-endpoints)  
- [Response Format](#response-format)  
- [Error Handling](#error-handling)  
- [License](#license)

---

## Overview

This Node.js and Express-based server allows users to create, view, and delete to-do tasks without using a database. Tasks are stored in an in-memory array and managed with a simple auto-incrementing ID system. It runs on port `3000`.

---

## Features

- Add, view, and delete to-do items via RESTful API
- In-memory storage (no database required)
- Supports `application/json` and `x-www-form-urlencoded`
- Lightweight and easy to test with Postman or curl

---

## Getting Started

### Prerequisites

- Node.js (v14+ recommended)

### Installation

```bash
git clone https://github.com/Dibyajyoti1515/skills-Week1.git
npm install
```

### Start Server

```bash
node index.js
```

The server will run at:  
`http://localhost:3000`

---

## Usage

###  POST `/todos`
- **Request:**
  ```json
  {
    "task": "Complete project"
  }
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "task": "Complete project",
    "completed": false
  }
  ```

###  GET `/todos`
- **Response:**
  ```json
  [
    {
      "id": 1,
      "task": "Complete project",
      "completed": false
    }
  ]
  ```

###  DELETE `/todos/1`
- **Response:** `204 No Content` (Empty body if successful)

---

## API Endpoints

| Method | Endpoint         | Description              |
|--------|------------------|--------------------------|
| GET    | `/todos`         | Get all tasks            |
| POST   | `/todos`         | Add a new task           |
| DELETE | `/todos/:id`     | Delete a task by ID      |

---

## Response Format

```json
{
  "id": 1,
  "task": "Your Task",
  "completed": false
}
```

---

## Error Handling

| Status Code | Message                         |
|-------------|----------------------------------|
| 400         | Missing or invalid task input    |
| 404         | Task not found for deletion      |
| 500         | Internal server error            |

---

## License

MIT License

---
