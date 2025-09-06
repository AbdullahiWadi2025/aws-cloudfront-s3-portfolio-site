# AWS CloudFront + S3 Static Website Hosting

This project showcases how I hosted a **static website** using **Amazon S3** for storage and **Amazon CloudFront** as a Content Delivery Network (CDN).  
It demonstrates **secure, cost-optimized deployment** using AWS Free Tier without purchasing a domain.

---

## 🌐 Project Overview

The goal was to deploy a portfolio website with global availability, caching, and restricted S3 access.  
I faced challenges with CloudFront and S3 static website endpoints, but solved them while learning best practices for AWS deployments.

---

## 🚀 Architecture

- **Amazon S3** – stores the website file (`index.html`).  
- **CloudFront Distribution** – delivers content globally with HTTPS.  
- **Origin Access Control (OAC)** – restricts direct S3 access.  
- **Cost Optimized** – no domain purchased, no SSL certificate requested, AWS Free Tier used.




<img width="1105" height="461" alt="Architecture" src="https://github.com/user-attachments/assets/8eff6898-aa9a-4520-9506-8383b4a86d23" />




## ⚙️ Implementation Steps

### Step 1: Prepare Website Content
Developed a single-page HTML website (`index.html`) with CSS styling and optional JavaScript.  
![Website Content Screenshot](<img width="1270" height="815" alt="Screenshot-website-code" src="https://github.com/user-attachments/assets/44895d3a-bf99-47ed-8246-e00b27eddb2a" />
)

### Step 2: Create S3 Bucket
Created an S3 bucket configured for static website hosting with `index.html` as the root object.  
![S3 Bucket Screenshot](screenshots/step2-s3-bucket.png)

### Step 3: Upload Website Files
Uploaded the website file to the S3 bucket and verified proper organization.  
![Upload Screenshot](screenshots/step3-upload.png)

### Step 4: Set Up CloudFront
Created a CloudFront distribution pointing to the S3 bucket with recommended cache settings.  
![CloudFront Screenshot](screenshots/step4-cloudfront.png)

### Step 5: Set Up Origin Access Control (OAC)
Configured OAC so CloudFront could securely fetch files while blocking direct S3 public access.  
![OAC Screenshot](screenshots/step5-oac.png)

### Step 6: Domain Registration (Optional)
Skipped purchasing a domain to stay cost-efficient; used the default CloudFront URL.  
![Domain Screenshot](screenshots/step6-domain.png)

### Step 7: Provision SSL Certificate (Optional)
Did not request SSL since no custom domain was used.  
![SSL Screenshot](screenshots/step7-ssl.png)

### Step 8: Configure WAF Protection (Optional)
Skipped AWS WAF for cost optimization.  

### Step 9: Set Up DNS Records (Optional)
Skipped since no custom domain; CloudFront URL used for live access.  
![DNS Screenshot](screenshots/step9-dns.png)

---

## 🔧 Challenges & Lessons Learned

- Initially used **S3 Static Website endpoint** → received `403 AccessDenied`.  
- Solution: switched to **regular S3 bucket endpoint** in CloudFront, which solved the issue.  
- Learned best practices for **CloudFront + S3 integration** and troubleshooting AWS access policies.  

---

## 💰 Cost Optimization

- **No domain purchased** – used CloudFront default URL.  
- **No SSL certificate requested** from AWS Certificate Manager.  
- Leveraged **AWS Free Tier** (S3 + CloudFront) for hosting.  

---

## 📸 Screenshots

All related screenshots are in the `/screenshots` folder:  
- S3 Bucket Setup  
- CloudFront Distribution  
- Origin Access Control  
- Website Working via CloudFront  

---

## 🔗 Demo

Website is live on CloudFront:  
[https://d38j2odq9336qj.cloudfront.net](https://d38j2odq9336qj.cloudfront.net)  

