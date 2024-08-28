# AWS CloudFront and S3 Secure Static Website Hosting

This project demonstrates how to securely host a static website using AWS CloudFront and an S3 bucket.
## What is S3 and CloudFront?

**Amazon S3 (Simple Storage Service)** is a scalable storage service that allows you to store and retrieve any amount of data at any time. S3 is commonly used to store static files, such as HTML, CSS, JavaScript, images, and videos.

**Amazon CloudFront** is a Content Delivery Network (CDN) that delivers your content with low latency and high transfer speeds. CloudFront distributes content globally by caching it at edge locations closer to the end-users. When integrated with an S3 bucket, CloudFront can securely serve content while keeping the S3 bucket private.

## Project Overview

* Set up an AWS CloudFront distribution.
* Configured a private S3 bucket to store website content.
* Used CloudFront to securely serve the content from the private S3 bucket.

Below is the architecture diagram for the project setup:

![Project Architecture Diagram](S3_CloudFront_Project.png)

## Steps to Set Up the Project

### 1. Create a Private S3 Bucket

* Go to the AWS S3 console.
* Create a new bucket and ensure it is private.
* Upload your static website files (e.g., `index.html`) & folders to this bucket.

### 2. Create a CloudFront Distribution

* Navigate to the CloudFront console and create a new distribution.
* Set the origin to the S3 bucket created in the previous step.
* Under "Origin Settings," enable "Origin Access Control" (OAC) to prevent direct access to the S3 bucket.
  * Create a new OAC by providing a name and description.

### 3. Configure S3 Bucket Policy

* Once the CloudFront distribution is created, you'll be provided with a policy to attach to the S3 bucket.
* Go to the S3 bucket permissions and edit the bucket policy to allow access from CloudFront.

### 4. Test the Setup

* Access your CloudFront distribution URL to ensure the static website is being served correctly.
* Ensure that direct access to the S3 bucket URL is denied.

## Conclusion

By following these steps, you can securely serve a static website using AWS CloudFront and a private S3 bucket, ensuring that your content is protected while being efficiently delivered to users.
