# Terraform Config for Small Infrastructure

This documentation provides an overview of Terraform, its key features, and the basic commands you'll use frequently. It also includes an example configuration and step-by-step instructions for deploying infrastructure with Terraform.

### What is Terraform?

Terraform is an open-source Infrastructure as Code (IaC) tool created by HashiCorp. It allows you to define and manage your infrastructure using a declarative configuration language. Terraform can manage resources across various providers, including AWS, Azure, Google Cloud, and many others.

### Key Features of Terraform:

- **Infrastructure as Code**: Define your infrastructure using code, allowing for version control, peer reviews, and automated testing.
- **Execution Plans**: Preview the changes Terraform will make to your infrastructure before applying them.
- **Resource Graph**: Visualize dependencies between resources and understand the order of operations.
- **Change Automation**: Automate the provisioning and management of your infrastructure.

## Basic Terraform Commands

### 1. `terraform init`

Initializes a new or existing Terraform configuration. This command downloads the necessary provider plugins and sets up the backend configuration.

```sh
terraform init
```

### 2. `terraform plan`

Generates an execution plan showing what actions Terraform will take to achieve the desired state defined in your configuration files. This command does not apply any changes.

```sh
terraform plan
```

### 3. `terraform apply`

Applies the changes required to reach the desired state of the configuration. It will create, update, or delete infrastructure resources as needed.

```sh
terraform apply
```

### 4. `terraform destroy`

Destroys the Terraform-managed infrastructure. This command removes all resources defined in your configuration.

```sh
terraform destroy
```

### 5. `terraform validate`

Validates the syntax and configuration of your Terraform files. This command checks for errors and potential issues in your code.

```sh
terraform validate
```

### 6. `terraform fmt`

Formats the Terraform configuration files to a canonical format and style.

```sh
terraform fmt
```

### 7. `terraform show`

Displays the current state or a plan file.

```sh
terraform show
```

### 8. `terraform output`

Extracts and displays the output values from the state file.

```sh
terraform output
```

## Example Usage

Here is a simple example of a Terraform configuration file (`main.tf`) that creates an AWS EC2 instance:

```sh
provider "aws" {
  region = "us-west-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleInstance"
  }
}
```

To deploy this infrastructure, follow these steps:

1. **Initialize the configuration:**

   ```sh
   terraform init
   ```

2. **Review the execution plan:**

   ```sh
   terraform plan
   ```

3. **Apply the changes:**

   ```sh
   terraform apply
   ```

4. **Destroy the infrastructure when no longer needed:**

   ```sh
   terraform destroy
   ```

## Additional Resources

- [Terraform Documentation](https://www.terraform.io/docs)
- [Terraform Best Practices](https://www.terraform-best-practices.com)
- [HashiCorp Learn](https://learn.hashicorp.com/terraform)
- [Terraform GitHub Repository](https://github.com/hashicorp/terraform)
