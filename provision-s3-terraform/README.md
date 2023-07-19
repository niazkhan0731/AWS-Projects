# Povisioning AWS S3 With Terraform
In this project, I will be provisioning an S3 instance inside AWS using Terraform for the first time. Terraform is a powerful Infrastructure as Code tool that facilitates the management of cloud infrastructure through a declarative approach. By defining the desired state of resources in a Terraform configuration file, users can efficiently provision and manage complex infrastructure setups across multiple cloud providers.

The benefits of using Terraform for Infrastructure as Code are manifold. They include:

<b>Consistency and Reproducibility:</b> With Terraform, infrastructure setups are defined as code, ensuring consistency across environments and making it easy to recreate the same infrastructure as needed. This reduces the risk of errors and discrepancies between development, staging, and production environments.

<b>Version Control:</b> Terraform configurations can be versioned using tools like Git, enabling teams to collaborate efficiently and track changes over time. This also facilitates rollback to previous configurations if needed.

<b>Infrastructure Reusability:</b> Terraform supports the use of modules, allowing users to encapsulate and reuse infrastructure components. This promotes best practices, standardization, and saves time by leveraging pre-built modules.

<b>Automated Provisioning:</b> Terraform automatically handles the provisioning and dependency management of resources. It detects changes in the desired state and applies only the necessary modifications, ensuring that the infrastructure stays up to date with minimal manual intervention.

<b>Multi-Cloud and Hybrid Cloud Support:</b> Terraform is cloud-agnostic, meaning it can manage infrastructure on various cloud platforms, as well as on-premises resources, making it suitable for multi-cloud and hybrid cloud deployments.

<b>Scalability and Flexibility:</b> As infrastructure requirements change, Terraform allows easy scaling and modification of resources. This adaptability is crucial for dynamic and growing applications.

<b>Dependency Management:</b> Terraform automatically handles the dependencies between resources, ensuring that resources are provisioned in the correct order, avoiding potential errors due to incomplete setups.

<b>State Management:</b> Terraform keeps track of the infrastructure's current state, storing it locally or remotely. This state allows Terraform to determine what changes are required for the infrastructure to match the desired state.
## Step 1: Create the terraform configuration file
I first went to https://registry.terraform.io/providers/hashicorp/aws/latest/docs to first grab the configuration code. This website is a ideal place to visit for all terraform configuration needs. Then I created a file called <b>main.tf</b> on <a href="https://code.visualstudio.com/"> Visual Studio Code</a>. You can also use any other code editor you are familiar with to create this file. This created a executable file that we will use later to create the S3 bucket using Terraform. You can see the script file on my repository and copy it if you are following along. 

## Step 2: Installing Terraform on AWS CloudShell
You have a few options when it comes to running Terraform. You can download Terraform to your computer and connect it to your AWS account. However, for this project I installed Terraform on AWS CloudShell. To accomplish this first I went to https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli. Then went to the <b>Linux</b> tab then clicked on <b>Amazon Linux</b> tab and followed the steps shown here:

<p align="center"><img width="694" alt="1" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/b9b713b5-1f52-4318-bc69-b6fcdaaf9b3f"></p>

## Step 3: Upload the main.tf file you created to AWS CloudShell
Now that we have Terraform installed on our CloudShell let's upload the <b>main.tf</b> file into our CloudShell:

<img width="1449" alt="2" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/2fcba2cb-0cd8-4524-9bed-3e8def0202e8">

## Step 4:Executing the main.tf file using Terraform

The first command we will execute on the CloudShell is <b>terraform init</b>. This command will download the provider files needed to connect Terraform to AWS.

The second command we will execute on the CloudShell is <b>terraform plan</b>. This command will provide you a brakdown of what Terraform will be doing during the provisioning process.

The last command we will execute  on the CloudShell is <b>terraform apply<b>. This command will tell Terraform to run the plan.

And there you can see below if we go back to our <b>AWS Management Console</b> you can see Terraform has provisioned an S3 bucket for us automatically! This method is super useful if you are tasked to provision multiple S3 buckets at once, you can use Terraform to automate the process.





