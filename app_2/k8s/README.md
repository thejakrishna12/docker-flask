kind create cluster
----------------------------
![image](https://github.com/user-attachments/assets/3e03a6be-0601-45cf-a73d-ddee3cebf403)


kind create cluster --name kind --wait 60s
----------------------------------------------

![image](https://github.com/user-attachments/assets/40106d7a-a402-4a4a-8c8a-313166ed8cc5)

kubectl cluster-info
--------------------------------------------
![image](https://github.com/user-attachments/assets/7f408a8a-8307-46c7-a5f4-ce9ad49a4e33)

kubectl get nodes
---------------------------------------------

![image](https://github.com/user-attachments/assets/4b8e9aa9-2f43-40ed-a991-feb08f00c8e6)

kubectl config get-contexts
------------------------------------------

![image](https://github.com/user-attachments/assets/ce9f33f5-7c7b-49fb-9faa-c738417243a7)


kind get clusters
---------------------------------------

![image](https://github.com/user-attachments/assets/9dd6b187-5c64-4221-9fab-adcc1a945b14)




Imperative Way
---------------------------------------



Create an Nginx pod
----------------------------------
kubectl run nginx-pod --image=nginx:latest --port=80

![image](https://github.com/user-attachments/assets/0fbcc1a1-7bc9-4d73-af72-17ffa3663b95)


Check pod status
----------------------------------------

kubectl get pods

![image](https://github.com/user-attachments/assets/a8510807-7c63-41ad-ab58-ee746371ea9c)

Describe the pod for more details
----------------------------------------------------------------------------

kubectl describe pod nginx-pod

![image](https://github.com/user-attachments/assets/e8179224-de05-4e9e-a4cf-c35fa981030c)


View pod logs
------------------------------------

sudo kubectl logs nginx-pod

![image](https://github.com/user-attachments/assets/a38a24b4-68b6-4ab4-8d91-a74c5edfa143)


Access the pod in your browser
-----------------------------------------
kubectl port-forward pod/nginx-pod 8080:80

![image](https://github.com/user-attachments/assets/e1146ed7-d6fa-49b0-9294-cb6019b69e88)




![image](https://github.com/user-attachments/assets/46e5a906-b3ee-4061-91a3-2b1ef1c7ec14)



kubectl delete pod nginx-pod
-----------------------------------------

![image](https://github.com/user-attachments/assets/5bcbc303-f7b6-49a3-aa4b-e75359f84d4c)

Declarative Way (Using YAML Files)
------------------------------------------------
1. Create the YAML file

nano nginx-pod.yaml
Open the terminal use nano command to create a yaml file

                    apiVersion: v1
                    kind: Pod
                    metadata:
                      name: nginx-pod-declarative # Name of your pod
                      labels:
                        app: nginx-declarative      # Labels 
                    spec:
                      containers:
                      - name: nginx-container       # Name of the container within the Pod
                        image: nginx:latest         # The Docker image to use
                        ports:
                        - containerPort: 80         # The port the application inside the container listens on


2)Apply the yaml file to the cluster

Use the command:

            kubectl apply -f file-name.yaml
            (eg: kubectl apply -f test.yaml)


![image](https://github.com/user-attachments/assets/5bd442cd-1f03-4bde-984c-c3f8bc850a86)









1.Create the deploymnt
-----------------------------------
nginx-deployment.yaml

    
kubectl apply -f nginx-deployment.yaml


![image](https://github.com/user-attachments/assets/e629504a-d4e0-40be-965a-ec7461d5bf65)






![image](https://github.com/user-attachments/assets/913303e4-b5a4-414d-be8e-ba5629d50582)


Apply to the cluster
Create the NodePort Service
Apply to the cluster




