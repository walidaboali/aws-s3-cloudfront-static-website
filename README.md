AWS S3 + CloudFront Static Website Hosting Project

This project demonstrates how to host a secure, globally distributed static website using:

Amazon S3 

Amazon CloudFront (CDN + HTTPS)

Origin Access Control (OAC) for secure S3 access

IAM (bucket policies)

ACM for SSL certificates

-Architecture Overview
User → CloudFront → S3 (private bucket)


S3 stores the website (index.html)

CloudFront serves it globally with caching + HTTPS

OAC allows CloudFront to securely access the private S3 bucket


Architecture Diagram:


🧱 Services Used
Service	Purpose
S3	Stores static website (index.html)
CloudFront	CDN + HTTPS + caching
IAM	Secure bucket permissions
OAC	Allows CloudFront to read from S3

- Step-by-Step Deployment
1️⃣ Create S3 Bucket

Name: wel-cloud-portfolio

Block public access: Enabled

Upload index.html

Enable Static Website Hosting

Index document: index.html

2️⃣ Create CloudFront Origin Access Control (OAC)

Type: S3

Name: wel-cloud-oac

Signing behavior: Sign requests

3️⃣ Create CloudFront Distribution

Origin: S3 bucket

Attach OAC

Update bucket policy automatically

Viewer Protocol Policy: Redirect HTTP to HTTPS

Default root object: index.html

📸 Screenshots

All screenshots are inside the /screenshots folder:

S3 bucket configuration

CloudFront distribution

OAC settings

Working website

🧪 Testing

After CloudFront deploys:

https://<your-distribution-id>.cloudfront.net


You should see your website.

-Skills Demonstrated

AWS cloud fundamentals

Storage & content delivery

IAM security best practices

CloudFront OAC configuration

Static website hosting

CDN deployment

Infrastructure documentation

👤 Author

Walid Aboali
Cloud Security Engineer
