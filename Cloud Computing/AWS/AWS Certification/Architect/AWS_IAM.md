# Identity and access Management

* [Resource](https://www.youtube.com/watch?v=y7-fAT3z8Lo)
* [IAM Best Practices](https://www.youtube.com/watch?v=SGntDzEn30s)

* As default new user when created he/she has no permissions
* Policies are JSON script
* Policies contains
  * Version
  * Statements defines who (Principal) can do what (Action) on what (resource) under what condition (Condition)
* ARN stands for Amazon Resource Name;
* Policy is made up of bunch of statements
* Each Statement is consist of (PARC Model)
1. **P** rincipal (Who)
1. **A** ction (do What)
1. **R** esources (what)
1. **C** onditions (Under what condition)

* Principal is a **User, Role, Group**.

* Sample Policy

```
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Action": "ec2:*",
        "Resource": [
          "arn:aws:ec2:us-west-2:123456789012:customer-gateway/*",
          "arn:aws:ec2:us-west-2:123456789012:dhcp-options/*",
          "arn:aws:ec2:us-west-2::image/*",
          "arn:aws:ec2:us-west-2:123456789012:instance/*",
          "arn:aws:iam::123456789012:instance-profile/*",
          "arn:aws:ec2:us-west-2:123456789012:internet-gateway/*",
          "arn:aws:ec2:us-west-2:123456789012:key-pair/*",
          "arn:aws:ec2:us-west-2:123456789012:network-acl/*",
          "arn:aws:ec2:us-west-2:123456789012:network-interface/*",
          "arn:aws:ec2:us-west-2:123456789012:placement-group/*",
          "arn:aws:ec2:us-west-2:123456789012:route-table/*",
          "arn:aws:ec2:us-west-2:123456789012:security-group/*",
          "arn:aws:ec2:us-west-2::snapshot/*",
          "arn:aws:ec2:us-west-2:123456789012:subnet/*",
          "arn:aws:ec2:us-west-2:123456789012:volume/*",
          "arn:aws:ec2:us-west-2:123456789012:vpc/*",
          "arn:aws:ec2:us-west-2:123456789012:vpc-peering-connection/*"
        ]
      },
      {
        "Effect": "Allow",
        "Action": "s3:*",
        "Resource": "arn:aws:s3:::example_bucket/marketing/*"
      },
      {
        "Effect": "Allow",
        "Action": "s3:ListBucket*",
        "Resource": "arn:aws:s3:::example_bucket",
        "Condition": {"StringLike": {"s3:prefix": "marketing/*"}}
      }
    ]
  }
```
## ARN
Amazon Resource Names (ARNs) uniquely identify AWS resources. We require an ARN when you need to specify a resource unambiguously across all of AWS, such as in IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls.

## ARN Examples
Here are some example ARNs:

  <!-- Elastic Beanstalk application version -->
  arn:aws:elasticbeanstalk:us-east-1:123456789012:environment/My App/MyEnvironment
  <!-- IAM user name -->
  arn:aws:iam::123456789012:user/David
  <!-- Amazon RDS instance used for tagging -->
  arn:aws:rds:eu-west-1:123456789012:db:mysql-db
  <!-- Object in an Amazon S3 bucket -->
  arn:aws:s3:::my_corporate_bucket/exampleobject.png

[See More](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)

# Policy Generator

* You can create policy, (it generated the JSON script)
* you can allow or deny a specific resource
* resource type Also Known as AWS Service
* Action that is allowed
* Add a specific conditions (Specify instance type etc.)

# Policy reviewer

* is a full JSON editor with syntax checker.

# Need to find out

1. Cognito
1. Fedrated Users

# Resources

* [AWS Policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html)
* [JSON Componenets](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#access_policies-json)
