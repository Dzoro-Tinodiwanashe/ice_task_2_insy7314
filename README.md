```markdown
# INSY7314 - ICE Task 2

* **Student Name:** Tinodiwanashe Dzoro
* **Student ID:** ST10402234
* **Module Code:** INSY7314
* **Module Name:** Information Systems 3D
* **Resource Entity:** Movies API

Structured Express backend API with modular routes, validation middleware, controlled CORS, and central error handling.

---

## Project Directory Structure

```text
api/
├── controllers/
│   └── movieController.js
├── middleware/
│   ├── errorHandler.js
│   └── validateMovie.js
├── routes/
│   └── movieRoutes.js
├── .env
├── index.js
└── package.json

```

---

## Tested API Endpoints

| Method | Endpoint | Description | Status Code |
| --- | --- | --- | --- |
| `GET` | `http://localhost:4000/` | Root server route | `200 OK` |
| `GET` | `http://localhost:4000/health` | Server health status | `200 OK` |
| `GET` | `http://localhost:4000/api/movies` | Fetch all movies from memory | `200 OK` |
| `GET` | `http://localhost:4000/api/movies/m1` | Fetch single movie by ID | `200 OK` |
| `POST` | `http://localhost:4000/api/movies` | Add new movie item to memory | `201 Created` |

---

## Postman Request Bodies (5 New Items)

Set POST requests to `http://localhost:4000/api/movies`:

### Item 1: Interstellar

```json
{
  "title": "Interstellar",
  "director": "Christopher Nolan",
  "releaseYear": 2014,
  "genre": "Sci-Fi"
}

```

### Item 2: Parasite

```json
{
  "title": "Parasite",
  "director": "Bong Joon-ho",
  "releaseYear": 2019,
  "genre": "Thriller"
}

```

### Item 3: Spirited Away

```json
{
  "title": "Spirited Away",
  "director": "Hayao Miyazaki",
  "releaseYear": 2001,
  "genre": "Animation"
}

```

### Item 4: Pulp Fiction

```json
{
  "title": "Pulp Fiction",
  "director": "Quentin Tarantino",
  "releaseYear": 1994,
  "genre": "Crime"
}

```

### Item 5: The Matrix

```json
{
  "title": "The Matrix",
  "director": "Lana Wachowski",
  "releaseYear": 1999,
  "genre": "Sci-Fi"
}

```

---

## Input Validation Test Cases

Tested against `validateMovie.js` middleware to ensure proper input handling and error responses:

### Test Case 1: Missing Required Field (`director`)

* **Endpoint:** `POST http://localhost:4000/api/movies`
* **Expected Result:** `400 Bad Request`

```json
{
  "title": "Incomplete Movie Record",
  "releaseYear": 2024,
  "genre": "Drama"
}

```

### Test Case 2: Invalid Data Type (`releaseYear` passed as String)

* **Endpoint:** `POST http://localhost:4000/api/movies`
* **Expected Result:** `400 Bad Request`

```json
{
  "title": "Invalid Year Record",
  "director": "Jane Doe",
  "releaseYear": "Two Thousand Twenty Four",
  "genre": "Action"
}





```

```
