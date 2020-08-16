# elb-ecs-cp
![Deploy to Amazon ECS](https://github.com/kkkooosss/elb-ecs-cp/workflows/Deploy%20to%20Amazon%20ECS/badge.svg)

# **CI/CD Pipeline with GitHub Actions for build and deploy static html Webdite  to ECS.**

This pipeline has follow workflow:
1. Build the updated docker image based on **nginx:alpine** (with updated html page);
2. Push this updated image to ECR (alb-http-ecs) with new version tag; 
3. Create a new revision of task-definition based on this updated image;
4. Deploy this new revision to ECS cluster.

## *For applying this pipline you should have prerequired resorces on AWS:*


- Create a repository (**alb-http-ecs** in this case).
- Create a ECS cluster with one or more EC2 instances (**my-alb-ec2-cluster** in this case).
- Create a Task-Definition with semple app, which will be updated leter (**elb-autoscalle-task-definition** and container name **alb-scale-cont**in this case).
- Create a Service which will run our tasks bsed on our task-definifion.
- As I use service with autoscalling we need to create ELB (Application Load balancer) for adjust our balance with multiple port mapping. 
-Also we have to configure our AWS credentals in **settings** and create IAM roles with permitions for deployments accordingly.  


