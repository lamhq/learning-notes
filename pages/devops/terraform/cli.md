# CLI Commands

## Get version

```shell
terraform version
```

## Set working directory

You can add `-chdir=<path_to/tf>` flag to commands to specify the working directory:
```shell
terraform -chdir="infra/" apply -var-file="test.tfvars"
```


## Validate Terraform code

Validate the code to look for any errors in syntax, parameters, or attributes within Terraform resources that may prevent it from deploying correctly:
```shell
terraform validate
```

## Preview

Create an execution plan:
```shell
terraform plan
```

Output the destroy plan:
```shell
terraform plan -destroy
```

## Apply changes

```shell
terraform apply
```

No asking:
```shell
terraform apply --auto-approve
```

Apply a specific plan:
```shell
terraform apply <plan_name>
```

Only apply changes to a targeted resource:
```shell
terraform apply -target=<resource_name>
```

Pass a variable via the command line:
```shell
terraform apply -var my_variable=<variable>
```


## Destroy

```shell
terraform destroy
```

```shell
terraform destroy --auto-approve
```

## View outputs

Display all the output variables from your Terraform state:
```shell
terraform output
```

## State

List all the resources being tracked by the Terraform state file:
```shell
terraform state list
```

## Workspace commands

List workspaces:
```shell
terraform workspace list
```

Create a workspace:
```shell
terraform workspace new <WORKSPACE_NAME>
```

Switch workspace:
```shell
terraform workspace select <WORKSPACE_NAME>
```

Delete workspace:
```shell
terraform workspace delete <WORKSPACE_NAME>
```

## List available commands

```shell
terraform
```

## List available options for a sub command

```shell
terraform <sub_command> -h
```


## Upgrade Terraform

First update Homebrew:

```shell
brew update
```

Upgrade Terraform to the latest version:

```shell
brew upgrade hashicorp/tap/terraform
```
