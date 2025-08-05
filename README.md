## ⚙️ Step-by-Step Instructions

### 1. Create an S3 Bucket
- Go to AWS Management Console → S3
- Click **Create bucket**
- Choose a **unique name**
- Select your **region**
- Uncheck "Block all public access" ✅
- Enable **static website hosting**

### 2. Configure Bucket for Hosting
- Under **Properties**, enable:
  - Static website hosting
  - Set `index.html` as the entry point
- Under **Permissions**, add a **Bucket Policy**:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
