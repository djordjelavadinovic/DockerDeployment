# Docker Build & Deployment Process

## Pre-build steps

1. Pre-fetching base image from Docker Hub
2. Pulling source from source repository
3. Pre-build of a new base image 
4. Static program analysis

## Build steps

1. Compiling
2. Image creation
3. Unit testing
4. Local publishing of image

## Further testing

1. Deploying of containers on test environment
2. Automated integration testing
3. QA steps
4. Publishing on public site

## Deploying in production

1. Pulling images from public site and caching in local repository
2. Testing
3. Replacing running containers with new images
