# Amazon S3 Lab

Hands-on practice with core Amazon S3 features using the AWS Console.

## Technologies Used
- Amazon S3
- S3 Static Website Hosting
- S3 Bucket Policy (JSON)
- S3 Cross-Region Replication (CRR)
- S3 Versioning

---

## Steps

### 1. Create S3 Bucket
- Go to **S3** in the AWS Console → click **Create bucket**
- Enter a globally unique **Bucket name** (e.g., `my-lab-bucket-2024`)
- Select an **AWS Region**
- **Block all public access**: leave enabled for now (we'll change later for static website)
- Leave other settings as default → click **Create bucket**

![Create Bucket](screenshots/01.Create_Bucket1.png)
![Create Bucket](screenshots/02.Create_Bucket2.png)
![Create Bucket](screenshots/03.Create_Bucket3.png)
![Create Bucket](screenshots/04.Create_Bucket4.png)

### 2. Upload Object
- Open your bucket → click **Upload**
- Click **Add files** → select a file from your computer (e.g., `index.html`)
- Leave permissions and properties as default
- Click **Upload** → wait for the success message

![Upload](screenshots/05.Upload1.png)
![Upload](screenshots/06.Upload2.png)

### 3. Enable Versioning
- Open your bucket → go to **Properties** tab
- Scroll to **Bucket Versioning** → click **Edit**
- Select **Enable** → click **Save changes**
- Now upload the same file again with different content — S3 will keep both versions
- To view versions: enable **Show versions** toggle in the **Objects** tab

![Versioning](screenshots/07.Versioning1.png)
![Versioning](screenshots/08.Versioning2.png)

### 4. Static Website Hosting
- Go to **Properties** tab → scroll to **Static website hosting** → click **Edit**
- Select **Enable**
- Set **Index document**: `index.html`
- Click **Save changes**
- Go to **Permissions** tab → **Block public access** → **Edit** → uncheck all → **Save**
- Copy the **Bucket website endpoint** URL and open it in a browser

![Static Website](screenshots/09.StaticWeb.png)
![Static Website](screenshots/10.StaticWeb2.png)
![Static Website](screenshots/11.StaticWeb3.png)

### 5. Bucket Policy
- Go to **Permissions** tab → **Bucket Policy** → click **Edit**
- Paste the following policy to allow public read access:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```

- Replace `YOUR-BUCKET-NAME` with your actual bucket name
- Click **Save changes**

![Bucket Policy](screenshots/12.Bucket_Policy1.png)
![Bucket Policy](screenshots/13.Bucket_Policy2.png)
![Bucket Policy](screenshots/14.Bucket_Policy3.png)

### 6. Cross-Region Replication (CRR)
- **Prerequisite**: Create a **destination bucket** in a different region with versioning enabled
- On the **source bucket** → go to **Management** tab → **Replication rules** → **Create replication rule**
- Rule name: e.g., `crr-rule`
- **Status**: Enabled
- **Source**: Apply to all objects
- **Destination**: Choose the destination bucket (different region)
- **IAM Role**: Create a new role or choose an existing one
- Click **Save** — S3 will ask if you want to replicate existing objects (optional)
- Upload a new object to the source bucket and verify it appears in the destination bucket

![Bucket Replication](screenshots/15.Bucket_Replication1.png)
![Bucket Replication](screenshots/16.Bucket_Replication2.png)
![Bucket Replication](screenshots/17.Bucket_Replication3.png)
![Bucket Replication](screenshots/18.Bucket_Replication4.png)
![Bucket Replication](screenshots/19.Bucket_Replication5.png)
![Bucket Replication](screenshots/20.Bucket_Replication6.png)

---

## Key Concepts Learned

| Feature | Description |
|---|---|
| S3 Bucket | Container for storing objects (files) |
| Versioning | Keeps multiple versions of the same object |
| Static Website Hosting | Serve HTML/CSS/JS directly from S3 |
| Bucket Policy | JSON-based access control for the bucket |
| CRR | Automatically replicate objects to another region |

---

## Resources
- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/)
- [S3 Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
- [S3 Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html)
- [S3 Pricing](https://aws.amazon.com/s3/pricing/)
