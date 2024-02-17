# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy the local directory contents into the container
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Generate Python gRPC code
RUN python -m grpc_tools.protoc -I./proto --python_out=. --grpc_python_out=. ./proto/greeter.proto

# Make port 50051 available to the world outside this container
EXPOSE 50051

# Define environment variable
ENV NAME World

# Run server.py when the container launches
CMD ["python", "server.py"]
