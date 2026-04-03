# Lab 1: AWS Elastic Beanstalk

Deploy and manage a web application without worrying about the underlying infrastructure.

## What is Elastic Beanstalk?

AWS Elastic Beanstalk is a PaaS (Platform as a Service) that lets you deploy and scale web applications automatically — handling capacity provisioning, load balancing, auto-scaling, and health monitoring for you.

---

## Steps

### 1. Create the Application
1. Navigate to **Elastic Beanstalk** in the AWS Console.
2. Click **Create application**.
3. Enter an **Application name**.

![Step 1](screenshots/Beanstalk1.png)

### 2. Configure the Platform
4. Under **Platform**, select your runtime (e.g., Node.js, Python, Java).
5. Choose **Platform branch** and **Platform version**.

![Step 2](screenshots/Beanstalk2.png)
![Step 3](screenshots/Beanstalk3.png)

### 3. Upload Application Code
6. Under **Application code**, select **Sample application** or upload your own `.zip`.

![Step 4](screenshots/Beanstalk4.png)

### 4. Configure Environment Options
7. Click **Configure more options** to review environment settings.
8. Under **Capacity**, choose **Single instance** (free tier) or **Load balanced**.
9. Review **Software**, **Instances**, **Security**, and **Network** settings as needed.

![Step 5](screenshots/Beanstalk5.png)
![Step 6](screenshots/Beanstalk6.png)
![Step 7](screenshots/Beanstalk7.png)

### 5. Launch the Environment
10. Click **Create environment** and wait for the environment to launch (~5 minutes).
11. Once status shows **Ok** (green), click the environment **URL** to verify the app is running.

![Step 8](screenshots/Beanstalk8.png)
![Step 9](screenshots/Beanstalk9.png)
![Step 10](screenshots/Beanstalk10.png)

### 6. Add Environment Variables
12. Go to **Configuration** > **Software** and add any environment variables needed.
13. Click **Apply** and wait for the environment to update.

![Step 11](screenshots/Beanstalk11.png)
![Step 12](screenshots/Beanstalk12.png)

### 7. Deploy a New Version
14. Navigate to **Application versions** to see the deployed version.
15. Upload a new application version (`.zip`) under **Application versions** > **Upload**.
16. Select the new version and click **Deploy**.
17. Monitor the **Events** tab to track the deployment progress.
18. Confirm the new version is live by visiting the environment URL again.

![Step 13](screenshots/Beanstalk13.png)
![Step 14](screenshots/Beanstalk14.png)
![Step 15](screenshots/Beanstalk15.png)
![Step 16](screenshots/Beanstalk16.png)
![Step 17](screenshots/Beanstalk17.png)

### 8. Monitor & Clean Up
19. Explore **Monitoring** to view CPU, network, and request metrics.
20. Optionally, **Terminate** the environment to avoid charges.

![Step 18](screenshots/Beanstalk18.png)
![Step 19](screenshots/Beanstalk19.png)
![Step 20](screenshots/Beanstalk20.png)

---

## Key Concepts

| Concept | Description |
|---|---|
| Environment | A version of your app running on AWS resources |
| Platform | The runtime/language your app uses |
| Application Version | A deployable snapshot of your code |
| Configuration | Settings for instances, scaling, software, etc. |

## Key Takeaway

Elastic Beanstalk abstracts away infrastructure management — you focus on code, AWS handles the rest.
