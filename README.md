# Back_end_Event-Announcer

# Event Announcer

## Description

Event Announcer is a Django-based backend service providing a RESTful API for managing events, automating CRUD operations, user authentication, and sending automated reminders to participants via background tasks.

---

## Key Features

- **User Authentication**  
  Secure sign-up, login, logout using Django’s built-in auth system.

- **REST API**  
  Full CRUD endpoints for events, participants, and reminders via Django REST Framework.

- **Background Tasks**  
  Automated reminder emails for upcoming events.

---

## Tech Stack & Dependencies

- **Django**  
- **Django REST Framework**  
- **PostgreSQL**  
- **Celery** (optional – for background task processing)  
- **Redis** (optional – as Celery broker)  
- **Docker & Docker Compose**

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/SoheilMehrizi/Back_end_Event-Announcer.git
cd Back_end_Event-Announcer
```


2. Build and run with Docker Compose
bash
Copy
Edit
docker-compose up --build
This will:

Build the Django application image.

Start PostgreSQL.

(If configured) Start Redis & Celery for background tasks.

Run migrations automatically.

Once up, the API will be available at http://localhost:8000/.

## Usage
API Endpoints

Events

* GET /api/events/ — List all events

* POST /api/events/ — Create a new event

* GET /api/events/{id}/ — Retrieve event details

* PUT /api/events/{id}/ — Update an event

* DELETE /api/events/{id}/ — Delete an event

Participants & Reminders

* POST /api/events/{id}/participants/ — Add a participant

Automated reminders will be sent (as decided) hours before each event (configurable).

## Deployment
Event Announcer is Dockerized for easy deployment:

Adjust environment variables in docker-compose.yml (e.g. SECRET_KEY, DATABASE_URL, email credentials).

Run docker-compose up --build -d.

Configure your production domain and reverse proxy (e.g. Nginx → Gunicorn).

