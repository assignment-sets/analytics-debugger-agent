# Variables
IMAGE_NAME = node-sample-app:latest
CONTAINER_NAME = node-app

# Default action
all: build run

# Build the image
build:
	docker build -t $(IMAGE_NAME) .

# Run the container
run:
	docker run -d --name $(CONTAINER_NAME) --network host --env-file .env $(IMAGE_NAME)

# Stop and remove the container (crucial for re-running)
stop:
	docker stop $(CONTAINER_NAME) || true
	docker rm $(CONTAINER_NAME) || true

# Rebuild and restart
restart: stop build run