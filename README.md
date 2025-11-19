# Django Notes App
This is a notes app built with React and Django.

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
	5.1.	Login to DockerHub
	5.2. 	Generate Token in Account Settings
	5.3.	Use Docker CLI command for login to Docker CLI client.
		```
		docker image tag notes-app:latest akshatpareek9/notes-app:latest
		
		docker images

		docker push akshatpareek9/notes-app:latest
		```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
