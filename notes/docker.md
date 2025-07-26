1. <b>Dockerfile</b> specifies one image configuration with base image, internal dependencies, volumes(files synced with host) and commands run on start.
2. <b>docker-compose.yml</b> *orchestrates* how to run several services together: their images, volumes, dependencies on each other, options (i.e cli options) and their network communication (virtual networks).
