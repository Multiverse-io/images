# Multiverse public docker images

This repo contains the Dockerfiles for our public images which are hosted in GitHub Container Registry.

This is only for **public** images - **DO NOT** publish images with private code into this repository. Our private docker images live on Amazon ECR.

All images are automatically built and pushed on the `main` branch.

## The images

| Name      | Description |
| --------- | ----------- |
| elixir-ci | Used for elixir builds in CI. Based on hexpm/elixir alpine images and contain a few extras packages |
| platform-production | Base image for our production builds. Alpine with a few extra packages |

## Image tags

Please ensure the image tags in the GitHub actions workflows are updated whenever the docker base images are updated, or other breaking changes are made to the images.
