# aws-cli
$ curl https://checkip.amazonaws.com
x.x.x.x

```
$ aws configure set aws_access_key_id default_access_key
$ aws configure set aws_secret_access_key default_secret_key
$ aws configure set default.region us-west-2
$ aws configure set default.ca_bundle /path/to/ca-bundle.pem
$ aws configure set region us-west-1 --profile testing
$ aws configure set profile.testing2.region eu-west-1
$ aws configure set preview.cloudsearch true
```


```

# How to create new key-pair 
aws ec2 create-key-pair --key-name new-key --query 'KeyMaterial' --output text > new-key.pem

#Change the permissions
chmod 400 new-key.pem

[root@minikube01 ~]# aws ec2 describe-key-pairs --key-name new-key
{
    "KeyPairs": [
        {
            "KeyPairId": "key-084c72864c80dbf50",
            "KeyFingerprint": "af:a8:23:e0:96:40:f9:92:70:6b:ca:4f:29:9c:9b:a5:57:c4:8e:5f",
            "KeyName": "new-key",
            "Tags": []
        }
    ]
}

# How To delete Key pair.
aws ec2 delete-key-pair --key-name new-key
```

#How to create Security Groups..
```
aws ec2 create-security-group --group-name my-sg --description "My security group" --vpc-id vpc-1a2b3c4d
```
```
aws iam create-group --group-name MyIamGroup
{
    "Group": {
        "GroupName": "MyIamGroup",
        "CreateDate": "2018-12-14T03:03:52.834Z",
        "GroupId": "AGPAJNUJ2W4IJVEXAMPLE",
        "Arn": "arn:aws:iam::123456789012:group/MyIamGroup",
        "Path": "/"
    }
}
aws iam create-user --user-name MyUser
{
    "User": {
        "UserName": "MyUser",
        "Path": "/",
        "CreateDate": "2018-12-14T03:13:02.581Z",
        "UserId": "AIDAJY2PE5XUZ4EXAMPLE",
        "Arn": "arn:aws:iam::123456789012:user/MyUser"
    }
}

aws iam add-user-to-group --user-name MyUser --group-name MyIamGroup
aws iam get-group --group-name MyIamGroup

root@minikube01 ~ # aws iam create-access-key --user-name serverless-admin
{
    "AccessKey": {
        "UserName": "serverless-admin",
        "AccessKeyId": "AKIATWOLD12345",
        "Status": "Active",
        "SecretAccessKey": "sySLLS7A7SPEDOp7/hGxzH/Td12345",
        "CreateDate": "2023-04-04T21:28:44+00:00"
    }
}



```




