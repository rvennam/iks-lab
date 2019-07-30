# Scale the application manually using the replica

The application was deployed with 2 replicas. Let's scale it to 3 replicas.

1. Let's scale up to 3 replicas
    ```sh
    kubectl scale --replicas=3 deployment/mytodos
    ```

1. Then, inspect your Pods again.
    ```sh
    kubectl get pods
    ```
    You should now see 3 pods.
    

# Auto scaling using HPA (Horizontal Pod Autoscaler)

1. Apply policy 
    ```
    kubectl autoscale deployment mytodos  --cpu-percent=20 --min=1 --max=10
    ```
 2. Simulate load to the app
     ```
    for i in {1..10}; do sleep 0.05; curl https://todo.<INGRESS SUBDOMAIN>/loadtest; done
    ```
