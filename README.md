
# Jenkins-on-EC2-with-Terraform

This Terraform project allows you to deploy a Jenkins server on an Amazon EC2 instance with all necessary configurations using Terraform. The EC2 instance is launched in the default VPC and a default subnet if they do not exist. The script installs Jenkins on the instance and exposes it on port 8080 for web access and port 22 for SSH access.

## Prerequisites
Before using this Terraform project, make sure you have the following prerequisites set up:

* An AWS account with appropriate credentials and permissions to create EC2 instances, VPCs, security groups, etc.
* Terraform installed on your local machine. You can download it from the Terraform website and follow the installation instructions for your operating system.
* A valid SSH key pair (`.pem` file) to be used for SSH access to the EC2 instance.

## Usage
* Clone this repository to your local machine.
* Make sure you have your AWS credentials configured properly on your machine. Depending on your setup, you can use environment variables or AWS CLI configuration.
* Navigate to the project directory in your terminal.

### Initialize Terraform

Before applying the Terraform configuration, you need to initialize the Terraform providers and modules used in the project. Run the following command to initialize:

```
terraform init
```

### Adjust Variables (Optional)
If needed, you can modify the provider.tf file to adjust the AWS region or the AWS profile used for authentication.

### Deploy the Jenkins Server
To deploy the Jenkins server, run the following Terraform commands:

```
terraform plan
terraform apply
```

Terraform will show you a summary of the changes it will apply. Review the output and type `yes` when prompted to proceed with the deployment.

The Terraform script will create an EC2 instance, a security group allowing access on ports 8080 (for Jenkins) and 22 (for SSH), and configure Jenkins on the instance.

### Accessing Jenkins
Once the Terraform script has been completed, it will output the URL of the Jenkins server. You can access Jenkins by navigating to the provided URL in your web browser.

Additionally, Terraform will print the initial admin password for Jenkins during the provisioning process. You will need this password to complete the Jenkins setup.

## Clean Up
To clean up and delete all the AWS resources created by this Terraform project, run:
```
terraform destroy
```
Terraform will show you a summary of the resources it will delete. Review the output and type `yes` when prompted to proceed with the deletion.

Please note that this will destroy all resources created by this Terraform configuration, including the EC2 instance and the associated Jenkins server. Make sure to save any important data before running the destroy command.

## Acknowledgments
This project was inspired by the need for a straightforward way to deploy Jenkins on an EC2 instance using Terraform. Feel free to contribute to this repository if you have any suggestions or improvements. Happy automating with Jenkins! 🚀