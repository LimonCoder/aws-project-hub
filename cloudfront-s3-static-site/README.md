# 🚀 AWS CloudFront + S3 (Static Website Hosting)

This guide outlines the steps to host a static website on AWS S3 using CloudFront for improved speed, security, and scalability.

## 🔹 Why Use CloudFront with S3?

- **Reduced Latency**: CloudFront caches your content at global edge locations, minimizing latency for users.
- **Enhanced Security**: CloudFront restricts direct S3 access, keeping your bucket secure.
- **Cost Efficiency**: It lowers data transfer costs by caching content at edge locations.

## 🔹 Steps to Host a Static Website on AWS S3 with CloudFront

### 1️⃣ **Create an S3 Bucket for Static Website Hosting**
   - Go to the **S3** service in the AWS console.
   - Click **Create bucket** and enter a unique name for your bucket (e.g., `my-static-website`).
   - Under **Bucket Settings for Block Public Access**, ensure **Block all public access** is turned off to allow public access to your files.
   - Enable **Static website hosting** under the bucket settings.
     - Set the **Index Document** (e.g., `index.html`) and **Error Document** (e.g., `error.html`).
   - Click **Create Bucket**.

### 2️⃣ **Upload Website Files**
   - Open the bucket you just created.
   - Click **Upload** and add your HTML, CSS, JavaScript, and other website files.
   - Ensure that all files are publicly accessible by setting appropriate permissions.

   ![Uploading Files to S3](/cloudfront-s3-static-site/images/ss-1.jpeg)

### 3️⃣ **Set Up CloudFront to Cache Content**
   - Go to the **CloudFront** service in the AWS console.
   - Click **Create Distribution**.
   - Under **Web** delivery, choose your S3 bucket as the origin.
   - Enable **Caching** for better performance.
   - Set **Viewer Protocol Policy** to **Redirect HTTP to HTTPS** for secure connections.

   ![CloudFront Setup](path/to/your/screenshot3.png)

### 4️⃣ **Link CloudFront with AWS Certificate Manager for SSL**
   - Go to **AWS Certificate Manager (ACM)**.
   - Request a new SSL certificate for your domain (e.g., `www.mysite.com`).
   - After validation, go back to your **CloudFront** distribution settings and associate the SSL certificate with the distribution.
   - Ensure that **SSL/TLS Protocols** are set to the latest (e.g., TLSv1.2 or higher).

   ![SSL Setup in CloudFront](path/to/your/screenshot4.png)

### 5️⃣ **Test Your Website**
   - Once the CloudFront distribution is deployed (it may take a few minutes), access your website via the CloudFront URL.
   - You should see your static website, now fast and secure!

   ![Testing Website](path/to/your/screenshot5.png)

## 🔹 Key Learnings

- CloudFront handled all requests smoothly, caching content at edge locations for faster load times.
- You can add **custom domains** and **SSL certificates** for a more professional setup, using Route 53 for DNS management.

## 🔹 Conclusion

Hosting your static website with **AWS S3** and **CloudFront** provides significant performance improvements, enhanced security, and lower data transfer costs. It’s a scalable solution ideal for personal or business websites.

---

### 🔖 Tags:
- AWS
- CloudFront
- S3
- Static Website Hosting
- CDN
- DevOps
- Cloud Computing
