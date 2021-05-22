# Fibonacci Series Generator using Multi-Container Architecture of Docker

## User Interface has been bootstrapped with **[Create React App](https://github.com/facebook/create-react-app/ "Visit Facebook Open Source Git Repo")**.

This is a demo app built with an intention to successfully deploy a multi-container docker app on **AWS BEANSTALK** and can be served to end user. 
>Note: You can also deploy this app on your local server by just using *Docker-compose.yml* present in the root directory of this project, it will get deployed on **NGINX server**


### How to use the project:
* Clone the repository
* Navigate to the root directory of the project in your terminal
* For deploying it on you localhost:
    + run command **"docker-compose up --build"**
    + Access the application on **[localhost:3050](http://localhost:3050/ "Visit localhost:3050")**
* For deploying it on AWS:
    + Setup Travis-CI
    + Setup AWS and it's services
    + Go to Elastic Beanstalk application and click on the URL provided for accessing the application over there


### **Tech-Stack Used:**
* For Development Environment
  + Docker
  + Docker-Compose
* For Deployment Environment
  + Docker
  +  Travic-CI
  +  AWS
      - Elastic Beanstalk
      - RDS (Postgres)
      - ElastiCache (Redis)
      - IAM

### Purpose of each file and folder in the root directory:
|File/Folder|Purpose|
|---|---|
|client|Font End of the Application|
|server|Express server|
|nginx|Nginx server to route traffic between client and server|
|worker|Actual logic for calculating the result and sending it back to redis-server|

## Project Architecture:

### Application FLow: <br>
![App Flow](https://user-images.githubusercontent.com/25420937/119230509-23ea7f80-bb3a-11eb-9547-08aac057b265.jpg)

### Nginx default.conf file: <br>
>**Purpose:** This file is going to override the default configuration of nginx that we receive out of the box and set them according to our project's requirement(s). <br>

![default conf architecture](https://user-images.githubusercontent.com/25420937/119232019-3c11cd00-bb41-11eb-8624-95473a034b80.jpg)

### Development Environment Flow: <br>
![App Architecture](https://user-images.githubusercontent.com/25420937/119231307-d53ee480-bb3d-11eb-9c75-725d407c4446.jpg)

### Production Environment Flow: <br>
![Multi Container Prod Setup](https://user-images.githubusercontent.com/25420937/119231314-e4be2d80-bb3d-11eb-9e15-310866ed7ffb.jpg)
