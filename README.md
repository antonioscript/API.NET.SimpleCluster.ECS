# API.NET.SimpleCluster.ECS
A simple .NET API running as a single task in AWS ECS, ideal for lightweight workloads.

# Application

## Containerize the application
Right-click on the project, then select 'Add', and choose 'Docker Support

### Create a image
```
docker build -t simple-project .
```

### Create a Container
```
docker run -d -p 8080:8080 simpleproject
```

## Create a Repository on ECR
Follow all the standard step by step to create the repository and copy the URI

![image](https://github.com/user-attachments/assets/a7a44d5c-3e9c-4eda-82a8-1cfa136c830f)

### Execute commands on terminal

</br> **PS: Make sure that you replace the 637423290521 with your AWS account id**


```
aws ecr get-login-password | docker login --username AWS --password-stdin 637423290521.dkr.ecr.us-east-1.amazonaws.com
```


```
docker tag simple-project 637423290521.dkr.ecr.us-east-1.amazonaws.com/ecs/simple-project
```

```
docker push 637423290521.dkr.ecr.us-east-1.amazonaws.com/ecs/simple-project
