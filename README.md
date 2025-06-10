# Album RESTful API

A simple RESTful API built with Go and Gin framework for managing a collection of music albums.

## Features

- List all albums
- Get album by ID
- Add new albums
- JSON response format
- Input validation

## Prerequisites

- Go 1.16 or higher
- Gin web framework

## Installation

1. Clone the repository:
```bash
git clone <your-repository-url>
cd web-service-gin
```

2. Install dependencies:
```bash
go mod tidy
```

## Running the API

Start the server by running:
```bash
go run main.go
```

The server will start on `localhost:8080`

## API Endpoints

### Get All Albums
- **URL:** `/albums`
- **Method:** `GET`
- **Success Response:**
  - **Code:** 200
  - **Content Example:**
```json
[
    {
        "id": "1",
        "title": "Blue Train",
        "artist": "John Coltrane",
        "price": 56.99
    },
    {
        "id": "2",
        "title": "Jeru",
        "artist": "Gerry Mulligan",
        "price": 17.99
    }
]
```

### Get Album by ID
- **URL:** `/albums/:id`
- **Method:** `GET`
- **URL Params:** `id=[string]`
- **Success Response:**
  - **Code:** 200
  - **Content Example:**
```json
{
    "id": "1",
    "title": "Blue Train",
    "artist": "John Coltrane",
    "price": 56.99
}
```
- **Error Response:**
  - **Code:** 404
  - **Content:** `{"message": "album not found"}`

### Add New Album
- **URL:** `/albums`
- **Method:** `POST`
- **Data Params:**
```json
{
    "id": "4",
    "title": "The Modern Sound",
    "artist": "Miles Davis",
    "price": 29.99
}
```
- **Success Response:**
  - **Code:** 201
  - **Content:** Returns the created album

## Example Usage

### Get All Albums
```bash
curl http://localhost:8080/albums
```

### Get Album by ID
```bash
curl http://localhost:8080/albums/1
```

### Add New Album
```bash
curl -X POST -H "Content-Type: application/json" -d "{\"id\":\"4\",\"title\":\"The Modern Sound\",\"artist\":\"Miles Davis\",\"price\":29.99}" http://localhost:8080/albums
```

## Project Structure

```
web-service-gin/
├── main.go         # Main application file
├── go.mod          # Go module file
├── go.sum          # Go module checksum
└── README.md       # Documentation
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
