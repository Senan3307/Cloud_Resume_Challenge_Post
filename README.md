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
