# aws-cli
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
