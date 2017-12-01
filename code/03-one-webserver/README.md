# Terraform Web Server example

This folder contains a web server example of a Terraform file (https://www.terraform.io/).
This Terraform file deploys a single web server in Google Cloud Platform (GCP). The web server returns "Hello, World" for the URL `/` listening on port 8080.

## Requirements

* You must have [Terraform](https://www.terraform.io/) installed on your computer. 
* You must have a [Google Cloud Platform (GCP) account](https://cloud.google.com/).
* You must have downloaded a Google Cloud Platform credentials file.
* You must have enabled the Google Compute Engine API.

This code was written for Terraform 0.10.x.

## Using the code

Two ways in order to configure credentials:

* Configure GOOGLE_APPLICATION_CREDENTIALS environment variable. The variable must contain the path to the credentials file.

```
export GOOGLE_APPLICATION_CREDENTIALS="~/.gcloud/terraform-examples-code.json"
```

* Configure GOOGLE_CREDENTIALS environment variable. The variable must contain the content of the credentials file and not the path to it.

```
export GOOGLE_CREDENTIALS="$(cat ~/.gcloud/terraform-examples-code.json)"
```

Validate the changes:

```
terraform plan
```

Deploy the changes:

```
terraform apply
```

Test the web server. When the `apply` command completes, it will output the public IP address of the web server.

```
curl http://(server_public_ip):8080/
```

Clean up the resources created when you have finished:

```
terraform destroy
```