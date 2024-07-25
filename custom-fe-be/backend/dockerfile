# Use the official Python image from the Docker Hub.
FROM python:3.8

# Set the working directory.
WORKDIR /usr/src/app

# Copy the requirements file into the image.
COPY requirements.txt ./

# Install the dependencies.
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code.
COPY . .

# Command to run the application.
CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app"]
