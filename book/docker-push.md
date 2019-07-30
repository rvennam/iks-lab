# Push the docker image to the IBM Cloud Container Registry

Before you can deploy the application on the cluster, you first need to push the Docker image to the IBM Cloud private container registry.

1. Log in to the private **Container Registry** of IBM Cloud. 

    ```sh
    ibmcloud cr login
    ```

1. Retrieve the namespace for the image registry that was created for you.
    ```sh
    ibmcloud cr namespace-list
    ```
    You should get a namespace called **lab-registry-rtp**

1. **Push** the image that you built in the last section to your private image registry.
    ```sh
    docker push <region>.icr.io/<namespace>/todo-<lastname>:1.0
    ```

    > If you get the error `unauthorized: authentication required`, run the command **ibmcloud cr login**

1. Verify that the image was successfully added to your registry in your namespace
    ```sh
    ibmcloud cr images
    ```
    Output:
    ```
    Listing images...
    REPOSITORY                                TAG   DIGEST         NAMESPACE          CREATED         SIZE    SECURITY STATUS
    us.icr.io/lab-registry-rtp/todo-rvennam   1.0   a9238a8d6326   lab-registry-rtp   3 minutes ago   35 MB   Scanning...
    ``` 

1. The image is also visible in the IBM Cloud Console. Go to the [Container Registry](https://cloud.ibm.com/containers-kubernetes/registry/main/start).

    ![](./images/registry-landing.png)
