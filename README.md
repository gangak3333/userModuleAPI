# User Module API

A lightweight Go-based API for handling basic user flows such as login, registration, and profile creation. The project is built with the Gin web framework and uses in-memory data structures for demo-style request handling.

## Features

- User login flow with email/password validation
- User registration flow with query parameter input
- User profile creation flow with profile details
- Built-in demo users for quick local testing
- Simple Gin-based routing and JSON responses

## Tech Stack

| Technology | Purpose |
| --- | --- |
| Golang | Backend runtime and application logic |
| Gin | HTTP routing and middleware |
| Go Modules | Dependency management |

## Project Structure

```text
.
├── main.go
├── go.mod
├── src/
│   └── user/
│       ├── login/
│       ├── profile/
│       ├── registration/
│       ├── profileDb/
│       ├── userLocalDb/
│       └── userRegistrationDb/
```

## Setup Instructions

### Prerequisites

- Go 1.18 or newer

### Install dependencies

```bash
go mod tidy
```

### Run the server

```bash
go run main.go
```

The server will start on port 8080 by default.

## API Endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | /login | Handles login requests with JSON body input |
| GET | /registration | Handles registration requests using query parameters |
| GET | /profile | Handles profile creation requests using query parameters |

## Example Requests

### Login

```bash
curl -X GET "http://localhost:8080/login" \
  -H "Content-Type: application/json" \
  -d '{"email":"User_1@gmail.com","password":"Passwd_1"}'
```

### Registration

```bash
curl "http://localhost:8080/registration?username=demo&email=User_1@gmail.com&password=Passwd_1&phone=1234567890&fullname=Demo%20User&gender=male&dob=1990-01-01"
```

### Profile

```bash
curl "http://localhost:8080/profile?name=Demo%20User&email=User_1@gmail.com&phone=1234567890&gender=male&dob=1990-01-01&about=Hello&profilePhoto=photo.jpg&address=Somewhere&location=Earth"
```

## Notes

This project is designed as a demo API and uses predefined sample users for testing purposes.
