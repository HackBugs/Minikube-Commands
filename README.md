## Minikube-Commands

<details><summary><b><h2>Kubectl Commands</h2></b></summary>

```sh
kubectl get pods
```
```sh
kubectl apply -f pod1.yml
```
</details>

<details><summary><b>Script</b></summary>
- Create folder - mkdir minikube-pods-script
- vi pod1.yaml - Now use this Script 
  
## CREATE POD
```sh
kind: Pod                              
apiVersion: v1                     
metadata:                           
  name: testpod                  
spec:                                    
  containers:                      
    - name: c00                     
      image: ubuntu              
      command: ["/bin/bash", "-c", "while true; do echo Hello-Bhupinder; sleep 5 ; done"]
  restartPolicy: Never         # Defaults to Always

kubectl apply -f pod1.yml
```
## MULTI CONTAINER POD ENVIRONMENT 
```sh
kind: Pod
apiVersion: v1
metadata:
  name: testpod3
spec:
  containers:
    - name: c00
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo Technical-Guftgu; sleep 5 ; done"]
    - name: c01
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo Hello-Bhupinder; sleep 5 ; done"]
```
### POD ENVIRONMENT  VARIABLES
```sh
kind: Pod
apiVersion: v1
metadata:
  name: environments
spec:
  containers:
    - name: c00
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo Hello-Bhupinder; sleep 5 ; done"]
      env:                        # List of environment variables to be used inside the pod
      - name: MYNAME
        value: BHUPINDER
```
### POD WITH PORTS
```sh
kind: Pod
apiVersion: v1
metadata:
  name: testpod4
spec:
  containers:
    - name: c00
      image: httpd
      ports:
       - containerPort: 80  
```
</details>
