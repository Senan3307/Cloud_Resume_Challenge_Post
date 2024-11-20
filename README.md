# Cloud_Resume_Challenge_Post

# The What and Why of the Cloud Resume Challenge 

The Cloud Resume Challenge was an incredible project that gave me hands-on experience with cloud computing. I created and hosted my personal resume on AWS, using HTML, CSS, and JavaScript, while diving into various cloud technologies. Some key steps included setting up a custom domain with HTTPS, building a visitor counter with a back-end API, and storing visitor data in a database. I also managed the infrastructure using Terraform and implemented a CI/CD pipeline for automated testing and deployment. Throughout the process, I documented my work in a GitHub repository, which helped me organize my project and showcase my progress.

For me, the challenge was an excellent way to learn and demonstrate cloud computing skills. It provided hands-on experience with hosting, APIs, databases, and version control, all while teaching me problem-solving and best practices. Beyond the technical skills, completing the project gave me something that I can add onto my resume that highlights my initiative and technical abilities to potential employers. By the end, I felt more confident in my cloud skills and my ability to deploy various tools on AWS adequately. 

# Services Used and the purpose for each service

## S3
S3, which stands for simple storage service, hosted the static website for the resume. S3 provides scalable storage for HTML, CSS, and JavaScript files while also being extremely durable, making it a cost-effective and reliable way to deploy static content. In this project, the S3 buckets created such as senanotsuka.com held files like my index.html, images, and many more. 

## Route 53
Route 53 manages the DNS (Domain Name System) for the custom domain (senanotsuka.com) while also directing traffic to the S3 bucket or CloudFront distribution. It helps set up a custom domain name so that users don't have to memorize complex sequences to get to your website. 

## Lambda
Lambda implements serverless backend logic which was used to update the visitor counter on the website. Lambda functions ran the backend code triggered by specific events without needing a dedicated server. In this case, it was the java script that updated the visitor counter. 

## API Gateway
The API gateway acts as a serverless API endpoint that triggers the Lambda function. API Gateway provides a secure and scalable way to expose the Lambda function to the web for handling requests (like tracking website visits).

## DynamoDB
DynamoDB serves as the database to store visitor counts or other data related to the resume site. DynamoDB is a managed NoSQL database that integrates well with Lambda and can handle high request volumes. In the cloud resume challenge, we decided to use a NoSQL database like DynamoDB instead of a relational database like RDS because it is fully serverless and managed, and since the visitor counter typically involves storing simple key-value pairs, DynamoDB was a better fit. 

## IAM
IAM Manages permissions for the AWS resources, ensuring secure access. IAM policies are applied to Lambda, S3, DynamoDB, and various other resources to control which resources each service can access as well as users. IAM is especially important in terms of security. If a person is able to get a root user access, they are able to conduct expensive actions on AWS. Thus, typically, users should not use root user access when using AWS. 

## CloudFront
Cloudfront serves as a content delivery network (CDN) to cache and deliver the website content globally with low latency. CloudFront improves the performance and availability of the website, especially for users in different geographic locations. Further, along with Certificate Manager, CloudFront allows the website to be securely accessed through HTTPS by acting as a secure, distributed network layer between users and the website's origin server. 

## EC2
A service that provides scalable virtual servers, or instances, in the cloud. While we learned about this in class, we did not use the service mainly for cost purposes. Running a virtual machine through an EC2 instance would cost us money as well as not being serverless. The whole theme of the project is to create a serverless architecture and EC2 would require us to use and manage servers. 

# What I learned through the Cloud Resume Challenge

The first important skill I learned through the cloud resume challenge was the importance of having good identity and access management habits on AWS. The root user on AWS holds a lot of power and if someone gains access to your root access, they could use your account to complete extremely expensive tasks on your account. Further, if your AWS account had any sensitive or important information on it, root access would allow the user to gain access to various tools on AWS, causing a major security breach. Thus, one of the first things we did was use IAM to manage IAM roles and policies. This way, when using AWS resources, we did not have to use the root account. We essentially learned about the principle of least privilege and beginning by assigning as little privilege as possible. Further, when we linked AWS to various tools such as VScode, we had to allow the terminal on VScode to gain access to AWS through the AWS Command Line Interface(CLI). However, one of the most important things was to never input your user information onto the AWS CLI because it could be accessed by anyone and lead to your root user being accessed. Thus, instead of inputting any data into the CLI, we used a Key Pair to have a secure mode of accessing AWS through the VScode terminal. Overall, I learned through this project the importance of having good security habits through access management by understanding who has access to what and ensuring that the least possible privilege is assigned. 

Another important technique and skill I learned throughout this project was automation using the CI/CD pipeline. At the beginning of the project, I would have to frequently go to the AWS console, press multiple buttons by going to each service in AWS, and click on the settings I wanted to configure to enable a certain process. However, through automation using CI/CD actions and Infrastructure as Code, I no longer had to log into the AWS console and I could configure many things through my terminal in VScode which saves a lot of time while also reducing human error. Terraform was used for Infrastructure as Code, which streamlined the deployment, testing, and management processes. For example, if I wanted to deploy the whole project fro scratch, it would be much faster since the Infrastructure is already written as code so I would only need to re-run the code. Further, we were able to easily conduct unit, system, and end-to-end tests because we had the whole infrastructure as code which meant we could figure out the problem with the infrastructure with ease. The CI/CD pipeline was done through github and github actions. By having the CI/CD pipeline, we were able to detect problems with the delivery with ease using the github actions as well as having more reliable deployment. 


