# README for Terraform Project

This README provides an overview of the Terraform configuration you have in this project. It describes the AWS resources being created and how to set up your environment. 

## Terraform Configuration

This Terraform project is designed to provision AWS resources using the `aws` provider. It creates the following AWS resources:

1. An EC2 instance named "rajendra" with the following specifications:
   - Instance Type: `t2.micro`
   - Amazon Machine Image (AMI): Make sure to change the AMI ID as per your requirements.
   - Subnet ID: Change the Subnet ID to the desired subnet.

2. An S3 bucket named "s3-demo-xyz". You should change the bucket name to a unique name if necessary.

3. An Amazon DynamoDB table named "terraform-lock" with the following attributes:
   - Table Name: "terraform-lock"
   - Billing Mode: "PAY_PER_REQUEST"
   - Hash Key: "LockID" (String type)

## Configuration Files

The Terraform configuration is defined in a `.tf` file, and the `backend` configuration is stored in the `backend.tf` file. The structure of the files is as follows:

- `main.tf`: Contains the AWS resource definitions for the EC2 instance, S3 bucket, and DynamoDB table.
- `backend.tf`: Defines the Terraform backend configuration for state management in an S3 bucket and uses DynamoDB for state locking.

## Prerequisites

Before you apply this Terraform configuration, ensure you have the following prerequisites set up:

1. **Terraform Installation**: Make sure Terraform is installed on your local machine. You can download it from [Terraform's official website](https://www.terraform.io/downloads.html).

2. **AWS Credentials**: Configure your AWS credentials on your local machine. You can do this by setting up the AWS Access Key ID and Secret Access Key as environment variables or using AWS CLI configurations.

3. **IAM Permissions**: Ensure that the AWS credentials you're using have the necessary permissions to create and manage the specified AWS resources.

## Usage

1. Clone this repository to your local machine.

2. Navigate to the project directory containing the `.tf` files.

3. Initialize your Terraform working directory by running the following command:

   ```
   terraform init
   ```

4. Review and update the Terraform configuration files as needed, especially the AMI, subnet, and S3 bucket names.

5. Apply the Terraform configuration to create the specified resources:

   ```
   terraform apply
   ```

   You will be prompted to confirm the resource creation. Type "yes" to proceed.

## Cleaning Up

To destroy the AWS resources created by this Terraform configuration, use the following command:

```
terraform destroy
```

You will be prompted to confirm the resource deletion. Type "yes" to proceed.

## Important Notes

- Make sure to review and customize the Terraform configuration according to your specific requirements before applying it.

- Always handle AWS credentials and sensitive information securely and follow best practices for managing infrastructure as code.

- This README serves as a basic guide to get you started with the Terraform project. For more advanced usage and further details, refer to the official Terraform documentation: [Terraform Documentation](https://www.terraform.io/docs/index.html).

Feel free to reach out if you have any questions or need further assistance with this Terraform project.
