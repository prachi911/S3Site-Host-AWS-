AWS S3 Static Website Hosting
📌 Introduction
This project showcases how to deploy and host a static website entirely on Amazon S3.
It involves setting up an S3 bucket, uploading a simple HTML/CSS site, configuring it for static hosting, and controlling access via ACLs and bucket policies.

🛠 Tech & Tools Used
Amazon S3 for storage and hosting

ACLs (Access Control Lists) for fine-grained permission control

Custom error pages for better UX


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/4e9dfb8c-052a-47f4-acc1-962d5e63531f" />


📂 Project Flow
Create an S3 bucket

Upload website files

Enable static hosting

Manage public access

Access via public endpoint

🚀 Step-by-Step Setup
1️⃣ Create an S3 Bucket
Sign in to AWS Management Console → Search for S3.

Click Create bucket.

Choose a globally unique name (e.g., my-static-site-demo).

Select a region close to your audience (e.g., ap-south-1 – Mumbai).

Under Object Ownership, select ACLs enabled for detailed access control.

2️⃣ Upload Your Files
Upload index.html and other assets to the bucket.

Keep the folder structure intact.

You can drag-and-drop or use the Upload button in the S3 console.

3️⃣ Configure for Static Website Hosting
In Properties, scroll to Static website hosting → Enable.

Set:

Index document: index.html

Error document: error.html (optional, for friendly error pages).

4️⃣ Set Permissions via ACL
After uploading, select all files → Actions → Make public using ACL.

This step ensures visitors won’t get a 403 Forbidden error.

5️⃣ Access Your Website
Once configured, AWS provides a public endpoint in this format:

php-template
Copy
Edit
http://<bucket-name>.s3-website-<region>.amazonaws.com
⚙ Troubleshooting
Issue	Possible Cause	Fix
403 Forbidden	Objects are private	Make files public using ACLs
Website not loading	Wrong index document name	Ensure index.html is set correctly
Custom error page not showing	Misconfigured path	Verify file exists and matches error doc setting

🏗 Architecture Overview
css
Copy
Edit
[Local Files] → [AWS S3 Bucket] → [Static Website Hosting] → [Public Endpoint]
S3 Bucket: Stores HTML, CSS, JS, and image files.

Hosting Config: Makes the bucket behave like a website.

ACL & Policies: Control access for public viewing.
