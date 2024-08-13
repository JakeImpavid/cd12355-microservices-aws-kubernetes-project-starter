# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set environment variables
ENV APP_HOME /usr/src/app
ENV DB_USERNAME=your_username
ENV DB_PASSWORD=your_password
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5432
ENV DB_NAME=postgres
ENV APP_PORT=5153

# Set the working directory in the container
WORKDIR $APP_HOME

# Update the local package index and install required packages
RUN apt-get update -y && \
    apt-get install -y build-essential libpq-dev

# Copy the current directory contents into the container at $APP_HOME
COPY . .

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port available to the world outside this container
EXPOSE 5153

# Define environment variable
ENV NAME World

# Run the application
CMD ["python", "app.py"]
