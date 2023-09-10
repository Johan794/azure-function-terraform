# aws lambda function terraform
In this fork you will see how to deploy a lambda function using terraform. <br>

## Configuration 👓

In order to use aws instead of azure you need to folow these steps: 
 - Install , if u dont have it yet,   aws CLI and run 
 ```bash
    aws configure
```
 then provide a new public and secret access key

- Change your provider to aws, and set your region, you can provide that configuration unsing your tfvars.
- Add your iam policy. 

## About the implementation 🎈

In this version, instead of using the file *index.js* a new file was created in order to support de lambda function. This new file was made in python called *lambda_function.py* and it looks like this
 ```python
import os
def lambda_handler(event, context):
    return "{} from Lambda!".format(os.environ['greeting'])
```

where the env varibale greeting, provided by the terraform code, is used for formatting the message.

## Testing terraform commads ⭐️

- *terraform init*

![Terrafor init](screenshots/terraform_init.png)

- *terraform plan*

![plan 1](screenshots/terraform_plann1.png)
![plan 2](screenshots/terraform_plann2.png)

- *terraform apply* 

![apply 1](screenshots/terraform_apply.png)
![apply 2](screenshots/terraform_apply2.png)
![apply 3](screenshots/terraform_apply3.png)

## Check the function running ⛹🏾‍♂️

![function out put](screenshots/exceuted_lambda.png)

![function created in aws](<screenshots/aws_lambda function.png>)



