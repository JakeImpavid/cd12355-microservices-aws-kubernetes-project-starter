## Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set environment variables for database connection
ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword

# Install system dependencies required for PostgreSQL and Python packages
RUN apt-get update -y && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Upgrade pip, setuptools, and wheel
RUN pip install --upgrade pip setuptools wheel

# Set the working directory in the container
WORKDIR /app

# Copy the local code to the container's workspace
COPY . /app

# Install Python dependencies
RUN pip install -r requirements.txt

# Expose the port the app is running on
EXPOSE 8000

# Command to run the application
CMD ["python", "app.py"]
