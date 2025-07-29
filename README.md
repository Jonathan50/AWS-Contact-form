# Serverless Contact Form (AWS)

### Team Members
- Jonathan Bernard  
- Ashan Viville 
- Avi Patel
---

## Project Overview

This project implements a fully serverless contact form using **AWS services**: Amazon S3, API Gateway, Lambda, and DynamoDB. The form allows users to submit their name, email, and message, which are processed by a Lambda function and stored in a DynamoDB table with timestamps for tracking submission time.

---

## Live Demo
👉 [Access the Hosted Contact Form Here](https://jonathan-bernard-s3-demo.s3.us-east-2.amazonaws.com/contact.html)

---

## Architecture

**Workflow:**
1. **Frontend (S3):** A static HTML form is hosted on Amazon S3 with public access enabled for demo purposes.  
2. **API Gateway:** The form sends a POST request to an API Gateway endpoint.  
3. **AWS Lambda:** API Gateway triggers a Lambda function that validates input and stores the data in DynamoDB.  
4. **DynamoDB:** A NoSQL database stores all submissions with unique IDs and timestamps.

---

### Architecture Diagram
*(Located in `architecture/architecture-diagram.png`)*  

---

## Features
- Fully serverless architecture (no backend servers required)  
- Stores submissions in DynamoDB with timestamps  
- Scalable, cost-effective (AWS free tier eligible)  
- Simple deployment using AWS Console  

---

## Technologies Used
- **Amazon S3** – Static website hosting  
- **Amazon API Gateway** – API endpoint for form submissions  
- **AWS Lambda** – Serverless backend logic (Python 3.12)  
- **Amazon DynamoDB** – Storage of form submissions  
- **HTML5, CSS3, JavaScript** – Frontend form  

---

## Setup Instructions

### 1. Frontend (S3 Hosting)
- Upload `contact.html` to your S3 bucket.
- Enable static website hosting in bucket properties.
- Make the file public for testing (or configure via CloudFront for secure hosting).

### 2. Backend (API Gateway + Lambda + DynamoDB)
- Create a DynamoDB table named `ContactFormSubmissions` with `id` as the primary key.
- Create a Lambda function and paste the provided code (`lambda_function.py`).
- Attach IAM permissions for DynamoDB read/write.
- Set up an API Gateway POST endpoint and integrate it with Lambda.
- Enable CORS in API Gateway.

### 3. Connect Frontend to Backend
- Update the fetch URL in `contact.html` to point to your API Gateway Invoke URL.

### 4. Test
- Open the hosted contact form link.
- Submit test data and verify storage in DynamoDB.

---

## Future Enhancements
- Add **email notifications** via Amazon SES.
- Create an **admin dashboard** to view submissions.
- Implement **form validation and spam protection**.
- Add **analytics** (e.g., submission frequency reporting).

---

## Documentation
Detailed documents are provided in the `/docs` folder:
- **Contact Form Documentation.docx**
- **Project Design System.docx**
- **Project Proposal.docx**

---

## License
This project is for academic purposes as part of a Master’s program and is not licensed for commercial use without permission from the team.
