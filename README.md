# terraform-vault-setup

## Description
The Terraform configuration comprises 2 sub-directories: modules and starter.

#### Modules
It contains configuration files for seting up KV-V2 secret engine, Approle auth method, and userpass. 

#### Starter
- root module resides here, plus resource output file. Root module contains setup for ACLs, auth method, and secret engine
- you can select any module by commenting the others for example: If you want a kv and userpass, comment the other modules in the root module

## Requirement
- install vault on your local machine

## Setup
- set up the dev server: `vault server -dev`
- include in the CLI:
    - `export VAULT_ADDR` environment variable
    - `export VAULT_TOKEN` environment variable
- go to setup/:
    - run `terraform init` cmd
    - run `terraform plan` cmd
    - run `terraform apply` cmd
