# terraform-vault-setup

## Description
The Terraform configuration comprises 2 sub-directories: modules and setup.

#### modules
It contains configuration files for seting up KV-V2 secret engine, Approle auth method, and Userpass. 

#### setup
- root module resides here, plus resource output file. Root module contains setup for ACLs, auth methods, and secret engine
- in the root module, you can select any module by commenting the others for example: If you want a kv, userpass or approle, comment the other modules in the root module
- comment any output data you don't need in the root module's output.tf

## Requirement
- install vault on your local machine

## Setup
- set up the dev server: `vault server -dev`
- include in the CLI:
    - `export VAULT_ADDR` environment variable
    - `export VAULT_TOKEN` environment variable. If using `approle`, there no need to export the **VAULT_TOKEN** (root roken)
- go to setup/:
    - run `terraform init` cmd
    - run `terraform plan` cmd
    - run `terraform apply` cmd
