# Dockerfile
FROM python:3.9-slim


# Set the working directory
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt requirements.txt
RUN pip3 install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

RUN ls

EXPOSE 8000
# Command to run the application
# CMD ["python", "app.py"]
