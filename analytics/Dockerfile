# Dockerfile
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Install system dependencies
RUN apt update -y && apt install -y build-essential libpq-dev && rm -rf /var/lib/apt/lists/*

# Copy requirements and install Python dependencies
COPY requirements.txt .
RUN pip install --upgrade pip setuptools wheel
RUN pip install -r requirements.txt

# Copy the rest of the app
COPY . .

# Expose the port used by Flask
EXPOSE 5153

# Command to run the app
CMD ["python", "app.py"]
