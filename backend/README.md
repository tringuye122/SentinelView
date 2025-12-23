# SentinelView Backend

Go-based backend API for the SentinelView security camera platform.

## Features

- RESTful API for camera feed management
- Token-based authentication (JWT)
- AI event detection and processing
- Real-time event streaming
- Secure API proxy for camera feeds

## Prerequisites

- Go 1.21 or higher
- Git

## Setup

1. Copy the environment template:
   ```bash
   cp .env.example .env
   ```

2. Edit `.env` and configure your environment variables:
   - Set `JWT_SECRET` to a strong random string
   - Configure `CAMERA_API_KEY` if using third-party camera APIs
   - Set database connection string if using a database

3. Install dependencies:
   ```bash
   go mod download
   ```

4. Run the server:
   ```bash
   go run main.go
   ```

   Or build and run:
   ```bash
   go build -o sentinelview-backend
   ./sentinelview-backend
   ```

## Environment Variables

See `.env.example` for all available configuration options.

## API Endpoints

### Authentication
- `POST /api/v1/auth/login` - Authenticate and receive JWT token
- `POST /api/v1/auth/refresh` - Refresh JWT token

### Cameras
- `GET /api/v1/cameras` - List all cameras
- `GET /api/v1/cameras/:id` - Get camera details
- `GET /api/v1/cameras/:id/snapshot` - Get current camera snapshot

### Events
- `GET /api/v1/events` - List events (with filters)
- `GET /api/v1/events/:id` - Get event details
- `GET /api/v1/events/stream` - Stream events (WebSocket)

## Project Structure

```
backend/
├── cmd/
│   └── server/
│       └── main.go          # Application entry point
├── internal/
│   ├── api/                 # HTTP handlers
│   ├── auth/                # Authentication logic
│   ├── camera/              # Camera service
│   ├── event/               # Event processing
│   └── config/              # Configuration management
├── pkg/                     # Shared packages
├── .env.example             # Environment template
├── go.mod                   # Go module file
└── README.md                # This file
```

## Development

Run tests:
```bash
go test ./...
```

Run with hot reload (requires [air](https://github.com/cosmtrek/air)):
```bash
air
```

## License

MIT License - see LICENSE file in the root directory.

