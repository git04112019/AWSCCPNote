# Application and Customer Engagement Services

## Application Services

* Step Functions: Coordinate components of distributed applications and microservices using visual workflows.
* Simple Workflow Service (Amazon SWF): Helps developers build, run and scale backgound jobs that have parallel or sequential steps.
* Simple Notification Service (SNS): Push notification service.
* Simple Queue Service (SQS): Message queuing service, that is, hold messages untill server are able to process it.

### Process Decoupling Example

* If average demand exceeds processing capacity, queue will grow indefinitely
* SQS can provide Cloud Watch metrics that can be used with auto scaling.

## Customer Engagement Services

* Amazon Connect: Self-service contact centre. Provided with PAYG pricing model, drag-and-drop UI, able to create process flows.
* Amazon Pinpoint: Run targeted campaigns to drive user engagement in mobile apps, e.g. send email, SNS, messages.
* Amazon Simple Email Service (SES): Build in Email service.

### Lab: Email with SES

#### Single Email

Send via SES -> Verify at Email -> ok

#### Bulk Email

SES -> request a send limit increase -> Fill in Form -> AWS process it with result giving