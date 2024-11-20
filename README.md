# Cloud_Resume_Challenge_Post

# The What and Why of the Cloud Resume Challenge 

The Cloud Resume Challenge is a project designed to help individuals gain hands-on experience with cloud computing. The challenge involves creating and hosting your personal resume on a cloud platform like AWS, using HTML, CSS, Javascript, and implementing various cloud technologies. Key requirements include setting up a custom domain with HTTPS, building a visitor counter using a back-end API, storing visitor data in a database, and managing the infrastructure using tools like Terraform. Additionally, I was required to integrate a CI/CD pipeline for automated testing and deployment, as well as document their work in a GitHub repository. These steps provide a practical introduction to essential cloud services and development workflows.

The challenge was an excellent way to develop and showcase cloud computing skills, making it ideal for beginners like myself or those looking to break into the tech industry. It offers hands-on experience with key cloud concepts, such as hosting, APIs, databases, and version control, while teaching problem-solving and best practices. Beyond technical learning, the project serves as a professional portfolio piece, demonstrating initiative and technical ability to potential employers. By completing the Cloud Resume Challenge, participants not only build confidence in their cloud skills but also create a standout resume that speaks to their dedication and expertise.

# Services Used and the purpose for each service

## S3
Hosts the static website for the resume. S3 provides scalable storage for the HTML, CSS, and JavaScript files, making it a cost-effective way to deploy static content. In this project, the S3 buckets created such as senanotsuka.com held files like my index.html, images, and many more. 

## Route 53
Manages the DNS (Domain Name System) for the custom domain, directing traffic to the S3 bucket or CloudFront distribution. It helps set up a custom domain name (e.g., yourname.com) for the website.

## Lambda
Implements serverless backend logic, often used to update a visitor counter on the website. Lambda functions run backend code triggered by specific events without needing a dedicated server. In this case, it was the java script that updated the visitor counter. 

## API Gateway
Acts as a serverless API endpoint that triggers the Lambda function. API Gateway provides a secure and scalable way to expose the Lambda function to the web for handling requests (like tracking website visits).

## DynamoDB
Serves as the database to store visitor counts or other data related to the resume site. DynamoDB is a managed NoSQL database that integrates well with Lambda and can handle high request volumes.

## IAM
Manages permissions for the AWS resources, ensuring secure access. IAM policies are applied to Lambda, S3, and DynamoDB to control which resources each service can access. IAM is especially important in terms of security. If a person is able to get a root user access, they are able to conduct expensive actions on AWS. 

## CloudFront
Serves as a content delivery network (CDN) to cache and deliver the website content globally with low latency. CloudFront improves the performance and availability of the website, especially for users in different geographic locations.

## EC2
A service that provides scalable virtual servers, or instances, in the cloud.
