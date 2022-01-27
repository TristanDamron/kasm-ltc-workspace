# Ansible based template for KASM Ubuntu Focal Images

## Introduction

This repo provides an [Ansible](https://www.ansible.com/) based template for building [Kasm](https://www.kasmweb.com/) workspaces (images) using Ubuntu Focal.  The included Dockerfile is based on the KASM documentaion on [building custom images](https://kasmweb.com/docs/latest/how_to/building_images.html).  

## How to Use this Repo

1. Fork this repo, giving the new repo a descriptive name for the workspace image to be created
1. Edit the `docker-compose.yml` file and update the `image:` entry to reflect the workspace image to be created
1. Add Ansible Galaxy packages to the `requirements.yaml` file as needed for the playbook
1. Add new Ansible plays to the `playbook.yaml` file to implement the workspace
1. Run `docker-compose build` to build the workspace image (see [Issue #1](https://github.com/j-simmons-phd/kasm-core-focal-template/issues/1) if you encounter an error in Step 1/15 for manual steps to correct the issue)

If you encounter Ansible errors, revise the requirements and playbook files as necessary.  Once built, the image can be pushed into the Kasm server per Kasm documentation or it can be run locally on port 6901 by running `docker-compose up`.

When running locally, the workspace can be accessed at https://localhost:6901 with
- **User:** `kasm_user`
- **Passwordd:** `password`