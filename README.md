# Todo Application

A simple Todo application built with Spring Boot and MongoDB, designed for practicing Jenkins pipelines.

## Features

- Create, read, update, and delete todos
- MongoDB integration for data persistence
- RESTful API endpoints
- Docker support for easy deployment

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/todos | Get all todos |
| GET | /api/todos/{id} | Get a specific todo |
| POST | /api/todos | Create a new todo |
| PUT | /api/todos/{id} | Update a todo |
| DELETE | /api/todos/{id} | Delete a todo |

## Example Requests

### Get all todos
```bash
curl http://localhost:8080/api/todos
```

### Get a specific todo
```bash
curl http://localhost:8080/api/todos/{id}
```

### Create a new todo
```bash
curl -X POST http://localhost:8080/api/todos \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Spring Boot", "description": "Complete the tutorial"}'
```

### Update a todo
```bash
curl -X PUT http://localhost:8080/api/todos/{id} \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Spring Boot", "description": "Tutorial completed", "completed": true}'
```

### Delete a todo
```bash
curl -X DELETE http://localhost:8080/api/todos/{id}
```

## Running the Application

### Using Docker Compose

1. Make sure Docker and Docker Compose are installed
2. Run the following command:
```bash
docker-compose up --build
```

The application will be available at `http://localhost:8080`

## Jenkins Pipeline

The application includes a Jenkins pipeline with the following stages:
- Install Dependencies
- Test
- Lint
- Build
- Docker

To use the pipeline:
1. Create a new Pipeline job in Jenkins
2. Configure it to use the Jenkinsfile from your repository
3. Make sure Jenkins has Docker installed and configured
4. Ensure the Jenkins user has permissions to run Docker commands 