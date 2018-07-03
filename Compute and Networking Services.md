# Compute and Networking Services

## Compute Service

* Elastic Compute Cloud (EC2): Virtual Servers in AWS Cloud. PAYG pricing.
* Amazon Machine Image: Template that contains the software configuration required to launch your instance.
* EC2 Autoscaling: Dynamically scale EC2 capacity up or down. Setup rules and health check to launch and terminate instance.
* Amazon Lightsail: The easiest way to launch server/application. Simplified EC2
* Elastic Container Service (ECS): Highly scalable and high performance container management service for docker containers. Docker containers run on managed cluster of EC2 instance
* Amazon Lambda: Serverless service, run code in AWS cloud without worrying about managing instance.

### Lab: Web Server and Scaling

1. In VPC, launch EC2 instance, can be with service e.g. Wordpress
2. Vertical Scaling: If current instance not strong enough, terminate and launch a bigger one. Con: Long offline time. Hard to scale if flow various. Not economical.
3. Horizontal Scaling: Add more instance as demand goes up, vice versa. Con: Multiple endpoint.
4. Elastic Load Balancing:

```
    1. Receive traffic at one endpoint, destribute traffic to instance that is avaliable. 
    2. Balance the load accross. 
    3. If one instant is not healthy, ELB won't send traffic to that EC2.
```

5. Auto Scaling: Launch EC2 when demand increase, vice versa. Replace unhealthy instance with healthy instance during health check.

## Networking and Content Delivery Service

* Cloud Front: Global *Content Delivery Network (CDN)*, delivery frequently requested content securely to edge location accross the globe to reduce latency. Also protect against DDoS attacks.
* Virtual Private Cloud (VPC): Logically isolated section of AWS Cloud. Launch instance within.
* Direct Connect: High speed dedicated connection to AWS. e.g. enterprise can use it to estabulish private connection to AWS Cloud.
* Elastic Load Balancing: Automatically distribute incoming traffic accross multiple ec2 instances, also to multiple Avaliability Zones (Disaster Recovery, fault tolerance).
* Route 53: DNS.
* API Gateway: Fully managed service that allow developers to create and deploy secure Application Programming Interface (API). Serverless service.

### Lab: Networking Service

#### Multiple AZ Architecture

1. Architecture VPC accross multiple avaliability zones.
2. Use ELB to distribute traffic accross.
3. If one AZ goes down, ELB will distribute traffic to AZ that is still healthy.

#### Architecture with Cloud Front CDN

4. Can also use Cloud Front to distribute information accross the globe, reduce latency and load of ELB.
5. If dynamic contents: Traffic -> Cloud Front -> ELB -> EC2 instance
6. N.B. CDN has its DNS.

#### Add in Route 53 DNS

 Route 53 get request -> Forward to Cloud Front

#### Architecture with On-premise Data Centre

AWS <-> AWS Direct Connect <-> Corporate Data Centre
