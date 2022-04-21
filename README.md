# mvp_hello
hello_mvp

Prerequisites

Start by authenticating the SDK to Google Cloud:

# Authenticate to Google Cloud
gcloud auth application-default login

Follow the web flow to obtain the access credentials. By the end of this step, you will be able to execute commands on the SDK similar to a service account.

Create a new project where your Cloud Run service will be deployed. 

gcloud projects create "PROJECT_ID" --name="PROJECT_NAME"

Deploying the infrastructure
At this point, you have all it takes to deploy the infrastructure to Google Cloud using Terraform.

Start by initializing the configuration. Run the following command in your terminal:

# Initialize Terraform configuration
terraform init

Run terraform plan to verify the changes that will be applied:

# Create a .tfvars file with your <PROJECT_ID>

tfvars: project = "PROJECT ID"

# Plan the changes
terraform plan

If everything is correct, you will see that 3 resources will be created and the service URL will be displayed.

Plan: 3 to add, 0 to change, 0 to destroy.

Changes to Outputs:
  + service_url = (known after apply)
Run terraform apply to apply all the changes:

# Apply all the changes
terraform apply
If everything goes well, you will see this at the end of the output:

Apply complete! Resources: 3 added, 0 changed, 0 destroyed.

Outputs:

service_url = https://app-inmmqbfyga-ue.a.run.app/
You can check if the service is running using curl:

curl https://app-inmmqbfyga-ue.a.run.app/

Hello, world!
Version: 1.0.0
Hostname: localhost
