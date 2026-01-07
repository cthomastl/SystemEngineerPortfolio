
Cloud-Native Systems Engineer Portfolio
Architecture: S3 + CloudFront + Route 53 + ACM
Project Overview
This repository contains the source code and infrastructure configuration for my professional portfolio website. The project demonstrates a secure, high-availability, and low-cost cloud architecture designed to serve static content globally with sub-second latency.

The site is hosted at https://cthomas.cloud (and subdomains such as resume.cthomas.cloud).

Technical Architecture
The deployment follows AWS best practices for static web hosting and edge delivery:

1. Storage & Origin
Amazon S3: Acts as the origin server, hosting the static HTML, CSS, and asset files.

Origin Access Control (OAC): Configured to restrict bucket access exclusively to CloudFront, ensuring the S3 bucket remains private and shielded from direct public access.

2. Edge Delivery & Security
Amazon CloudFront: Serves as the Content Delivery Network (CDN) to cache content at edge locations worldwide.

AWS Certificate Manager (ACM): Provides a free, auto-renewing SSL/TLS certificate for cthomas.cloud, enabling end-to-end encryption via HTTPS.

Security Headers: Configured to enforce secure communication and prevent common web vulnerabilities.

3. DNS & Identity
Amazon Route 53: Manages public DNS records, utilizing Alias records to map the custom domain to the CloudFront distribution.

Hybrid Integration: While the site is public, it serves as a gateway to my broader lab environment, including my Oakmont Chemical internal intranet and Entra ID hybrid identity demonstrations.

Technical Stack
Frontend: HTML5, TailwindCSS, JavaScript

Infrastructure: AWS (S3, CloudFront, Route 53, ACM)

Governance: IAM Policies, S3 Bucket Policies

CI/CD: Manual deployment (Optional: Github Actions for automated S3 sync)

Infrastructure as Code (Conceptual)
The networking and compute components of my broader lab environment are managed via Terraform. Below is a high-level representation of the resource logic used to support my cloud presence:

Terraform

# Example logic for DNS Alias to CloudFront
resource "azurerm_resource_group" "rg" {
  name     = "vm-rg"
  location = "East US"
}
# (Referencing the cross-cloud infrastructure skills demonstrated in my IaC Lab)
Key Features
Global Content Delivery: Sub-second load times via CloudFront edge caching.

Automated SSL/TLS: Full HTTPS enforcement through ACM.

Cost Efficiency: Leverages the AWS Free Tier, resulting in an operational cost of ~$0.51/month (Route 53 hosted zone fee).

Responsive Design: Mobile-first architecture built with TailwindCSS.

Skills Demonstrated
Cloud Architecture: Designing multi-tier, highly available systems.

Web Security: Implementing SSL/TLS certificates and private origin access.

DNS Management: Configuring public hosted zones and CNAME/Alias records.

Tier II Troubleshooting: Resolving complex DNS resolution and CloudFront propagation issues (e.g., DNS_PROBE_STARTED).
