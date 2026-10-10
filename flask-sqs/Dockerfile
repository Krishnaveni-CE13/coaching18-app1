# Using a slim Python base image from Docker Hub
FROM python:3.12-slim

# Prevent Python from writing .pyc files and keep logs unbuffered
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

# Create working directory inside container
WORKDIR /app

# Install dependencies first for better Docker layer caching
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code into working directory inside container
COPY . .

# Expose Flask app port
EXPOSE 5002

# Start Flask app
CMD ["python", "app-sqs.py"]
