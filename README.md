# Cloud_Resume_Challenge_Post

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
