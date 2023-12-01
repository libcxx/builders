# Building and Tagging Docker Images for libc++

In order to automate the process of building and tagging Docker images for libc++, two Github workflows have been provided: `build-container.yaml` and `tag-container.yaml`. Here is a brief guide on how to use these workflows.

## Build Docker Image Workflow

The `build-container.yaml` workflow allows you to build Docker images for different targets and tag them. The possible targets include 'actions-builder', 'buildkite-builder', and 'android-buildkite-builder'. The workflow can be initiated manually with parameters.

The parameters include:

- **llvm_ref**: The LLVM reference to check out. Default is 'main'.
- **target**: The target for Docker build. Possible values are 'actions-builder', 'buildkite-builder', and 'android-buildkite-builder'.
- **tag**: The tag for Docker image. Default is 'testing'.
- **dry_run**: If set to 'true', the workflow will pull the necessary resources and build the image without pushing it to the Docker registry. Useful for testing purposes.

## Tag Docker Image Workflow

The `tag-container.yaml` workflow provides the capability to retag existing images. This is useful in cases where the tag of an image needs to be updated without having to rebuild the image. This workflow also accepts parameters.

The parameters include:

- **image**: The Docker image to retag.
- **source_tag**: The existing tag of the Docker image.
- **new_tag**: The new tag for the Docker image.

In order to make any changes to the Docker images, you will need to be logged into the GitHub Container Registry. The login process is included in the workflows.
