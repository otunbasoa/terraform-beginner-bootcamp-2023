# Terraform Beginner Bootcamp 2023 - Week 1

## Root Module structure

Our root module structure is as follows:

```
PROJECT_ROOT
│
├── main.tf                 # everything else.
├── variables.tf            # stores the structure of input variables
├── terraform.tfvars        # the data of variables we want to load into our terraform project
├── providers.tf            # defined required providers and their configuration
├── outputs.tf              # stores our outputs
└── README.md               # required for root modules
```

[Standard Module Structure](https://developer.hashicorp.com/terraform/language/modules/develop/structure)

## Terraform and Input Variables

### Terraform Cloud Variables

In terraform we can set two kind of variables:
- Enviroment Variables - those you would set in your bash terminal eg. AWS credentials
- Terraform Variables - those that you would normally set in your tfvars file

We can set Terraform Cloud variables to be sensitive so they are not shown visibliy in the UI.

### Loading Terraform Input Variables

[Terraform Input Variables](https://developer.hashicorp.com/terraform/language/values/variables)


### var flag
We can use the `-var` flag to set an input variable or override a variable in the tfvars file eg. `terraform -var user_ud="my-user_id"`

### var-file flag

the "var-file" flag is used to specify an external variable file that contains input variable values for your Terraform configuration. This flag allows you to keep your variable values separate from your main Terraform configuration files, which can be helpful for maintaining a clean and organized project structure. It's a way to provide variable values without modifying the core configuration files. e.g `terraform apply -var-file=variables.tfvars
`

### terraform.tvfars

This is the default file to load in terraform variables in blunk

### auto.tfvars

 the `auto.tfvars` file is a special file that is automatically loaded to provide default values for input variables in your configuration. This file is useful for simplifying the process of providing values for variables without needing to specify them every time you run Terraform commands like `terraform apply` or `terraform plan`.

 ### order of terraform variables

  the order of variable declarations can be important when you have variables with dependencies or when you want to ensure that certain variables are defined before others. The order in which variables are declared in your Terraform configuration files doesn't affect their behavior, but it can impact readability and maintainability.

  ### Moved state files from terraform cloud to local

  Moving state files from Terraform Cloud (or Terraform Enterprise) to a local environment involves exporting or retrieving the state file from the remote backend (Terraform Cloud) and then configuring your local environment to use that state file for future Terraform operations. 