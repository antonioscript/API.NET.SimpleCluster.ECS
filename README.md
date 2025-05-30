# API.NET.SimpleCluster.ECS
A simple .NET API running as a single task in AWS ECS, ideal for lightweight workloads.

## Application

## Containerize the application
Right-click on the project, then select 'Add', and choose 'Docker Support

## Create a image
```
docker build -t simple-project .
```

## Create a Container
```
docker run -d -p 8080:8080 simpleproject
```

## Create a Repository on ECR
