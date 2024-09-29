# Use an official Python runtime as a parent image
FROM python:3.13.0rc2-slim

# Set environment variables to ensure the Python output is not buffered
ENV PYTHONUNBUFFERED=1

# Install Poetry
RUN pip install poetry

# Set the working directory to /app
WORKDIR /app

# Copy Poetry files
COPY ../../source/main/pyproject.toml ../../source/main/poetry.lock /app/

# Install dependencies using Poetry
RUN poetry config virtualenvs.create false \
    && poetry install --no-root --no-interaction --no-ansi

# Copy the rest of the application
COPY ../../source/main /app/

# Expose port 8000
EXPOSE 8000

# Run Gunicorn server with 3 workers
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:8000", "config.wsgi:application"]
