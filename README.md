# Dockerfile
Dockerfiles for different developing environment.
1.Usage:
  (1)revise the dockerfile to fit your project 
  (2)copy the dockerfile to the project path
  (3)run "$docker build -t name/projectname ."  -t is the tag, '.' is the dockerfile path.
  (4)now you have a image named "name/projectname"
  (5)run "$docker run -d -P --name websit imageID CMD 

2.Files

  Node_Express 
    This file is the dockerfile for the Node.js developing and producting environment. 
    And Express is installed, you can use express to creat a web app.
    How to use it:
    (1)change the "RUN express -e website", website is your webapp project name. '-e' use the ejs model.
    (2)you can install the dependencies by "RUN npm install" or by "ADD" the package.json you have revised.
    (3)If you are not run the docker container in a demmon status, you can change the "CMD["npm","start"]" ,CMD is the comand that you want to run when the container start.
  
  Python
    This file is the dockerfile 
