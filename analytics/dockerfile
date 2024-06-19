#Python image
FROM python:3.9-slim

# Environment variables
ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

# Install dependencies
RUN apt-get update && apt-get install -y build-essential libpq-dev && rm -rf /var/lib/apt/lists/*


# Working directory
WORKDIR /app

# Python dependencies
COPY requirements.txt .
RUN pip install --upgrade pip setuptools wheel && pip install -r requirements.txt

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 5153
EXPOSE 5153

# Command to run the application
CMD python app.py