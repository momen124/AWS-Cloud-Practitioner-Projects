# Launching EC2 Instances and Managing IAM Permissions

## Objective
Launch two EC2 instances (production and development) and use AWS IAM to manage access for an intern, ensuring they can only interact with the development instance.

## Steps
1. **Launched EC2 Instances**:
   - Created `nextwork-prod-<my-name>` and `nextwork-dev-<my-name>` instances.
   - Used Free Tier eligible AMI and instance type (`t2.micro`).
   - Added tags: `Env: production` and `Env: development`.

2. **Created IAM Policy**:
   - Defined `NextWorkDevEnvironmentPolicy` to allow EC2 actions on `Env: development` resources.
   - Denied tag modification actions.
   - JSON policy:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Action": "ec2:*",
           "Resource": "*",
           "Condition": {
             "StringEquals": {
               "ec2:ResourceTag/Env": "development"
             }
           }
         },
         {
           "Effect": "Allow",
           "Action": "ec2:Describe*",
           "Resource": "*"
         },
         {
           "Effect": "Deny",
           "Action": ["ec2:DeleteTags", "ec2:CreateTags"],
           "Resource": "*"
         }
       ]
     }