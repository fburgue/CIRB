VCLOUD Terraform Repository
==================
## Installing the Terraform on Local Windows
### Install Chocolatey
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
### Install Terraform
```
$ choco install terraform
```

#### Install azure cli
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
- Restart powershell and CMD Cli
- Install Git https://git-scm.com/


### CMD:
```
az login
```

### POWERSHELL:
```
cd c:\learn-terraform-azure
terraform init
terraform validate
terraform plan
terraform apply
--> yes
```

```
terraform show
terraform state list
```


### Sources

The official Terraform provider for [VMware vCloud Director](https://www.vmware.com/products/vcloud-director.html)

- Documentation of the latest binary release available at https://www.terraform.io/docs/providers/vcd/index.html
- This project is using [go-vcloud-director](https://github.com/vmware/go-vcloud-director) Golang SDK for making API calls to vCD
- Join through [VMware {code}](https://code.vmware.com/) to [![Chat](https://img.shields.io/badge/chat-on%20slack-brightgreen.svg)](https://vmwarecode.slack.com/messages/CBBBXVB16) in #vcd-terraform-dev channel 


**Note.** This repository is made to support IaC for the Cloud Teams (Private or Public).

```
$ cd ~/mydir
$ git clone https://github.com/terraform-providers/terraform-provider-vcd.git
$ cd terraform-provider-vcd/
$ make build
```

### Installing the built provider

For a more thorough test using the Terraform client, you may want to transfer the plugin in the Terraform directory. A `make` command can do this for you:

```sh
$ make install
```

This command will build the plugin and transfer it to `$HOME/.terraform.d/plugins`, with a name that includes the version (as taken from the `./VERSION` file).

### Using the new plugin

Once you have installed the plugin as mentioned above, you can simply create a new `config.tf` as defined in [the manual](https://www.terraform.io/docs/providers/vcd/index.html) and run 

```sh
$ terraform init
$ terraform plan
$ terraform apply
```
