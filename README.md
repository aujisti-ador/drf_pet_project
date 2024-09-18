Here's your content reformatted in a clean and convenient `README.md` format:

```markdown
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
```

### Build and Start Containers

Navigate to the `container` folder:

```bash
cd container
```

Build and start the Docker containers:

```bash
docker-compose up --build
```

This command builds the Docker images and starts the containers for your Django application, MySQL database, and Redis server.

## Running the Application

Once the containers are up and running, the Django application will be accessible at [http://localhost:8000](http://localhost:8000).

## Making Code Changes

To make changes to your code:

1. Edit files in the `source/main` directory.
2. The changes will be reflected immediately in the running container due to the Docker volume mount.

## Database Migrations

If you need to apply database migrations, run the following command:

```bash
docker-compose run web poetry run python manage.py migrate
```

## Stopping the Containers

To stop the running containers, use:

```bash
docker-compose down
```

## Troubleshooting

- **Dependency Issues**: If you encounter issues related to dependencies, ensure that you have the correct Python version specified in your `pyproject.toml`. Update the Dockerfile if necessary.

- **Code Not Reflecting**: Ensure that the volume mount is correctly set up in your `docker-compose.yml` file. If you experience issues, try restarting the Docker containers.

- **Database Connection**: Check the `docker-compose.yml` configuration for database connection settings and ensure that the MySQL service is running.

For further assistance, refer to the [Docker documentation](https://docs.docker.com/) or the [Django documentation](https://docs.djangoproject.com/en/stable/).
```

This `README.md` provides clear and structured instructions for setting up and managing your Django project, making it easy for others (or yourself) to follow.