# Static-website-hosting
Using s3 buscket to host a static website
This repository contains the steps and configurations used to host a static website using an Amazon S3 bucket. The static website includes HTML, CSS, and JavaScript files, and leverages the capabilities of S3 to serve the site content. This is a very simple project which should take you less than 10 mins to complete.

## Table of Contents

- Introduction
- Prerequisites
- Setup Steps
  - Step 1: Create an S3 Bucket
  - Step 2: Configure Bucket for Static Website Hosting
  - Step 3: Upload Website Files
  - Step 4: Configure Bucket Policy
  - Step 5: Access the Website
- Conclusion


Introduction

This guide demonstrates how to host a static website using Amazon S3. AWS S3 is a scalable object storage service that allows you to store and retrieve any amount of data at any time from anywhere. By configuring an S3 bucket for static website hosting, you can serve your website content directly from the S3 bucket.

Prerequisites

Before you begin, ensure you have the following:

- An AWS account
- Basic knowledge of AWS S3
- Website files (HTML, CSS, JavaScript)


Step 1: Create an S3 Bucket

1. Log in to the AWS Management Console.
2. Navigate to the S3 service.
3. Click on "Create bucket."
4. Enter a unique bucket name and choose a region.
5. Leave the default settings and click "Create bucket."

Step 2: Configure Bucket for Static Website Hosting

1. Click on the newly created bucket.
2. Go to the "Properties" tab.
3. Scroll down to the "Static website hosting" section.
4. Select "Enable" and configure the following:
   - Index document: `index.html`
   - Error document: `error.html` (optional)
5. Click "Save changes."

Step 3: Upload Website Files

1. Go to the "Objects" tab in your S3 bucket.
2. Click on "Upload" and select your website files (HTML, CSS, JavaScript).
3. Click "Upload" to start uploading your files to the S3 bucket.

Step 4: Configure Bucket Policy

1. Navigate to the "Permissions" tab in your S3 bucket.
2. Click on "Bucket Policy" and add the following policy to make the bucket content publicly accessible:


```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

![Image](https://github.com/users/DerrickAbabioAnim/projects/1/assets/160782895/69eb0281-8e18-4941-9226-e5d8c1faae6c)

3. Replace `your-bucket-name` with the name of your S3 bucket.
4. Click "Save changes."

### Step 5: Access the Website

1. Go back to the "Properties" tab.
2. Scroll down to the "Static website hosting" section.
3. Note the "Endpoint" URL provided.
4. Open the endpoint URL in a web browser to view your static website.

Looks like this

http://[bucket name].s3-website.[region].amazonaws.com/

http://derrick-static-website.s3-website.us-east-2.amazonaws.com/


![Image](https://github.com/users/DerrickAbabioAnim/projects/1/assets/160782895/28f16c48-d128-4bf6-927c-bfb9a2ef18e2)


Conclusion

The static website is now hosted using Amazon S3. You can update your website by uploading new files to the S3 bucket, and the changes will be reflected immediately.


Credit: 
Sami Abdul
Mawuli Denteh
