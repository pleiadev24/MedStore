For instructions on AWS - Refer Developer manual.

## Code 
back-end code - https://github.com/rohinimohan14/MedStore-backend
front-end code - https://github.com/SS3789796/medstore-frontend 

## Architecture
The diagram provided above gives a high-level overview of the AWS services used in this
application. The services mentioned in the diagram are as follows:

 ![alt text](https://github.com/rohinimohan14/MedStore/blob/main/architecture.png) 

### AWS Elastic Beanstalk
Elastic Beanstalk is a PaaS that is designed to support the complete web application
lifecycle. To deploy the backend of our website we were able to automate the setup,
configuration, and provision other AWS services like EC2 and Elastic Load Balancing. In
the MedStore application part, there can be many users accessing at a time, and we did
not want to not worry about controlling scaling and capacity. In this part we wanted to
have the infrastructure abstracted and instead focus primarily on our app. [11]

### AWS Elastic Container Service
It is a fully managed container orchestration service by AWS. We chose ECS for the
consultation part as there is a need for more granular control. As consultations would not
be as often as website visits by users, it does not require frequency access. By also
keeping the pricing in mind, ECS was a feasible solution. [22]
### AWS Elastic Container Registry
ECR is a container image registry service. Amazon Elastic Container Registry integrated
easily with Docker and ECS, simplifying the deployment process. [23] ECR was used
alongside ECS to deploy the consultation process of the application.
### AWS Lambda
Lambda is a computing service that runs code in response to events and automatically
manages the computing resources required by it. It is used along with Lex [16] for
business logic execution- which is selecting slots, type of appointment in consultation
scheduler bot. AWS Lambda function is used as a code hook for the bot and the bot
returns the intent information to the Lambda function in the application. [15]
### Amazon S3
S3 is an object storage that is accessible through a web service interface. That is then
set to enable static website hosting. The tier selected is standard, general purpose
storage and can be frequently accessed.[20] S3 was used to deploy the static website
along with CloudFront. It was also used to store the images used in the application.

### Amazon Lex
Aws Lex is used to make conversational bots. Lex is used within the application to create
appointments for consultations. The conversational structure and expected inputs/outputs
are specified in the console.[16] It is integrated natively with other AWS services like
Lambda to deliver an interactive experience. [15]

### Route 53
Our website did not have a domain to safely host the website in Https. Using Route 53,
we were able to register a domain name under .com. The implementation details are
specified in the later part of this report. [17]
### AWS CloudFront
CloudFront is a CDN (Content delivery network) that gives the advantage of a globally
distributed network of proxy servers that cache content, such as web videos or other bulky
media, locally to end users, and this improves the speed for downloading the content.[18].
### Amazon Certificate Manager
To add an SSL certificate and enable safe transactions in our website, we requested a
certificate from Amazon Certificate Manager.
### Others
To manage permission and login, IAM (Identity and Access Management) was used.

