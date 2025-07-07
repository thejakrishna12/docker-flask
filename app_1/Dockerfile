# 1. Use a base image with Python
FROM python:3.10-slim

# 2. Set working directory in container
WORKDIR /app

# 3. Copy requirements.txt and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 4. Copy your app code into the container
COPY . .

# 5. Set the command to run the app
CMD ["python", "app.py"]
