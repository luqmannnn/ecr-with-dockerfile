# Push Docker images to AWS ECR

## Docker Flow
![image](https://github.com/luqmannnn/ecr-with-dockerfile/assets/9068525/6535635b-838e-4175-b4f0-fedaad61d6d6)

## What is a Docker image?
A Docker image is a lightweight, standalone, and executable software package that includes everything needed to run a piece of software, including the code, a runtime, libraries, environment variables, and config files. It serves as a template or blueprint for creating a containerized application.

## What is a Docker container?
A container is a sandboxed process running on a host machine that is isolated from all other processes running on that host machine. That isolation leverages kernel namespaces and cgroups, features that have been in Linux for a long time. Docker makes these capabilities approachable and easy to use. To summarize, a container:

1. Is a runnable instance of an image. You can create, start, stop, move, or delete a container using the Docker API or CLI.
Can be run on local machines, virtual machines, or deployed to the cloud.
2. Is portable (and can be run on any OS).
3. Is isolated from other containers and runs its own software, binaries, configurations, etc.

https://docs.docker.com/get-started/ 

## What are some Docker images' registries?
1. Dockerhub
2. AWS ECR
3. JFrog Artifact Repository

## Getting Started
![image](https://github.com/luqmannnn/ecr-with-dockerfile/assets/9068525/e6700ca6-1347-42ca-b5ad-c5845c0e8928)

We will need the following files to create a Docker image:
1. Dockerfile (contains steps to package and build an image)
2. Simple application code and binaries (to be packaged into an image)

Given the above, we will then create a workflow file (placed in .github/workflows) that will do the following:
1. Connect to AWS to retrieve ECR registry information
2. Build docker image from Dockerfile
3. Push docker image into AWS ECR

Once image has been pushed, we can verify by heading over to the AWS console to verify in ECR or using AWS CLI to retrieve the list of images in ECR.

## Future improvements
1. Integration with image scanning tools: Docker Scout, Snyk, Aqua Security
2. Integration with container orchestration tools: AWS ECS, AWS EKS
