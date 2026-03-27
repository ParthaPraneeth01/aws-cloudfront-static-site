# 🚀 AWS CloudFront + S3 Static Website (Production Setup)

## 🌐 Live Demo

👉 https://d1p2cy658iuykh.cloudfront.net

---

## 📌 Overview

This project demonstrates a **secure and scalable static website deployment** using AWS.

The architecture ensures:

* Private storage (S3 not publicly accessible)
* Secure delivery via CloudFront CDN
* Low latency global performance
* Proper DevOps deployment workflow

---

## 🧠 Architecture

```text
User → CloudFront (CDN) → Private S3 Bucket → IAM Policies
```

---

## ⚙️ Tech Stack

* AWS S3 (Private Storage)
* AWS CloudFront (CDN)
* Origin Access Control (OAC)
* IAM (Access Management)
* GitHub (Code Hosting)

---

## 🔐 Security Implementation

* S3 bucket configured as **private**
* Public access completely blocked
* CloudFront allowed via OAC only
* Direct S3 access returns **403 Forbidden**
* HTTPS enforced using CloudFront

---

## 🚀 Deployment Steps

### 1. Create S3 Bucket

* Block all public access
* Upload website files (`index.html`)

### 2. Configure CloudFront

* Connect S3 as origin
* Enable private access (OAC)
* Set default root object:

  ```
  index.html
  ```

### 3. Access Website

* Use CloudFront distribution URL

---

## 🔄 Update Workflow (DevOps)

```text
Edit → Upload → Invalidate Cache → Live
```

### Steps:

1. Update `index.html`
2. Upload to S3 (overwrite)
3. Go to CloudFront → Invalidations
4. Create:

   ```
   /*
   ```

---

## 📸 Screenshots

### S3 Bucket

![S3](screenshots/s3-bucket.png)

### File Uploaded

![Upload](screenshots/upload.png)

### CloudFront Distribution

![CloudFront](screenshots/cloudfront.png)

### Live Website

![Live](screenshots/live.png)

---

## 💡 Key Learnings

* CDN caching and invalidation
* Secure architecture using private storage
* Difference between public vs private access
* Real-world deployment flow
* Cloud-based hosting fundamentals

---

## ⚠️ Common Issues

### Access Denied

* Fix: Set default root object → `index.html`

### Changes not visible

* Fix: Create CloudFront invalidation (`/*`)

---

## 🎯 Project Highlights

* Production-style architecture (not basic hosting)
* Secure by design (no public S3 exposure)
* Uses CDN for performance optimization
* Demonstrates DevOps deployment workflow

---

## 👨‍💻 Author

**P. Partha Praneeth Reddy**
##
DevOps Enthusiast
