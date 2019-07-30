# Clean up the environment

1. Delete the deployment and the services
    ```sh
    kubectl delete -f ingress-tls-deploy.yaml
    ```
2. Delete the HPA
    ```
    kubectl delete hpa mytodos
    ```
