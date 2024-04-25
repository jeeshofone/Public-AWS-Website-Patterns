# Public AWS Website Patterns

Welcome to the Public AWS Website Patterns repository. This collection of CloudFormation templates is designed to provide practical examples and ready-to-deploy resources for setting up web infrastructure using AWS services. It covers a variety of patterns from simple HTTP to HTTPS redirections to complex setups involving Lambda@Edge for dynamic content handling. Each pattern includes detailed explanations, architecture diagrams, and step-by-step deployment guides.

## Companion Blog Post

For a deeper exploration of these patterns and a guide on how to adapt them to your specific needs, please visit our companion blog post at <blog-post-url-here>. The blog post provides additional insights and contextual information, enhancing your understanding and application of the templates provided here.

## Patterns Overview

- **301 HTTPS Subdomain Redirect**: Redirect traffic from one subdomain to another using S3 and CloudFront.
- **Lambda@Edge 301 HTTPS Subdomain Redirect**: Employ Lambda@Edge for subdomain redirection, offering a serverless solution for SEO-friendly URLs.
- **S3+Cloudfront with OAC (Origin Access Control)**: Set up a secure content delivery network with S3 and CloudFront using origin access controls to manage CORS settings and enhance security.
- **S3+Cloudfront with OAI (Origin Access Identity)**: Similar to the OAC example, but uses the CloudFront Origin Access Identity for S3 bucket access.
- **HTTPS Subdomain Redirect**: Redirect from a root domain to a WWW subdomain using CloudFront and Lambda, suitable for platforms that do not support apex domain hosting such as Substack.

## Getting Started

To deploy these patterns, you'll need:
- An AWS account
- Basic understanding of AWS CloudFormation, S3, CloudFront, Route 53, and optional knowledge of Lambda.
- The AWS CLI installed, if you prefer to deploy via command line.

## Guided Deployment

Each directory contains a README.md file with detailed instructions for deployment:
1. Navigate to the desired pattern directory.
2. Follow the instructions in the README.md file to deploy using the AWS Management Console or AWS CLI.

## Contributions

Contributions are welcome! If you have improvements or additional patterns to add, please fork this repository and submit a pull request.

## License

This project is licensed under the terms of the MIT license.

## Support

For questions or support regarding these deployment patterns, please open an issue in this repository. U aim to assist and address any deployments issues or inquiries you may have.

Thank you for visiting the Public AWS Website Patterns repository. I hope these templates help you effectively deploy and manage your AWS-based web infrastructure!