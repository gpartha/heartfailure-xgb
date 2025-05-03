# Create a docker build
docker build -t heart-failure-app .

# Run the docker image
docker run -p 7860:7860 heart-failure-app

# Build your Docker image using the following command.
docker build -t gpartha/heart-failure-app .

