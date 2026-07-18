# Yashraj's Cloud Portfolio

> Personal portfolio website hosted on AWS S3 — built as part of the Cloud Engineer Roadmap 2026.

**Live site:** [your-bucket-name.s3-website.ap-south-1.amazonaws.com](http://yash-s3-demo-project-bucket.s3-website.us-east-1.amazonaws.com)

---

## About

A fully static portfolio website showcasing my cloud engineering learning journey, projects, and AWS skills. No frameworks, no build tools — just HTML and CSS, hosted on AWS S3 with static website hosting.

---

## Tech used

- Pure HTML5 & CSS3 — zero dependencies, zero frameworks
- Google Fonts (Syne, Inter, JetBrains Mono)
- Hosted on AWS S3 with static website hosting enabled
- Served via public bucket policy

---

## Projects featured

| Project | Stack | Repo |
|---|---|---|
| System Health Dashboard | Python, Linux, subprocess | [health-dashboard](https://github.com/yashraj-1012/health-dashboard) |
| Server Monitor Tool | Python, Bash, Git | [Server-monitor](https://github.com/yashraj-1012/Server-monitor) |
| Cloud Scripts Collection | Bash, Python, AWS EC2 | [cloud-scripts](https://github.com/yashraj-1012/cloud-scripts) |

---

## How to deploy your own

### 1. Create an S3 bucket

```bash
aws s3 mb s3://your-bucket-name --region ap-south-1
```

### 2. Enable static website hosting

```bash
aws s3 website s3://your-bucket-name \
  --index-document index.html \
  --error-document index.html
```

### 3. Set bucket policy for public read

Create a file called `policy.json`:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

Apply it:

```bash
aws s3api put-bucket-policy \
  --bucket your-bucket-name \
  --policy file://policy.json
```

### 4. Upload the site

```bash
aws s3 cp index.html s3://your-bucket-name/
```

### 5. Access your site

Your site is live at:
```
http://your-bucket-name.s3-website.ap-south-1.amazonaws.com
```

---

## AWS skills demonstrated

By hosting this project I practiced:

- Creating and configuring an S3 bucket
- Enabling static website hosting on S3
- Writing and applying an S3 bucket policy
- Using AWS CLI to upload and manage objects
- Using an IAM role on EC2 to access S3 without hardcoded keys
- Disabling Block Public Access settings safely for a public website

---

## Learning journey

This portfolio is part of my 7-week AWS Cloud Engineer Roadmap:

| Week | Topic | Status |
|---|---|---|
| 1–2 | Linux & Networking | ✅ Done |
| 3 | Python, Bash & Git | ✅ Done |
| 4 | Cloud concepts | ✅ Done |
| 5 | AWS deep dive | 🔄 In progress |
| 6 | Docker, Terraform & CI/CD | ⏳ Upcoming |
| 7 | Kubernetes | ⏳ Upcoming |

---

## Author

**Yashraj** — Aspiring Cloud / DevOps Engineer
📍 India | 🔍 Open to internship opportunities

- GitHub: [github.com/yashraj-1012](https://github.com/yashraj-1012)
- LinkedIn: [linkedin.com/in/yashraj](https://linkedin.com/in/yashraj)
- Email: yashraj@email.com
