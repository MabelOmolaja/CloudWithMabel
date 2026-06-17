# Hosting a Static Website on Amazon S3 and CloudFront

**Project:** AWS Static Website Hosting with Amazon S3 and CloudFront

**Author:** Mabel Omolaja
**Email:** [maybelomolaja@gmail.com](mailto:maybelomolaja@gmail.com)

---

# Project Overview

In this project, I built and deployed a static website using Amazon S3 and Amazon CloudFront. The goal was to learn how static web hosting works on AWS while improving website performance, security, and global content delivery through CloudFront.

This project provided hands-on experience with cloud storage, content delivery networks (CDNs), website deployment, access management, and troubleshooting common caching issues.

---

# Architecture

**Users → CloudFront → Amazon S3**

CloudFront acts as a Content Delivery Network (CDN), distributing website content from edge locations around the world while retrieving the original files from an Amazon S3 bucket.

<img width="1198" height="1313" alt="architecture diagram" src="https://github.com/user-attachments/assets/60aeb5b4-738c-4f5e-988d-13c6bd73016e" />


---

# AWS Services Used

## Amazon S3

Amazon S3 (Simple Storage Service) was used to store the website files, including HTML, CSS, and image assets.

### Key Benefits

* Highly durable object storage
* Scalable hosting solution
* Cost-effective for static websites
* Easy integration with CloudFront

---

## Amazon CloudFront

CloudFront was used to distribute website content globally and improve website performance.

### Key Benefits

* Low-latency content delivery
* Global edge network
* Reduced load on the S3 bucket
* Content caching for faster access

---

## IAM (Identity and Access Management)

IAM was used to securely manage permissions and access to AWS resources throughout the project.

### Key Benefits

* Secure access control
* Principle of least privilege
* Resource protection

---

# Step 1: Creating the S3 Bucket

## What I Did

I created an Amazon S3 bucket that would serve as the origin storage location for my website files.

## Why This Step Matters

Every static website hosted on AWS needs a location where the website files can be stored. Amazon S3 provides a reliable and scalable solution for hosting these files.

## Key Learning

S3 bucket names must be globally unique across all AWS accounts.

<img width="1280" height="800" alt="Screen Shot 2026-06-10 at 2 50 36 PM" src="https://github.com/user-attachments/assets/996385bb-e2fd-4317-b437-478fda8a35f6" />


---

# Step 2: Uploading Website Files

## What I Did

I uploaded my website files to the S3 bucket.

The files included:

* index.html
* Images
* Supporting website assets

## Why This Step Matters

Without uploading the website files, visitors would have no content to view when accessing the website.

<img width="1040" height="554" alt="Screen Shot 2026-06-11 at 10 31 56 PM" src="https://github.com/user-attachments/assets/e7b32252-4da4-41fc-933f-ea2fead352aa" />

---

# Step 3: Configuring Static Website Hosting

## What I Did

I configured the S3 bucket to support static website hosting.

## Why This Step Matters

Static website hosting allows Amazon S3 to serve web pages directly to users through a website endpoint.

## Key Learning

S3 can host websites without requiring a traditional web server.

<img width="1280" height="627" alt="Screen Shot 2026-06-17 at 9 06 12 AM" src="https://github.com/user-attachments/assets/8d1e345a-8d13-4884-883a-4fca962a040b" />



---

# Step 4: Creating the CloudFront Distribution

## What I Did

I created a CloudFront distribution and connected it to my S3 bucket.

## Why This Step Matters

CloudFront improves performance by caching content at edge locations around the world, reducing the distance between users and website content.

### Benefits of CloudFront

* Faster website loading times
* Improved user experience
* Reduced latency
* Better scalability

<img width="1280" height="627" alt="Screen Shot 2026-06-17 at 9 09 26 AM" src="https://github.com/user-attachments/assets/f81abc04-af68-43fa-82a9-c57eb2113831" />

---

# Step 5: Testing the Website

## What I Did

After deployment, I tested the CloudFront URL to confirm that the website was publicly accessible.

## CloudFront URL

https://d3j3a63lgmom3d.cloudfront.net/

## Result

The website loaded successfully through CloudFront, confirming that the integration between CloudFront and S3 was working correctly.

<img width="886" height="615" alt="cloudwithmabelw-web" src="https://github.com/user-attachments/assets/d8fcaa8a-ddd1-4e37-b433-aa0fda69728e" />/

---

# Challenge Encountered

## The Issue

After updating my website files in Amazon S3, I expected the changes to appear immediately on the website.

However, when I refreshed the CloudFront URL, the old version of the website continued to display.

## Why It Happened

CloudFront caches website content to improve performance. Because the old content was already cached at edge locations, users continued to see the previous version.

## How I Solved It

I created a CloudFront Invalidation to clear the cached content.

### Invalidation Path Used

```
/*
```

This forced CloudFront to retrieve the latest files from the S3 bucket.

## Result

Once the invalidation was completed, the website displayed the updated content correctly.

## Key Learning

Caching improves performance but can sometimes delay content updates. CloudFront invalidations are an important tool for ensuring users receive the latest version of a website.

<img width="1279" height="643" alt="Screen Shot 2026-06-13 at 1 34 36 PM" src="https://github.com/user-attachments/assets/46b6e929-6a8b-4dc8-8a08-1f805afe2283" />


---

# Security Considerations

Throughout the project, IAM permissions were used to securely manage access to AWS resources.

This helped ensure that:

* Only authorised users could modify resources
* Website files remained protected
* AWS best practices were followed

---

# What I Learned

Through this project, I gained practical experience with:

* Amazon S3
* Amazon CloudFront
* Static website hosting
* CDN architecture
* Content caching
* Cache invalidation
* IAM permissions
* Website deployment workflows

I also learned how CloudFront caching works and how to troubleshoot situations where website updates do not immediately appear to users.

---

# Project Outcome

By the end of this project, I successfully deployed a static website using Amazon S3 and CloudFront.

The website is globally accessible, benefits from faster content delivery through CloudFront's edge network, and follows AWS best practices for scalable static website hosting.

---

# Live Website

https://d3j3a63lgmom3d.cloudfront.net/

---

# Author

**Mabel Omolaja**

Aspiring Cloud Engineer | AWS Certified Cloud Practitioner | Building hands-on cloud projects to strengthen real-world AWS skills.
