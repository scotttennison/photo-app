# CS385 Photo Gallery - Cloud-Based Web Application

A full-stack cloud application built with AWS services that allows users to sign up, authenticate, and upload photos to the cloud.

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![Cognito](https://img.shields.io/badge/AWS-Cognito-red)
![S3](https://img.shields.io/badge/AWS-S3-green)
![Amplify](https://img.shields.io/badge/AWS-Amplify-purple)

## 🌐 Live Demo

**Live Application:** [Add your Amplify URL here]

**GitHub Repository:** <https://github.com/scotttennison/photo-app>

---

## 📋 Project Overview

This project demonstrates cloud-based web application development using Amazon Web Services (AWS). Users can create accounts, verify their email, securely sign in, and upload photos that are stored in the cloud. The application implements role-based access control and demonstrates key cloud architecture concepts including authentication, authorization, and scalable storage.

**Built for:** CS385 Cloud-Based Web Application Assignment

---

## Architecture

``` text
User Browser
    ↓
AWS Amplify (Hosting)
    ↓
Amazon Cognito (Authentication)
    ↓
Identity Pool (AWS Credentials)
    ↓
Amazon S3 (Photo Storage)
```

---

## 🛠️ Technologies & AWS Services Used

### **Core AWS Services:**

- **Amazon Cognito User Pools** - User authentication and management
- **Amazon Cognito Identity Pools** - Temporary AWS credentials for authenticated users
- **Amazon S3** - Scalable object storage for photos
- **AWS Amplify** - Web application hosting and deployment
- **AWS IAM** - Role-based access control and permissions

### **Frontend:**

- HTML5
- CSS3
- JavaScript (ES6+)
- AWS SDK for JavaScript

---

## ✨ Features

### **User Authentication:**

- ✅ User sign-up with email verification
- ✅ Secure login with password requirements
- ✅ Email verification with 6-digit codes
- ✅ Session management
- ✅ Secure sign-out

### **Photo Management:**

- ✅ Upload photos (up to 5MB)
- ✅ View all uploaded photos in a responsive grid
- ✅ Automatic file naming with timestamps
- ✅ Public photo URLs for sharing

### **Cloud Access Management:**

- ✅ Role-based access control (RBAC)
- ✅ Temporary AWS credentials via Identity Pool
- ✅ Secure S3 bucket policies
- ✅ IAM role permissions for S3 access

### **Security Features:**

- ✅ Password validation (8+ characters, mixed case, numbers, symbols)
- ✅ Email format validation
- ✅ File type validation (images only)
- ✅ File size limits
- ✅ Secure authentication tokens

---

## 📊 AWS Configuration

### **Cognito User Pool:**

- **User Pool ID:** `us-east-1_U16muhJGM`
- **Sign-in:** Email
- **MFA:** Disabled (for development)
- **Email verification:** Required

### **App Client:**

- **Client ID:** `3f0o98tpo7dkfu18e1i1fjl6bc`
- **Type:** Public client (SPA)
- **Authentication flows:** USER_PASSWORD_AUTH, USER_SRP_AUTH

### **Identity Pool:**

- **Identity Pool ID:** `us-east-1:67681cae-7c98-4549-a056-e2e83745303f`
- **Authentication provider:** Cognito User Pool
- **IAM Role:** CognitoIdentityPool_CS385PhotoAppAuth_Role

### **S3 Bucket:**

- **Bucket Name:** `cs385-photo-app-tennison-2026`
- **Region:** US East (N. Virginia) - `us-east-1`
- **Public Access:** Enabled for GetObject via bucket policy
- **CORS:** Configured for web uploads

---

## 🚀 Setup Instructions

### **Prerequisites:**

- AWS Account (Free Tier eligible)
- Modern web browser
- Text editor (VS Code recommended)

### **Local Development:**

1. **Clone the repository:**

   ```bash
   
   git clone https://github.com/scotttennison/photo-app.git
   cd photo-app
   ```

2. **Open `index.html` in a browser:**
   - Option A: Double-click the file
   - Option B: Use a local server:

     ```bash
     npx http-server -p 8080

     ```

     Then visit: `http://localhost:8080`

3. **Test the application:**
   - Sign up with your email
   - Check email for verification code
   - Verify your account
   - Sign in
   - Upload a photo

### **AWS Setup (if recreating from scratch):**

Full setup instructions are available in the project documentation, including:

- Creating a Cognito User Pool
- Configuring an Identity Pool
- Setting up an S3 bucket with proper permissions
- Deploying to AWS Amplify

---

## 📸 Screenshots

### Sign Up & Authentication

![Sign Up Page](screenshots/signup.png)
*User registration with email and password*

### Photo Upload Interface

![Upload Interface](screenshots/upload.png)
*Simple interface for uploading photos*

### Photo Gallery

![Photo Gallery](screenshots/gallery.png)
*Responsive grid displaying uploaded photos*

### AWS Cognito User Pool

![Cognito Console](screenshots/cognito.png)
*User management in AWS Console*

### S3 Bucket

![S3 Console](screenshots/s3.png)
*Photo storage in Amazon S3*

---

## 🔐 Security Considerations

- **Passwords:** Minimum 8 characters with complexity requirements
- **Email Verification:** Required before account activation
- **S3 Access:** Controlled via IAM roles and bucket policies
- **Client Type:** Public client (no client secret in browser)
- **Credentials:** Temporary AWS credentials via Identity Pool
- **HTTPS:** All communication encrypted via AWS services

---

## 📈 Scalability

This application is built on AWS services that automatically scale:

### **Amazon S3:**

- Unlimited storage capacity
- 99.999999999% (11 9's) durability
- Handles millions of concurrent requests

### **Amazon Cognito:**

- Scales to millions of users
- Automatic failover and replication
- No infrastructure management required

### **AWS Amplify:**

- Global CDN (CloudFront) for fast content delivery
- Auto-scaling based on traffic
- 99.95% uptime SLA

---

## 🎓 Learning Outcomes

This project demonstrates proficiency in:

- ✅ Cloud architecture design
- ✅ AWS service integration
- ✅ Authentication and authorization
- ✅ Identity and access management (IAM)
- ✅ Serverless application development
- ✅ RESTful API integration
- ✅ Cloud storage management
- ✅ Security best practices

---

## 🐛 Troubleshooting

### Common Issues

## "User is not confirmed"

- Verify your email using the 6-digit code sent to your inbox

## "Upload failed: Access Denied"

- Check S3 bucket policy allows public read
- Verify IAM role has S3 permissions

## "Missing credentials"

- Ensure Identity Pool is configured
- Check that User Pool is added as authentication provider

## Photos not displaying

- Verify S3 bucket name in code matches actual bucket
- Check CORS configuration on S3 bucket

---

## 📚 Additional Resources

- [AWS Cognito Documentation](https://docs.aws.amazon.com/cognito/)
- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
- [AWS Amplify Documentation](https://docs.aws.amazon.com/amplify/)
- [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

---

## 📝 License

This project is for educational purposes as part of CS385 coursework.

---

## 👤 Author

## Scott Tennison

- GitHub: [@scotttennison](https://github.com/scotttennison)
- Project: CS385 Cloud-Based Web Application

---

## 🙏 Acknowledgments

- Course: CS385 - Cloud Computing
- AWS Free Tier for providing cloud resources
- Amazon Web Services documentation and tutorials

---

**⭐ If you found this project helpful, please consider giving it a star!**
