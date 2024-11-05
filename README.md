# Command History API

A simple API that allows users to store and search command history using Quarkus. This API can be used to remember commands typed by users across multiple sessions.

## Features

- Store commands typed by the user.
- Search command history by keyword.

## Technologies Used

- Java 21
- Quarkus
- H2 Database
- Docker
- Docker Compose

## API Documentation

### Store a command
-Endpoint: `POST /api/v1/commands`
-Sample Request : 
```bash
curl -X POST http://localhost:8080/api/v1/commands \
  -H "Content-Type: application/json" \
  -d '{"command":"ls -l"}'
```
- Sample Response :
```json
{
  "Id": "123456",
  "command": "ls -l"
  "timestamp": "2024-11-05"
}
```

### Search for all commands containing a keyword 
- Endpoint : `/api/v1/commands`
- Query Params : `keyword=` 
- Sample Request:
  ```bash
  curl "http://localhost:8080/api/v1/commands?keyword=ls"
  ```
- Sample Response:
  ```json
  [
  {
  "Id": "123456",
  "command": "ls -l"
  "timestamp": "2024-11-05"
   }
  ]
  ```
  ### Search for all commands 
- Endpoint : `/api/v1/commands`
- Sample Request :
  ```bash
  curl http://localhost:8080/api/v1/commands
  ```




## Steps to Use 
- Ensure you have all prereqs installed like Java , Gardle (better to use IntelliJ) , Docker , Docker Compose
- Next Clone the Repository , Navigate to the Project Directory
- Open Docker in background and run the docker-compose command
  ```bash
  docker-compose up --build
  ```
- You should see an image 'safedep-swe' up and running in docker.  
- Test the API endpoints in the terminal using the given sample cURLs
