# identity and access management (iam)

----
- [group](#group)
    * [create a group](#create-a-group)
    * [attach an AWS Managed Administrator policy to a group](#attach-an-aws-managed-administrator-policy-to-a-group)
    * [list attached group policies of a group](#list-attached-group-policies-of-a-group)
    * [list the members of group](#list-the-members-of-group)
- [user](#user)
    * [list iam users](#list-iam-users)
    * [create a user](#create-a-user)
    * [add user to a group](#add-user-to-a-group)
    * [attach an AWS Managed IAMReadOnlyAccess policy to a user](#attach-an-aws-managed-iamreadonlyaccess-policy-to-a-user)
- [access keys](#access-keys)
    * [inactive an access key id of a user](#inactive-an-access-key-id-of-a-user)
    * [list access keys](#list-access-keys)
- [resources](#resources)
- [terms](#terms)
----

## group
### create a group
```shell
aws iam create-group --group-name <YOUR_FRIENDLY_GROUP_NAME>
```

### attach an AWS Managed Administrator policy to a group
```shell
aws iam attach-group-policy --group-name <YOUR_FRIENDLY_GROUP_NAME> --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

### list attached group policies of a group
```shell
aws iam list-attached-group-policies --group-name <YOUR_FRIENDLY_GROUP_NAME>
```

### list the members of group
```shell
aws iam get-group --group-name <YOUR_FRIENDLY_GROUP_NAME>
```

## user
### list iam users
```shell
aws iam list-users
```

### create a user
```shell
aws iam create-user --user-name <YOUR_FRIENDLY_USER_NAME>
```

### add user to a group
```shell
aws iam add-user-to-group --group-name <YOUR_FRIENDLY_GROUP_NAME> --user-name <YOUR_FRIENDLY_USER_NAME>
```

### attach an AWS Managed IAMReadOnlyAccess policy to a user
```shell
aws iam attach-user-policy --user-name <YOUR_FRIENDLY_USER_NAME> --policy-arn arn:aws:iam::aws:policy/IAMReadOnlyAccess
```

## access keys

### inactive an access key id of a user
```shell
aws iam update-access-key --user-name <YOUR_FRIENDLY_USER_NAME> --status Inactive --access-key-id <ACCESS_KEY_ID>
```

### list access keys
```shell
aws iam list-access-keys --user-name <YOUR_FRIENDLY_USER_NAME>
```

## resources
- [best practices for managing aws access keys](https://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html)

## terms

- aws managed policy: a policy managed by AWS
- access keys: access key id + secret access key, used for aws api calls