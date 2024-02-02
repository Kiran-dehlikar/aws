
# Assignment 01

##  Problem Statements

In this assignment you have to learn about deployment strategies:
    - Recreate deployment 
    - Rolling deployment 
    - Blue-green deployment 
    - A/B  deployment
    - Canary deployment 

After this you need to implement these 2 below deployment strategies:
Must Do
    - Recreate deployment 
    - Rolling deployment 
Good to  Do
    - Blue Green deployment
    - Canary deployment 

Recommendation
    - Don't straight forward jump into creating the utility, first do it manually

github-link --> https://github.com/OT-TRAINING/DeploymentStrategies

Hint :
1. Use ASG
2. Use LB
3. Use EC2 service
4. Use AMI Snapshot

# Recreate Deployment
## Basic Requirements 
### Create VPC, 2 Subnets (Public and Private), Route Table, IGW Gateway, NAT Gateway 

### Create a instance for v1 and make the AMI of it.
![Screenshot from 2024-01-22 18-07-13](https://github.com/Kiran-dehlikar/test/assets/104997588/b3668adb-6dc0-496f-ae06-1b5b16c36ee3)

![image](https://github.com/Kiran-dehlikar/test/assets/104997588/798c8e10-b583-49ce-bca7-e730e209723e)

### Create a Target group for Load Balancer
![Screenshot from 2024-01-22 18-06-39](https://github.com/Kiran-dehlikar/test/assets/104997588/e15fb1e0-c7da-47dc-af21-ac08194c6e19)

### Create a Load Balancer and attach Target Group to it.
![Screenshot from 2024-01-22 18-07-25](https://github.com/Kiran-dehlikar/test/assets/104997588/f9256eb5-18ba-46fa-875f-8b8a804f3403)

### Create a Launch Template Create a Autoscaling group and attach Load Balancer to it.
![Screenshot from 2024-01-22 18-08-02](https://github.com/Kiran-dehlikar/test/assets/104997588/8372ba0f-b209-49c3-b0de-0bb354199b6b)

### Go to web browser and hit the Load Balancer dns 
![Screenshot from 2024-01-22 15-53-09](https://github.com/Kiran-dehlikar/test/assets/104997588/cfe37b90-0d9d-493f-b526-b0269ced5981)

### Now change the version in Launch template and Go to the auto scaling group and change the capacity to zero.
### It will shows downtime and then increase the capacity. When the instance gets up it will shows V2. 
![Screenshot from 2024-01-22 18-08-26](https://github.com/Kiran-dehlikar/test/assets/104997588/b16dd187-7842-4680-a7c4-9966298b828e)


![Screenshot from 2024-01-22 16-48-04](https://github.com/Kiran-dehlikar/test/assets/104997588/c8f41260-f949-4457-9e13-7cb33649fbf8)
![Screenshot from 2024-01-22 16-48-15](https://github.com/Kiran-dehlikar/test/assets/104997588/f4e752ea-59b5-45ff-8469-d62e3ccdb609)

# Rolling Deployment 
### Here we use same infrastructure as ablove in it.
### I have 3 servers running in v1 as shown below. By changing the capacity in Autoscaling group.
![Screenshot from 2024-01-22 19-38-15](https://github.com/Kiran-dehlikar/test/assets/104997588/67550ce0-a374-420e-8f2f-932b56a33299)
![Screenshot from 2024-01-22 19-39-45](https://github.com/Kiran-dehlikar/test/assets/104997588/bf39b6d6-20a0-4358-b480-6d8df3ece0cc)
![Screenshot from 2024-01-22 19-39-45](https://github.com/Kiran-dehlikar/test/assets/104997588/694ada25-45f8-496d-98d4-46d96108bd7f)

### It will gradually increase the instances then we change the capacity in autoscaling group to desired as shown in below screenshots.
![Screenshot from 2024-01-22 20-02-28](https://github.com/Kiran-dehlikar/test/assets/104997588/7e02be20-de8c-4ba4-8668-3e424769220f)

![Screenshot from 2024-01-22 20-07-21](https://github.com/Kiran-dehlikar/test/assets/104997588/727fb960-f2f6-431c-bbb9-d2465a359c7e)

### So due to this v1 replaces the v2 gradually with no downtime.
![Screenshot from 2024-01-22 15-53-09](https://github.com/Kiran-dehlikar/test/assets/104997588/cfe37b90-0d9d-493f-b526-b0269ced5981)
![Screenshot from 2024-01-22 16-48-15](https://github.com/Kiran-dehlikar/test/assets/104997588/f4e752ea-59b5-45ff-8469-d62e3ccdb609)


## Authors

- [Kiran Dehlikar](https://github.com/Kiran-dehlikar)
