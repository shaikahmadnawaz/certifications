# AWS Hands-On Labs (Free Tier)

## What is This File? & Why It Matters

Reading about AWS gets you **recognition**. Doing the labs gets you **recall**. Cloud Practitioner exam questions feel much easier after 3-4 hours in the console because you've actually seen the menus, the naming, and the workflow.

All labs below use **AWS Free Tier** and should cost $0 if you follow the cleanup steps.

---

## Before You Start

1. Create an AWS account at https://aws.amazon.com (requires credit card)
2. **Immediately**:
   - Enable MFA on root user
   - Set up AWS Budgets with a $5 alert
   - Create an IAM user for daily use (see Lab 1)
3. Use region **`us-east-1`** (N. Virginia) unless a lab says otherwise — more services, cheaper, more Free Tier

### Free Tier Safety Rules

- Always **stop or terminate** resources when done
- Never leave instances, NAT Gateways, or Elastic IPs running idle (they cost money)
- Check [AWS Free Tier details](https://aws.amazon.com/free/) for exact limits
- Set a Budget alert at $1 to catch mistakes early

---

## Lab 1: IAM Foundation (30 min)

**Goal:** Create an admin IAM user, enable MFA, stop using root.

### Steps

1. Log in as root user
2. Go to **IAM** console
3. Create a user group: `Admins`
4. Attach policy: `AdministratorAccess`
5. Create user: `yourname-admin`, add to `Admins` group
6. Enable console access, set password
7. Enable MFA on the new user (use Google Authenticator, Authy, or hardware key)
8. Log out of root, log in as the IAM user
9. From now on: **never use root for daily work**

### What You Learn

- IAM users vs root
- Groups as permission containers
- MFA configuration
- Console URL format: `https://<account-id>.signin.aws.amazon.com/console`

### Cleanup

Keep this user — you'll use it for all other labs.

---

## Lab 2: S3 Static Website (20 min)

**Goal:** Host a static HTML page from S3.

### Steps

1. Go to **S3** console
2. Create a bucket: `<yourname>-static-<random-digits>` (must be globally unique)
3. Uncheck "Block all public access" (confirm)
4. Upload an `index.html` file with any content (e.g., `<h1>Hello from S3</h1>`)
5. **Properties** → **Static website hosting** → Enable → index document: `index.html`
6. **Permissions** → add bucket policy:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [{
       "Sid": "PublicRead",
       "Effect": "Allow",
       "Principal": "*",
       "Action": "s3:GetObject",
       "Resource": "arn:aws:s3:::<your-bucket>/*"
     }]
   }
   ```
7. Open the endpoint URL (shown in static hosting settings)

### What You Learn

- S3 bucket + object model
- Bucket policies (resource-based policies)
- Block Public Access settings
- Static website hosting
- Public read vs private

### Cleanup

- Delete all objects in bucket
- Delete bucket

---

## Lab 3: Launch and Terminate an EC2 (20 min)

**Goal:** Launch a t2.micro, SSH in, terminate.

### Steps

1. Go to **EC2** console → Launch Instance
2. Name: `lab-ec2`
3. AMI: Amazon Linux 2023 (Free Tier eligible)
4. Instance type: **t2.micro** or **t3.micro**
5. Key pair: create new (download `.pem`)
6. Network settings: allow SSH from your IP
7. Launch
8. Connect via EC2 Instance Connect (browser) OR SSH:
   ```bash
   chmod 400 ~/Downloads/lab-key.pem
   ssh -i ~/Downloads/lab-key.pem ec2-user@<public-ip>
   ```
9. Run:
   ```bash
   uname -a
   curl http://169.254.169.254/latest/meta-data/instance-id
   ```

### What You Learn

- EC2 launch wizard
- AMIs and instance types
- Security Groups (inbound rules)
- Key pairs for SSH
- EC2 metadata service

### Cleanup

- **Terminate** the instance (not just stop — stopped instances may still incur EBS cost)

---

## Lab 4: IAM Role for EC2 → S3 (30 min)

**Goal:** Give an EC2 instance read access to S3 via an IAM role.

### Steps

1. Create an S3 bucket: `<yourname>-role-test`
2. Upload a small file
3. Go to **IAM** → Roles → Create Role
4. Trusted entity: **EC2**
5. Attach policy: `AmazonS3ReadOnlyAccess`
6. Name: `EC2-S3-Read-Role`
7. Launch an EC2 instance (Lab 3) and attach this role (Advanced → IAM instance profile)
8. SSH in, run:
   ```bash
   aws s3 ls
   aws s3 cp s3://<bucket>/<file> /tmp/
   ```
9. No credentials needed — role provides temporary creds via EC2 metadata

### What You Learn

- IAM roles vs users
- Trust policies vs permission policies
- Temporary credentials via STS
- Why roles > access keys on EC2

### Cleanup

- Terminate EC2
- Delete S3 bucket and objects
- Delete IAM role

---

## Lab 5: VPC with Public & Private Subnets (45 min)

**Goal:** Build a custom VPC with one public and one private subnet.

### Steps

1. Go to **VPC** → Create VPC
2. Choose "VPC and more" wizard
3. Name: `lab-vpc`, CIDR: `10.0.0.0/16`
4. 1 AZ, 1 public subnet, 1 private subnet
5. NAT Gateway: **None** (costs money; skip for lab)
6. VPC endpoints: None
7. Review and create

### Explore

- Route tables for public vs private
- Internet Gateway attached
- Security Groups default behavior
- Launch an EC2 in the public subnet → it gets a public IP
- Launch an EC2 in the private subnet → no public IP

### What You Learn

- VPC CIDR blocks
- Public vs private subnet via route tables
- Internet Gateway vs NAT Gateway
- Subnet-to-AZ mapping

### Cleanup

- Terminate all EC2s
- Delete VPC (it cascades and removes subnets, IGW, route tables)

---

## Lab 6: RDS MySQL (Free Tier) (30 min)

**Goal:** Launch a Free Tier RDS database.

### Steps

1. Go to **RDS** → Create database
2. Easy create, MySQL, **Free tier** template
3. DB instance identifier: `lab-db`
4. Master username/password: save them
5. Default VPC is fine
6. **Public access: No** (security best practice; for lab testing from console it's fine)
7. Create
8. Once available, note the endpoint

### Connect (from an EC2 in same VPC)

```bash
sudo yum install mariadb105 -y
mysql -h <endpoint> -u admin -p
```

### What You Learn

- RDS create flow
- Free Tier: db.t3.micro or db.t2.micro, 20 GB storage
- Multi-AZ option (paid)
- DB subnet groups
- RDS security group

### Cleanup

- **Delete database** (uncheck "final snapshot" for lab use)

---

## Lab 7: Lambda Function (20 min)

**Goal:** Deploy a Lambda function triggered by API Gateway.

### Steps

1. Go to **Lambda** → Create function
2. Author from scratch, runtime: Python 3.12
3. Function name: `hello-lambda`
4. Code:
   ```python
   def lambda_handler(event, context):
       return {
           'statusCode': 200,
           'body': 'Hello from Lambda'
       }
   ```
5. Deploy
6. Add trigger: **API Gateway** → REST API → Open
7. Copy the generated API Gateway URL, open in browser

### What You Learn

- Lambda function lifecycle
- Lambda runtime environments
- Event-driven architecture
- API Gateway + Lambda integration
- Free Tier: 1M requests/month

### Cleanup

- Delete API Gateway REST API
- Delete Lambda function

---

## Lab 8: CloudWatch Alarm + Budget (15 min)

**Goal:** Set up a billing alarm + AWS Budget.

### Steps

#### Part A: Billing Alarm (CloudWatch)

1. Go to **Billing** → Preferences → Enable "Receive Billing Alerts"
2. Go to **CloudWatch** → switch region to `us-east-1` (required for billing)
3. Alarms → Billing → Create alarm
4. Threshold: $5 (or $1 for paranoia)
5. Add email notification (SNS topic)
6. Confirm the email subscription

#### Part B: AWS Budget

1. Go to **Billing** → Budgets → Create budget
2. Template: "Zero spend budget" or "Monthly cost budget"
3. Set threshold (e.g., $5)
4. Add email recipient

### What You Learn

- CloudWatch alarms vs Budgets
- SNS topic and subscription confirmation
- Why billing alarms live in us-east-1 only

### Cleanup

Keep these — they protect you from surprise charges.

---

## Lab 9: CloudTrail + Config (20 min)

**Goal:** See your own API activity and config history.

### Steps

#### CloudTrail

1. Go to **CloudTrail** → Event history
2. Filter by event name: `RunInstances` (or any action you did)
3. See the user, IP, time, and full JSON event

#### Config

1. Go to **AWS Config** → Set up Config
2. Enable default settings (1-click)
3. View resource inventory
4. Review compliance dashboard

### What You Learn

- CloudTrail event history (last 90 days free)
- Trail = persistent CloudTrail logs to S3
- Config resource inventory
- Config rules (e.g., "s3-bucket-public-read-prohibited")

### Cleanup

- Optional: turn off Config recording to stop charges
- Delete any S3 buckets created by CloudTrail/Config

---

## Lab 10: Multi-AZ Pattern (45 min)

**Goal:** Deploy a simple web app across 2 AZs behind an ELB.

### Steps

1. Launch 2 EC2 instances in different AZs (each in public subnet)
2. On each, install httpd:
   ```bash
   sudo yum install httpd -y
   sudo systemctl start httpd
   echo "<h1>$(hostname -f)</h1>" | sudo tee /var/www/html/index.html
   ```
3. Open port 80 in security group
4. Go to **EC2** → Load Balancers → Create Application Load Balancer
5. Internet-facing, 2 AZs, register both instances
6. Access the ALB DNS name, refresh multiple times — you see both instances respond

### What You Learn

- Multi-AZ for high availability
- Application Load Balancer
- Target groups and health checks
- Why Multi-AZ > single instance

### Cleanup

- Delete ALB (ALB has hourly cost)
- Terminate EC2 instances
- Delete target group

---

## Exam-Specific Quick Drills

After completing the labs, answer these **without looking**:

1. What is the difference between an IAM user and an IAM role?
2. What happens when you stop vs terminate an EC2?
3. Why do you need a NAT Gateway for private subnets?
4. What's the difference between Security Group and NACL?
5. Where does billing alarm get configured?
6. What is the Free Tier limit for Lambda requests?
7. Why is it better to attach a role to EC2 than to put access keys on the instance?
8. What happens to an EBS volume when the EC2 is terminated?

---

## Total Lab Cost Estimate

If you follow cleanup steps:
- All labs combined: **$0 – $2**
- Biggest risks: forgetting to terminate EC2, leaving NAT Gateway or ALB running

---

## Recommended Lab Order & Schedule

| Day | Lab |
|-----|-----|
| Day 1 | Labs 1, 2 (IAM + S3) |
| Day 2 | Lab 3 (EC2) |
| Day 3 | Lab 4 (IAM role for EC2) |
| Day 4 | Lab 5 (VPC) |
| Day 5 | Lab 6 (RDS) |
| Day 6 | Lab 7 (Lambda) |
| Day 7 | Lab 8 (Budgets + alarms) |
| Day 8 | Lab 9 (CloudTrail + Config) |
| Day 9 | Lab 10 (Multi-AZ + ALB) |

Spend 30-45 min per day in the console. By Day 9 you'll recognize almost every service name and screen on the real exam.
