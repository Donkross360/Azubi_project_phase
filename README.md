# Azubi & AWS Solution Architect Project 

## Version 1 And 2

 ### Version1
## Create a simple HTML form.
- fire up your ide prefarably VScode
- create a folder and cd into it.
inside the folder create a file and name it index.html, write a simple static html form code snippet.
- create a docker file and name it Dockerfile without any extension. 
- push your code to github. 
- Use the docker image build command to create a image using the instructions in the Dockerfile.
- Use the docker run command to start a new container from the image you created.
- If done properly you should see you app running on port 80 on localhost
- Finally push your image to Docker Hub.
- From Docker Hub anyone can pull and run the exact copy of your app on any computer.


### Version2

## Push Your image to Amazon ECR and create a cluster with a task definition

- In this version we will create a frontend html form and a backend simple code snippet in php programming language.
- The backend only needs to get the post request from the frontend html form and send back a response to the frontend when a post request with the correct credentials is successful or not.
- Once again following the same steps as the version1 we build an image from the instruction in the dockerfile expose it to port 80 and so on...
- create an Amazon ECR repository, tag and push your image to the repo.
- create a task defenition on Amazon ECS attach an execution role to it also point it to your image in the repository.
- create a cluster and a service and point it to the task definition.
- click the task tab, click your created task, check for the public ip address, paste it in the browser, you should see you app running.
Do not forget to tear down all the infrastructure created when you are done.