# 🚀 Ansible AWS EC2 Multi-Instance Deployment with Nginx

This project uses **Ansible** to automate the creation of multiple **EC2 instances** on AWS, installs **Nginx**, and deploys a custom `index.html` page to each instance.

---

## 📁 Project Structure

```
Ansible-Aws/
├── create_ec2.yml
├── files
│   └── index.html
├── install_nginx.yml
└── 📄 inventory.ini
```


---

## ✅ Features

- Launches 2 or more EC2 instances
- Installs and starts Nginx
- Replaces default web page with custom HTML
- Dynamically adds new instances to the Ansible inventory

---

## 🔧 Requirements

### 🖥️ Local Machine (Control Node)
Install the following:

```bash
sudo apt update
sudo apt install ansible python3-pip -y
pip3 install boto3 botocore
ansible-galaxy collection install amazon.aws

🔑 AWS Credentials

Set credentials using aws configure or environment variables:

export AWS_ACCESS_KEY_ID=your_access_key
export AWS_SECRET_ACCESS_KEY=your_secret_key
export AWS_DEFAULT_REGION=us-east-1

☁️ AWS Configuration

    ✅ A public subnet ID (replace in create_ec2.yml)

    ✅ A Security Group allowing:

        Port 22 (SSH) from your IP

        Port 80 (HTTP) from anywhere

    ✅ An IAM user with EC2 permissions

🚀 Usage

    Clone the repo:

git clone https://github.com/<your-username>/Ansible-AWS-Deployment.git
cd Ansible-AWS-Deployment

    Launch EC2 instances:

ansible-playbook create_ec2.yml

    Install Nginx and deploy HTML:

ansible-playbook -i inventory.ini install_nginx.yml

🌐 Access

After deployment, open your browser and enter the public IP of any launched EC2 instance:

http://<instance-public-ip>

You should see your custom HTML page.
