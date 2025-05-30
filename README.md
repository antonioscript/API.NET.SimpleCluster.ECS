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


# ECR

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
```
![image](https://github.com/user-attachments/assets/b58f6598-1072-45e4-9386-6faa54c3c42f)


# ECS


## Create a Cluster on ECS
Follow all the standard step by step to create the cluster


## Create a Task Definition

Follow all the standard step by step to create Task Definition

![image](https://github.com/user-attachments/assets/6cb7db1f-8164-4ab0-8d74-230deb9176df)

## Create a Service
Follow all the standard step by step to create a Service

# References

![image](https://github.com/user-attachments/assets/8d69fcb7-92d9-4e38-bd2c-417871df1459)

https://codewithmukesh.com/blog/deploy-aspnet-core-web-api-to-amazon-ecs/#getting-started---deploy-aspnet-core-web-api-to-amazon-ecs

https://www.rahulpnath.com/blog/amazon-ecs-dotnet-api-hosting/
