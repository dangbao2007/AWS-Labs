# AWS Lambda Function Lab

Step-by-step guide to creating an AWS Lambda Function.

## Steps

### Step 1 - Access Lambda Console
![Lambda1](screenshot/Lambda1.png)
- Log in to AWS Console
- Search for and select **Lambda** service

### Step 2 - Create a New Function
![Lambda2](screenshot/Lambda2.png)
- Click **Create function**
- Select **Author from scratch**

### Step 3 - Configure Function
![Lambda3](screenshot/Lambda3.png)
- Enter a **Function name**
- Choose a **Runtime** (Python, Node.js, ...)

### Step 4 - Configure IAM Role
![Lambda4](screenshot/Lambda4.png)
- Create or select an **Execution role**
- Click **Create function**

### Step 5 - Write Code
![Lambda5](screenshot/Lambda5.png)
- Write your code in the **Code source** section
- Click **Deploy** to save

### Step 6 - Create Test Event
![Lambda6](screenshot/Lambda6.png)
- Go to **Test** → **Create new event**
- Enter a name and configure the event

### Step 7 - Run Test
![Lambda7](screenshot/Lambda7.png)
- Click **Test** to run the function
- Check the result in **Execution results**

### Step 8 - View Logs
![Lambda8](screenshot/Lambda8.png)
- View logs in **CloudWatch Logs**

### Step 9 - Configure Trigger
![Lambda9](screenshot/Lambda9.png)
- Add a **Trigger** to the function (API Gateway, S3, ...)

### Step 10 - Complete
![Lambda10](screenshot/Lambda10.png)
- Verify and confirm the function is working

## References
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/)
- [AWS Lambda Pricing](https://aws.amazon.com/lambda/pricing/)
