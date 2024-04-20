# AWS Root Domain to Subdomain Redirect using Lambda@Edge

This CloudFormation template automates the process of redirecting requests from a root domain (e.g., `example.com`) to a subdomain (e.g., `www.example.com`) utilizing AWS Lambda@Edge, Amazon Route 53, and Amazon CloudFront.

## Architecture Diagram

![Lambda@Edge Redirection Architecture](Lambda%40Edge-301-https-subdomain-redirect.png)

## Description

The provided CloudFormation stack deploys a serverless architecture to redirect users from a specified root domain to a target subdomain. This implementation is especially beneficial for users aiming to direct traffic from their main website to a blog or other subdomain-based services, achieving this with minimal latency worldwide through CloudFront.

## Key Features

- **Serverless Redirection**: Utilizes Lambda@Edge for efficient, serverless redirection from root domain to subdomain.
- **Global Performance**: Amazon CloudFront distribution ensures low-latency redirects worldwide.
- **SSL/TLS**: Supports HTTPS redirection through an ACM Certificate, enhancing security.
- **Automated DNS Setup**: Optionally creates Route 53 DNS records for seamless integration.

## Architecture Overview

The solution involves the following AWS services:
- **AWS Lambda@Edge**: Inspects incoming requests and performs HTTP 301 redirects to the target subdomain.
- **Amazon CloudFront**: Globally distributed CDN that serves the redirect responses with low latency.
- **Amazon Route 53**: Manages DNS records, directing traffic to the correct CloudFront distribution.
- **AWS Certificate Manager (ACM)**: Manages SSL/TLS certificates for secure redirection over HTTPS.

## Prerequisites

- An owned domain with its DNS managed by Amazon Route 53.
- If performing HTTPS redirects, an ACM Certificate must be available in the `us-east-1` region due to CloudFront requirements.

## Parameters

The template requires the following parameters to be set:

- `SourceDomain`: The root domain from which traffic will be redirected (e.g., `example.com`).
- `DestinationDomain`: The target subdomain to direct traffic to (e.g., `www.example.com`).
- `HostedZoneId`: Route 53 hosted zone ID associated with the `SourceDomain`.
- `CreateDNSRecords`: Option to automatically create Route 53 A and AAAA records (yes/no).
- `ACMCertificateArn`: (Optional) ARN of an existing ACM certificate. A new one will be created if not supplied and `CreateACMCertificate` is set to `yes`.
- `CreateACMCertificate`: Indicates whether a new ACM certificate should be created if `ACMCertificateArn` is not provided (yes/no).

## Deployment Steps

1. Log into the AWS Management Console.
2. Navigate to the CloudFormation service and choose to create a new stack.
3. Upload or copy and paste the template into CloudFormation.
4. Fill in the required parameters when prompted.
5. Launch the stack.

Upon successful deployment, any requests made to your root domain will be redirected to the specified subdomain using the HTTPS protocol.

## Maintenance and Contributions

- To update the redirection logic or configuration, modify the Lambda@Edge function code within the stack and redeploy.
- Contributions and suggestions are welcome. Please fork the repository and submit pull requests with enhancements.

## Contact and Support

For support or to report issues, please open a GitHub issue on the repository page where this CloudFormation template is hosted.

## License

This template is released under the MIT License. See the LICENSE file in the repository for full details.
