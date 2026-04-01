# AWS RDS Lab

Hands-on practice with Amazon RDS — creating, securing, backing up, and managing a relational database.

## Technologies Used
- Amazon RDS (MySQL / PostgreSQL)
- Amazon DynamoDB
- AWS Security Group
- RDS Snapshots
- AWS Console

---

## Steps

### 1. Create RDS Database
- Go to **RDS** in the AWS Console → click **Create database**
- **Creation method**: Standard create
- **Engine**: MySQL (or PostgreSQL)
- **Template**: Free tier
- **DB instance identifier**: e.g., `my-rds-lab`
- **Master username**: `admin`
- **Master password**: set a strong password and save it
- **Instance type**: `db.t3.micro` (Free Tier eligible)
- **Storage**: 20 GiB (default)
- **Public access**: Yes (for lab purposes — disable in production)
- Click **Create database** and wait for status to become `Available`

![Create Database 1](screenshots/01.Create_Database1.png)
![Create Database 2](screenshots/02.Create_Database2.png)
![Create Database 3](screenshots/03.Create_Database3.png)
![Create Database 4](screenshots/04.Create_Database4.png)
![Create Database 5](screenshots/05.Create_Database5.png)
![Create Database 6](screenshots/06.Create_Database6.png)
![Create Database 7](screenshots/07.Create_Database7.png)
![Create Database 8](screenshots/08.Create_Database8.png)

### 2. Configure Security Group
- Go to your RDS instance → **Connectivity & security** tab
- Click on the **VPC security group** link
- Select the security group → **Inbound rules** → **Edit inbound rules**
- Add a rule:
  - Type: `MySQL/Aurora` (port `3306`) or `PostgreSQL` (port `5432`)
  - Source: `My IP` (or your EC2 instance's Security Group for private access)
- Click **Save rules**

> **Best practice**: Never open database ports to `0.0.0.0/0`. Restrict to known IPs only.

![Database Security Group](screenshots/09.Databse_Security_Group9.png)

### 3. Take a DB Snapshot
- Go to your RDS instance → click **Actions** → **Take snapshot**
- Enter a **Snapshot name** (e.g., `my-rds-lab-snapshot-01`)
- Click **Take snapshot** — wait for status to become `Available`
- Snapshots can be used to restore the database to a previous state

![Take DB Snapshot](screenshots/10.Take_DB_Snapshot.png)

### 4. Create Items in DynamoDB
- Go to **DynamoDB** in the AWS Console → click **Tables** → select your table
- Go to the **Explore table items** tab → click **Create item**
- Switch to **JSON view** or use the **Form view** to fill in attributes:
  - Add **Partition key** value (e.g., `id`: `1`)
  - Click **Add new attribute** to add more fields (e.g., `name`, `email`)
- Click **Create item** → the item will appear in the table
- Repeat to add more items as needed
- Use **Scan** or **Query** to verify the items were created successfully

![Create Items 1](screenshots/11.Create_Items1.png)
![Create Items 2](screenshots/12.Create_Items2.png)
![Create Items 3](screenshots/13.Create_Items3.png)

---

## Key Concepts Learned

| Concept | Description |
|---|---|
| Amazon RDS | Managed relational database — no need to manage OS or DB engine patches |
| Amazon DynamoDB | Fully managed NoSQL database — stores data as items with attributes |
| Partition Key | Unique identifier for each item in a DynamoDB table |
| Security Group | Controls which IPs/services can connect to the database |
| DB Snapshot | Manual point-in-time backup of the database |
| Endpoint | The hostname used to connect to the RDS instance |
| Free Tier | `db.t3.micro` with 20 GiB storage is free for 12 months |

---

## Resources
- [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/)
- [RDS Free Tier](https://aws.amazon.com/rds/free/)
- [RDS Security Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.Security.html)
- [RDS Snapshots](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateSnapshot.html)
