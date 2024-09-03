# terraform

 Terraform is an open-source infrastructure as code (IaC) tool developed by HashiCorp. It allows you to define and provision infrastructure using a declarative configuration language.

 ->  Infrastructure is described in configuration files using HashiCorp Configuration Language (HCL) or JSON. These files are typically stored with a .tf extension.

 -> It helps to automate infrastructure provisioning using reusable, shareable, human-readable configuration files. The tool can automate infrastructure provisioning in both on-premises and cloud environments.

**Advantages:**

1. **Track your infrastructure**

Terraform generates a plan and prompts you for your approval before modifying your infrastructure. It also keeps track of your real infrastructure in a state file(terraform.tfstate), which acts as a source of truth for your environment. Terraform uses the state file to determine the changes to make to your infrastructure so that it will match your configuration.

2. **Automate changes**
Terraform configuration files are declarative, meaning that they describe the end state of your infrastructure. You do not need to write step-by-step instructions to create resources because Terraform handles the underlying logic. Terraform builds a resource graph to determine resource dependencies and creates or modifies non-dependent resources in parallel. This allows Terraform to provision resources efficiently.

** Terraform modules**

Terraform modules are small, reusable Terraform configurations for multiple infrastructure resources that are used together. Terraform modules are useful because they allow complex resources to be automated with reusable, configurable constructs. Writing even a very simple Terraform file results in a module. A module can call other modules—called child modules—which can make assembling configuration faster and more concise. Modules can also be called multiple times, either within the same configuration or in separate configurations.

**How terraform Works:**

The core Terraform workflow consists of three stages:

**Write**: You define resources, which may be across multiple cloud providers and services. For example, you might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.

**Plan:** Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration.

**Apply:** On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies. For example, if you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.


**Terragrunt:**


->  Terragrunt is a thin wrapper around Terraform designed to manage multiple Terraform configurations and modules more easily, especially for complex setups.

-> It works on DRY(do not repeat yourself) principle which helps avoid duplication by allowing you to define common configurations in a single place and reuse them across multiple Terraform configurations.

Steps to be followed to use terragrunt:

1. Go to the project directory.

2. go to the Environments folder and choose the environment in which you want to run terragrunt.
for example, cd Environments/Dev command to move to the desired environment to run terragrunt on.

3. run command terragrunt init to initialize the terragrunt and terragrunt plan to see the infrastructure changes.

4. Once the changes have been reviewed, Run terragrunt Apply to apply the infrastructure changes. 
