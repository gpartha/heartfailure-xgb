# Create a docker build
docker build -t heart-failure-app .

# Run the docker image
docker run -p 7860:7860 heart-failure-app

# Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:
aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 922060081647.dkr.ecr.eu-north-1.amazonaws.com

# Build your Docker image using the following command. For information on building a Docker file from scratch, see the instructions here . You can skip this step if your image has already been built:
docker build -t gpartha/heart-failure-app .

# After the build is completed, tag your image so you can push the image to this repository:
docker tag gpartha/heart-failure-app:latest 922060081647.dkr.ecr.eu-north-1.amazonaws.com/gpartha/heart-failure-app:latest

# Run the following command to push this image to your newly created AWS repository:
docker push 922060081647.dkr.ecr.eu-north-1.amazonaws.com/gpartha/heart-failure-app:latest