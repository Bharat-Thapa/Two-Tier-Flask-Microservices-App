# Stage 1: Build Stage
FROM python:3.7 AS builder

# Set the working directory
WORKDIR /app

# Copy the application files
COPY . .

# Install the dependencies
RUN pip install -r requirements.txt

# Stage 2: Final Stage
FROM python:3.7-slim

# Set the working directory
WORKDIR /app

# Copy the installed dependencies from the builder stage
COPY --from=builder /app .

# Install the dependencies
RUN pip install -r requirements.txt

# Set environment variables
ENV PORT 5000

# Expose the port the app runs on
EXPOSE 5000

# Define the entrypoint
ENTRYPOINT ["python"]

# Define the default command
CMD ["app.py"]
