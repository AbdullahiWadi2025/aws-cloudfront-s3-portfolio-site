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

<img width="1270" height="815" alt="Screenshot-website-code" src="https://github.com/user-attachments/assets/6b39da74-5f85-4d3a-98b7-40c9ed609104" />


### Step 2: Create S3 Bucket
Created an S3 bucket configured for static website hosting with `index.html` as the root object.  

<img width="1114" height="701" alt=" S3 bucket configured for static website" src="https://github.com/user-attachments/assets/9e3f0ec6-e88f-433e-b798-45741a6c5a0e" />


### Step 3: Upload Website Files
Uploaded the website file to the S3 bucket and verified proper organization.  

<img width="829" height="511" alt="Uploaded the website file to the S3 bucket" src="https://github.com/user-attachments/assets/a66eaf67-3c13-456f-b283-f3185de25bad" />



### Step 4: CloudFront Setup & Troubleshooting
- Initially tried **S3 static website hosting**, which caused `403 AccessDenied` errors with CloudFront.  
- **Screenshot 1**: S3 bucket with static website enabled.
- 
  <img width="798" height="684" alt="S3statichost-enable" src="https://github.com/user-attachments/assets/76a9cf69-8958-4c4f-aadb-010058e73919" />
  

- **Solution:** Disabled static website hosting and used the **regular S3 bucket endpoint**, resolving the access issue.  
- **Screenshot 2**: S3 bucket after switching to the regular endpoint.
- 
  <img width="886" height="441" alt="S3staticwebsite-disable" src="https://github.com/user-attachments/assets/0c2a1a7c-0808-474f-bb79-6d6496d79008" />
 

- Created CloudFront distribution pointing to the S3 bucket with recommended cache settings.
- 
  <img width="1114" height="671" alt="Created CloudFront distribution pointing to the S3 bucket" src="https://github.com/user-attachments/assets/b5792249-4bbf-4834-8d7a-b9448f48a459" />


### Step 5: Set Up Origin Access Control (OAC)
Configured OAC so CloudFront could securely fetch files while blocking direct S3 public access.  

<img width="1097" height="696" alt="Set Up Origin Access Control (OAC)" src="https://github.com/user-attachments/assets/41473afb-c8f6-47d3-ad45-bbe693882a00" />


### Step 6: Domain Registration (Optional)
Skipped purchasing a domain to stay cost-efficient; used the default CloudFront URL.  


### Step 7: Provision SSL Certificate (Optional)
Did not request SSL since no custom domain was used.  


### Step 8: Configure WAF Protection (Optional)
Skipped AWS WAF for cost optimization.  

### Step 9: Set Up DNS Records (Optional)
Skipped since no custom domain; CloudFront URL used for live access.  


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


## 🔗 Demo

## Website is Live on CloudFront
<img width="842" height="860" alt="Website-test" src="https://github.com/user-attachments/assets/c262a210-2245-4289-bfb3-1be7ab95dec9" />

