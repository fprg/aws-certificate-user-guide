# AWS–Managed Policies<a name="authen-awsmanagedpolicies"></a>

 AWS managed policies are standalone identity–based policies that you can attach to multiple users, groups, and roles in your AWS account\. AWS managed policies are created and managed by AWS\. The following AWS managed policies are available for ACM\. For more information about attaching managed policies to a user, group, or role, see [Working with Managed Policies ](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-using.html) in the [IAM User Guide](http://docs.aws.amazon.com/IAM/latest/UserGuide/)\. 

 To use an AWS managed policy, a user with administrative privileges must attach the policy to a user, role, or group\. For more information about attaching AWS managed policies, see [ Attaching Managed Policies ](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-using.html#attach-managed-policy-console) in the [IAM User Guide](http://docs.aws.amazon.com/IAM/latest/UserGuide/)\. 


+ [AWSCertificateManagerReadOnly](#acm-read-only-managed-policy)
+ [AWSCertificateManagerFullAccess](#acm-full-access-managed-policy)

## AWSCertificateManagerReadOnly<a name="acm-read-only-managed-policy"></a>

This policy provides read–only access to ACM Certificates; it allows users to describe, list, and retrieve ACM Certificates\. 

```
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": [
      "acm:DescribeCertificate",
      "acm:ListCertificates",
      "acm:GetCertificate",
      "acm:ListTagsForCertificate"
    ],
    "Resource": "*"
  }
}
```

To view this AWS managed policy in the console, go to [https://console\.aws\.amazon\.com/iam/home\#policies/arn:aws:iam::aws:policy/AWSCertificateManagerReadOnly](https://console.aws.amazon.com/iam/home#policies/arn:aws:iam::aws:policy/AWSCertificateManagerReadOnly)\. 

## AWSCertificateManagerFullAccess<a name="acm-full-access-managed-policy"></a>

 This policy provides full access to all ACM actions and resources\. 

```
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": ["acm:*"],
    "Resource": "*"
  }]
}
```

To view this AWS managed policy in the console, go to [https://console\.aws\.amazon\.com/iam/home\#policies/arn:aws:iam::aws:policy/AWSCertificateManagerFullAccess](https://console.aws.amazon.com/iam/home#policies/arn:aws:iam::aws:policy/AWSCertificateManagerFullAccess)\. 