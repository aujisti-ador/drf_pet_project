# Django Project with Docker

This project is a Django application set up with Docker, Poetry for dependency management, and Gunicorn as the WSGI server. The project also includes MySQL and Redis services configured via Docker Compose.

## Table of Contents

- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Making Code Changes](#making-code-changes)
- [Database Migrations](#database-migrations)
- [Stopping the Containers](#stopping-the-containers)
- [Troubleshooting](#troubleshooting)

## Installation

### Prerequisites

Ensure you have the following installed on your machine:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Poetry](https://python-poetry.org/docs/#installation)

### Clone the Repository

```bash
git clone https://github.com/yourusername/your-repository.git
cd your-repository

Build and Start Containers
Navigate to the container folder:

bash
Copy code
cd container
Build and start the Docker containers:

bash
Copy code
docker-compose up --build
This command builds the Docker images and starts the containers for your Django application, MySQL database, and Redis server.

Running the Application
Once the containers are up and running, the Django application will be accessible at http://localhost:8000.

Making Code Changes
To make changes to your code:

Edit files in the source/main directory.
The changes will be reflected immediately in the running container due to the Docker volume mount.
Database Migrations
If you need to apply database migrations, run the following command:

bash
Copy code
docker-compose run web poetry run python manage.py migrate
Stopping the Containers
To stop the running containers, use:

bash
Copy code
docker-compose down