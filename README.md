# Django Notes App
This is a notes app built with React and Django.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/29af75b8-3d89-4a12-942b-37fbcc2d81d6" />

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/AkshatPareek9/project-django-notes-app.git
```

2. Create Dockerfile and Build the app
```
vim Dockerfile

docker build -t notes-app .

docker images
```

3. Run and test the app
```
docker run -d --name notes-app-container -p 8000:8000 notes-app:latest
```

4. Stop and Delete the container
```
docker stop notes-app-container && docker remove notes-app-container
```

5. Push the Image to DockerHub	

 - Login to DockerHub
 - Generate Token in Account Settings
 - Use Docker CLI command for login to Docker CLI client.
   ```
   docker image tag notes-app:latest akshatpareek9/notes-app:latest

   docker images

   docker push akshatpareek9/notes-app:latest
   ```

6. Automate the deployment using Kubernetes cluster
```
mkdir k8s
cd k8s

vim namespace.yaml
vim deployment.yaml
vim service.yaml

kubectl apply -f namespace.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

sudo -E kubectl port-forward service/notes-app-service -n notes-app-namespace 80:8000 --address=0.0.0.0
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`	
`sudo apt install nginx`

---

# Project Jenkins

Github ---- git clone --->  Docker ---- build and push ---> Docker Hub ------ deploy ---> EC2

<-------------------------------------- JENKINS -------------------------------------------->

<img width="639" height="229" alt="image" src="https://github.com/user-attachments/assets/5846b842-ac13-40eb-9b6f-d0c633197d5b" />

github -------- auto build --------> 
(push) <------- Webhook ----------- Jenkins
