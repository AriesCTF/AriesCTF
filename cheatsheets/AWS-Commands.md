# 🧠 AWS CLI Cheatsheet

## ⚙️ General Setup & Configuration

| # | Command | Description |
|--|---------|-------------|
| 1 | `aws configure` | Set up credentials and default region |
| 2 | `aws configure list` | View current configuration |
| 3 | `aws configure get region` | Get configured region |
| 4 | `aws configure set region eu-west-1` | Set default region |
| 5 | `aws sts get-caller-identity` | Show current identity |

## 🗂️ S3 (Simple Storage Service)

| # | Command | Description |
|--|---------|-------------|
| 1 | `aws s3 ls` | List all buckets |
| 2 | `aws s3 ls s3://bucket-name` | List contents of a bucket |
| 3 | `aws s3 mb s3://bucket-name` | Make a new bucket |
| 4 | `aws s3 rb s3://bucket-name` | Remove empty bucket |
| 5 | `aws s3 cp file.txt s3://bucket-name/` | Upload file |
| 6 | `aws s3 cp s3://bucket/file.txt .` | Download file |
| 7 | `aws s3 sync ./localdir s3://bucket/` | Sync local to bucket |
| 8 | `aws s3 sync s3://bucket/ ./localdir` | Sync bucket to local |
| 9 | `aws s3 rm s3://bucket/file.txt` | Delete object |
| 10 | `aws s3 presign s3://bucket/file.txt` | Generate pre-signed URL |

## 🖥️ EC2 (Elastic Compute Cloud)

| # | Command | Description |
|--|---------|-------------|
| 1 | `aws ec2 describe-instances` | List EC2 instances |
| 2 | `aws ec2 run-instances --image-id ami-123 --count 1 --instance-type t2.micro --key-name MyKey --security-group-ids sg-123 --subnet-id subnet-123` | Launch instance |
| 3 | `aws ec2 terminate-instances --instance-ids i-123` | Terminate instance |
| 4 | `aws ec2 start-instances --instance-ids i-123` | Start instance |
| 5 | `aws ec2 stop-instances --instance-ids i-123` | Stop instance |
| 6 | `aws ec2 describe-volumes` | List EBS volumes |
| 7 | `aws ec2 create-key-pair --key-name MyKeyPair` | Create key pair |
| 8 | `aws ec2 describe-key-pairs` | List key pairs |
| 9 | `aws ec2 create-security-group --group-name MySG --description "My SG"` | Create security group |
| 10 | `aws ec2 authorize-security-group-ingress --group-id sg-123 --protocol tcp --port 22 --cidr 0.0.0.0/0` | Add inbound rule |

## 🔐 IAM (Identity & Access Management)

| # | Command | Description |
|--|---------|-------------|
| 1 | `aws iam list-users` | List IAM users |
| 2 | `aws iam create-user --user-name Bob` | Create user |
| 3 | `aws iam delete-user --user-name Bob` | Delete user |
| 4 | `aws iam attach-user-policy --user-name Bob --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess` | Attach policy to user |
| 5 | `aws iam list-groups` | List groups |
| 6 | `aws iam create-group --group-name MyGroup` | Create group |
| 7 | `aws iam add-user-to-group --user-name Bob --group-name MyGroup` | Add user to group |
| 8 | `aws iam list-policies` | List policies |
| 9 | `aws iam get-policy --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess` | Get policy details |
| 10 | `aws iam create-role --role-name MyRole --assume-role-policy-document file://trust-policy.json` | Create role |
