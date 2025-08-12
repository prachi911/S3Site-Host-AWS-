# AWS S3 Static Website Hosting

## Overview
This project demonstrates how to host a simple static website using **Amazon S3**.  
It covers creating an S3 bucket, uploading files, enabling static hosting, setting permissions, and accessing the site via a public URL.

---

## Architecture
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/7cb8f07b-6a11-448e-9667-eee6ccf0c232" />


---

## Features
- Fully hosted static site on Amazon S3.
- Custom error document for better user experience.
- Access control using ACLs and bucket policies.
- Public endpoint accessible from any browser.

---

## Setup and Deployment

### Step 1: Create an S3 Bucket
1. Log in to the **AWS Management Console**.
2. Navigate to **S3**.
3. Click **Create bucket**:
   - Choose a unique name (e.g., `my-demo-static-site`).
   - Select a region close to your target audience (e.g., `ap-south-1` – Mumbai).
4. Under **Object Ownership**, enable **ACLs** for fine-grained permissions.

---

### Step 2: Upload Files
- Upload `index.html` and other assets.
- Preserve folder structure during upload.

---

### Step 3: Enable Static Website Hosting
1. In **Properties**, go to **Static website hosting**.
2. Enable hosting and set:
   - **Index document:** `index.html`
   - **Error document:** `error.html` (optional).

---

### Step 4: Make Files Public Using ACL
1. Select files in the bucket.
2. Go to **Actions → Make public using ACL**.
3. Grants public read access and resolves `403 Forbidden` errors.

---

### Step 5: Access Your Website
Once hosting is enabled, AWS provides a public URL:


---

## Using ACLs
**Access Control Lists (ACLs)** define permissions for individual objects.  
They allow more granular control compared to bucket policies.

**Why ACLs?**
- Object-level permissions.
- Public read access without giving write permissions.
- **HOW DO THEY ACTUALLY WORK ?**
<img width="1043" height="745" alt="image" src="https://github.com/user-attachments/assets/093b8682-3ea6-4e36-bd9c-6f56a8a3ba0f" />

---

## Troubleshooting
| Issue | Cause | Solution |
|-------|-------|----------|
| 403 Forbidden | Files are private | Make public using ACLs |
| Website not loading | Wrong index document name | Ensure `index.html` is set correctly |
| Custom error page not showing | Incorrect file path | Verify error document setting |

---

## Project Summary
- **S3 Bucket** created to store files.
- **Static hosting** enabled.
- **ACLs configured** for public access.
- Website live via AWS endpoint.

