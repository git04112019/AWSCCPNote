# AWS Certified Cloud Practitioner

## Module 1 Introduction to AWS Cloud

### What is Cloud computing

Cloud computing is the on-demand delivery of compute power, database storage, applications, and other IT resources through a cloud service platform via the internet with pay-as-you-go pricing. -AWS

### Benefit of AWS Cloud

High capacity, reliability, agility

Agility(敏捷）, the NO.1 reason that customers switch to cloud computing: speed, experimentation and culture of innovation

#### Global

1. Increase of global reach.
2. New resources click away, fast reach to customers.
3. Dramatic increase in agility.

#### Experimentation

1. Operations as code
2. Safely experiment

    For example: Spin up servers in minutes for experimenting, Returen or re-purpose servers,

3. Testing using different configuration: like different VPC, different Hadroop.
4. Templates environments

#### Innovation

1. Experiment quickly with low cost/risk
2. More experimentation more often
3. Discovery

### Infrastructure

Elasticity, scalability and reliability of computing resources(e.g. change in infrastructure settings, data centre security).

#### Regions, Availability Zones and CloudFront

Regions:

* Physical locations in the world (e.g Tokyo, Australia-Sydney...)
* Contains multiple availability zones (e.g. Tokyo 1 2 3)
* AWS has 18 Regions

Availability Zones (AZs):

* One or more discrete data centres
* Redundant(冗余): extra resources and back up powers
* Housed in separate facilities.
* AWS has 49 availability zones

Availability Zones allow **fault tolerance** and **high availability**

* Fault Tolerance:
  * Application operational during component failure.
  * build in redundancy of component.(e.g. auto check, AWS CloudWatch etc.)

* High Availability:
  * Make sure that the system is 'always' functioning and accessible.
  * Down time is minimized as much as possible.
  * Without the need for human intervention.

We can see that AWS data centres use both physical and digital security protocol.

CloudFront: distribute at edge locations for high performance delivery of content. There are over 50 edge locations across the globe where we can cache our regular used data.

#### Elasticity, Scalability and Reliability Benefits

Scale computing resources up or down easily:

* Quick deploy new applications e.g. WordPress or Apache auto installations
* Instant scale up
* Instant shutdown
* scale down and not paid for infrastructure

Elastic:

* Use services at own pace.
* Adapt consumption (e.g. promotion time of game gives server a high demand).
* Launch new services or products.
* Accommodate new strategic directions

Scalability:

* Tools to run a wide range of applications.
* Auto scaling and Elastic Load Balancing
  * Scale up or down based on demand (e.g. game promotion)
* Deploy your system in multiple regions.
  * Lower latency and better experience (e.g. avoid lagging)
* Innovative services and cutting-edge technology
* virtualy any workload

Security:

* Customer retain control over region where data located (Customer can select regions they want to deploy their server)
* Security auditing often periodic and manual (Controlling of risk and forecast comes handy)
* AWS Cloud provide governance capabilities(Continue monitor a configuration changes of IT resources)
* Industrial leading capabilities that meet the strictest security requirements (e.g. login key pair, security groups)

#### Data Centre

* AWS use state-of-the-art electronic surveillance
* Multi-factor access control systems (e.g. finger prints and facial recognition)
* Staffed 24/7 by security guards
* Access is strictly least-privileged basis
* Designed for minimize the impact of disruptions
* Multiple regions and AZs enable resiliency

Security policy can be formalised and embedded with the design of your infrastructure.

#### Reliability

* High performing and reliable solutions
* Implement solutions quickly and with limited friction
* Reliability: Ability to recover from failures and dynamically acquire resources to meet demand and mitigate disruptions
* Data centre architecture and system must have well-planned foundation: that can handle changes in demand and detect failure as well as automatic heal itself
* Achieve greater flexibility and capacity
* Reduce uncertainty of forecasting hardware needs
* AWS gives customer capacity and reliability that is difficult to march by on-premise (self server) solutions.

#### Pricing

* Avoid spending resources (human & financial) on infrastructure.
* PAYG system:
  * Make you focus on innovation and invention
  * Easy to use
  * Flexible billing such as adapting needs
  * Improve responsiveness to changes
  * reducing risk or over provisioning or missing capacity

### Models of Cloud Computing

* **Infrastructure as a Service (IaaS)**: Contains the basic building of IT: e.g. VPC, EC2, EBS
* **Platform as a Service (PaaS)**: AWS(service provider) manages the underlying infrastructure (usually hardware and operating systems) e.g. RDS,EMR,Elastic Search
* **Software as a Service (SaaS)**: Complete product that us run and managed by the service provider. Mostly refers to end-user applications e.g. Web-based email, Office 365, Amazon Workspaces.
* Serverless Computing: Allow you to build and run applications and services without thinking about servers. Also refer to as **Function as a Service (FaaS)** or abstracted service. e.g. Amazon Simple Storage Service (S3), AWS Lambda, Amazon DynamoDB, Amazon SNS

The level of service provided: IaaS->PaaS->FaaS->SaaS

### Lab Session 1 v1.11

**S3**
Create a S3 Bucket, upload document.

S3 is basically a dropbox like storage space but with API

**RDS with MySQL**
1. Click into RDS, launch instance then click MySQL.
2. Use db.t2.micro
3. Setup master username and password
4. Setup Network and Security
5. Enter a database name.
6. Launch instance

**EC2 with Wordpress**

1. Select EC2, then select launch instance
2. At marketplace select WordPress
3. Select and continue
4. Choose t2.micro
5. Enable auto assign public IP
6. Launch
7. Finding the Username and Password for your WordPress application: Go back to the EC2 console and select “Instance Settings”, “Get System Log”. 
8. Scroll down until you find the log entry for the application password and copy it.

**AWS SES**

1. Select SES->Email Addresses.
2. Click Verify a New Email Address.
3. Refresh to see if it has been verified
4. Select address->send test email
5. Fill in then send

Full Access:

1. Click sending statistics
2. Request a Sending Limit Increase

Create a Billing Alert with CloudWatch and SES:

1. Click on Username, then My Billing Dashboard
2. Select Preference, then select Receive Billing Alerts
3. The create a CloudWatch Alarm: Click Service menu and select CloudWatch from Management Tools
4. Click on Alarms, Create Alarm
5. Select Total Estimated Charge from the billing metrics
6. Select EstimatedCharges metrics,click Next
7. Give the alarm a name and description
8. Set the alarm threshold to $10
9. Click New List
10. The topic a name monthly-billing-alert and put in your email address.
11. Click Create Alarm. If you haven’t already confirmed your email and confirmation email will be sent to you.
12. Click on confirm subscription in the email you receive.
13. Go back to the CloudWatch console and refresh the screen.
14. If you can’t see your alarm then make sure All alarms is selected for the filter.

**Create a Highly Avaliable Architecture with Elastic Beanstalk**

1. Click on Service menu and select Elastic Beanstalk
2. Click Create New Application, fill detail, create
3. Select Actions -> Create Environment (it might be auto skipped by the server)
4. Create Web server environment: Select Node.Js as the platform 
5. Select Sample Application for Application Code 
6. Click Configure More Options
7. All next, Click Launch

