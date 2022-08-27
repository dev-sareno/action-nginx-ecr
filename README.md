# action-nginx-ecr
Github action that will push image to AWS private ECR using Github's OpenID Connect to authenticate AWS.

## Requirements
1. AWS Private Elastic Container Registry (ECR)
1. AWS IAM Role that is use for OpenID Connect
1. AWS IAM Policy that has necessary permission to ECR
1. AWS IAM Identity Provider for Github OpenID Connect

## Notes
1. You may need to use AWS CLI to get the ECR ARN

## Sequence
1. Authenticate Github to AWS using OpenID Connect (no IAM user needed!).
    * AWS' official Github Action for the authentication [https://github.com/aws-actions/configure-aws-credentials](https://github.com/aws-actions/configure-aws-credentials)
    * Complete instruction [https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services)
1. Login to AWS Elastic Container Registry
    * AWS' official Github Action for the ECR login [https://github.com/aws-actions/amazon-ecr-login](https://github.com/aws-actions/amazon-ecr-login) 
1. Build and push image to AWS ECR
