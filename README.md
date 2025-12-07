# Stay Positive – AWS S3 Static Website

This project is a simple static website hosted on **Amazon S3**, created as part of an exercise to deploy an HTML page to AWS cloud storage and serve it publicly via the S3 static website hosting feature.

---

## 🌐 Live Website
You can view the deployed website here:

➡️ **http://aws-positivitywiths3.s3-website.eu-north-1.amazonaws.com/**

---

## 📄 Project Description

The website displays a motivational message using a basic HTML page.  
It demonstrates:

- Using an S3 bucket to host static content  
- Enabling S3 website hosting  
- Setting the correct bucket policy for public access  
- Uploading an HTML `index.html` file  
- Accessing the site via the S3 *website endpoint* (important!)

---

## 📁 Project Structure


### **index.html**
A minimal page that displays this message:

> **“The mind believes as it's told; Keep it positive.”**

---

## 🛠 Technologies Used

- **HTML**
- **Amazon Web Services (AWS)**
  - S3 Bucket  
  - Static Website Hosting  

---

## 🚀 Deployment Guide (How This Was Hosted)

Below are the steps followed to deploy the site:

### 1. Create an S3 bucket
- Bucket name: `aws-positivitywiths3`
- Region: `eu-north-1`
- Disable **Block Public Access**

### 2. Upload `index.html` to the bucket root.

### 3. Set the correct metadata
Ensure the file has:


### 4. Enable Static Website Hosting
Under **Properties → Static website hosting**:
- Set *Index document*: `index.html`
- Copy the **website endpoint** (NOT the object URL)

### 5. Add a public bucket policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::aws-positivitywiths3/*"
    }
  ]
}
http://aws-positivitywiths3.s3-website.eu-north-1.amazonaws.com/
