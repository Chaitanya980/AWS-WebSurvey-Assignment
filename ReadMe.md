
---

# AWS-WebSurvey-Assignment

This repository contains the files and instructions , which includes a class homepage, a student survey form, and an error page. The assignment is hosted on AWS S3 (Part 1) and AWS EC2 (Part 2).

## Assignment Overview

The assignment consists of the following components:

- **index.html**: The class homepage , featuring a picture, a brief description of the class, and a navigation link to the Student Survey Form. The survey form is hosted on an Amazon EC2 instance.
- **survey.html**: A student survey form designed to meet all assignment requirements, hosted on an Amazon EC2 instance.
- **error.html**: An error page displayed when the main page is unavailable.
- **images/**: A folder containing images used in the assignment.
- **bootstrap.min.css** and **bootstrap.min.js**: Bootstrap files for styling and functionality.
- **style.css** and **survey.css**: Custom styling sheets for the three pages.
- **sample_output**: A sample output file for reference.
- **README.md**: This file, providing an overview and instructions.

## How to Access the Assignment

### Part 1: Class Homepage (AWS S3)
- **URL**: [http://cchaudha-swe645-assignment1.s3-website-us-east-1.amazonaws.com](http://cchaudha-swe645-assignment1.s3-website-us-east-1.amazonaws.com)
- **Description**: The class homepage, error page, and associated CSS/media files are hosted in an AWS S3 bucket. Use the link above to view the pages.
- **Navigation**: The header section of the homepage includes a link to the Student Survey Form (Part 2).

#### Steps to Host on AWS S3
1. Created an AWS Free Tier account and set up an S3 bucket.
2. Disabled "Block Public Access" to allow public access.
3. Enabled static website hosting under bucket properties.
4. Configured permissions by adding a bucket policy to allow public access.
5. Uploaded all assignment files (HTML, CSS, images, etc.) to the bucket.
6. Tested the S3 URL to confirm functionality.

### Part 2: Student Survey Form (AWS EC2)
- **URL**: [http://ec2-18-204-213-120.compute-1.amazonaws.com](http://ec2-18-204-213-120.compute-1.amazonaws.com)
- **Description**: The student survey form is hosted on a web server running on an Amazon EC2 instance.

#### Steps to Host on AWS EC2
1. Created an EC2 instance, allowing HTTP and HTTPS traffic.
2. Launched the instance and confirmed it passed status checks (2/2 tests).
3. Connected to the instance using EC2 Instance Connect.
4. Executed the following commands in the terminal:
   ```bash
   sudo su -                       # Switch to root
   yum update -y                   # Update packages
   sudo yum install -y httpd       # Install Apache web server
   mkdir swe645-assignment1        # Create directory
   cd swe645-assignment1
   wget <zip-file-link>            # Download zipped code
   unzip <zip-file>                # Unzip the file
   mv * /var/www/html/             # Move files to web server directory
   cd /var/www/html/
   systemctl enable httpd          # Enable httpd service
   systemctl start httpd           # Start the web server
   ```
5. Verified the website functionality using the Public IPv4 address or Public IPv4 DNS.

