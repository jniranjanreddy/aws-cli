## How to list ec2 instances.
```
aws ec2 describe-instances
root@minikube01 /jnr/terraform/localstack/ec2 (main) # awslocal ec2 describe-instances --filters "Name=instance-type,Values=t2.micro" --query "Reservations[].Instances[].InstanceId"
[
    "i-911e51c3886639674"
]
aws ec2 describe-instances --filters "Name=tag:Name,Values=MyInstance"
aws ec2 describe-instances --filters "Name=image-id,Values=ami-x0123456,ami-y0123456,ami-z0123456"
aws ec2 terminate-instances --instance-ids i-5203422c
```
