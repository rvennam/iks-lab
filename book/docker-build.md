# Build the docker image with your application code

Before you can deploy the application on the cluster, you first need to build the Docker image.

1. **Build** a Docker image. Make sure to replace the value region and namespace
    ```sh
    docker build . -t <region>.icr.io/lab-registry-rtp/todo-<lastname>:1.0
    ```
    > Region is **us** for the US.

1. Verify that the image was successfully added to your local docker registry
    ```sh
    docker images
    ```
    Output:
    ```
    REPOSITORY                         TAG                 IMAGE ID            CREATED             SIZE
    us.icr.io/lab-registry-rtp/todo-rvennam   1.0                 7ca722eb7848        6 seconds ago       97.5MB
    node                                      11.13.0-alpine      f34bcc2815ed        3 months ago        75.4MB
    ``` 
