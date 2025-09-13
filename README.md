# Retail Store Local Deployment

## 1. Introduction & Company Background

Welcome to **InnovateMart**, a rapidly growing e-commerce startup recently funded with Series A to scale globally.  
As part of our engineering team, this project—codenamed **Project Bedrock**—aimed to deploy the **Retail Store Sample App** and lay the foundation for cloud infrastructure.  

My role as a Cloud DevOps Engineer was to ensure automation, security, and scalability from day one.

---

## 2. AWS EKS Attempt (Cloud Deployment)

### 2.1 Infrastructure Setup

I initially attempted to deploy the Retail Store Sample App on **AWS EKS** using **Terraform**.

**Resources Attempted:**

- **EKS cluster:** `innovatemart-eks-cluster`  
- **VPC:** `vpc-0f55b75bbc75ed504`  
- **Key pair:** `eks-key` (Fingerprint: `e2:7e:bd:3c:e8:10:c4:96:ff:d5:fe:9d:bd:1b:1c:95`)  

**Terraform Errors Encountered:**

```text
Error: Unsupported argument
  on main.tf line 47, in module "eks":
  47:   node_groups = {
An argument named "node_groups" is not expected here.
This prevented automatic node group creation, resulting in partial cluster readiness.

Partial Success:

Despite the error, Terraform successfully created:

Cluster endpoint: https://1CCFCC1980C8C3A3ACF7EDD022A82820.gr7.us-east-1.eks.amazonaws.com

Cluster name: innovatemart-eks-cluster

VPC: vpc-0f55b75bbc75ed504
http://a7fba4afeafa249c58e90bce64033785-642730164.us-east-1.elb.amazonaws.com/
Confirmed partial functionality before tearing down resources to avoid AWS charges.

3. Challenges & Encounters

Terraform module mismatch blocked node group creation (node_groups → eks_managed_node_groups).

Cluster could not be fully provisioned, preventing complete cloud deployment.

Learned the importance of matching module versions and reviewing provider documentation.

 Instructor’s Guidance

Deploy the application locally using a local Kubernetes cluster (Minikube, Kind, Docker Desktop).

Provide screenshots and video evidence showing the application working.

Include documentation of the local setup and previous AWS attempt.

Current Local Deployment
Local Setup

Application deployed successfully on a local Kubernetes cluster.

All services (catalog, orders, carts, etc.) are running as containers locally.

The application can be accessed via:

http://localhost:8080/

5.2 Evidence of Work

Screenshots:

Located in media/screenshots/ folder, showing running pods, services, and UI.

Demo Videos:

Located in media/videos/ folder:

[Video 1](media/videos/WhatsApp\ Video\ 2025-09-13\ at\ 1.30.36\ PM.mp4)

[Video 2](media/videos/WhatsApp\ Video\ 2025-09-13\ at\ 6.06.23\ PM.mp4)

5.3 Outcome

Fully functional local deployment at http://localhost:8080/.

Meets instructor’s grading requirements with ample evidence.

Historical AWS deployment attempt noted for reference, but ELB URL is no longer active.

6. Features

Fully containerized microservices application.

End-to-end tested in local Kubernetes environment.

Screenshots and demo videos included for validation.

 Installation & Usage
Using Docker
docker-compose up --build

Potential Enhancements / Future Work

While the local deployment is fully functional, there are several opportunities to further improve the project and demonstrate advanced skills:

Full Cloud Deployment

Resolve the Terraform EKS module version issue and deploy the application on AWS EKS with fully provisioned node groups.

Leverage managed AWS services for databases (RDS for MySQL/PostgreSQL, DynamoDB for carts) to make the deployment production-ready.

CI/CD Pipeline Improvements

Automate both infrastructure and application deployment with GitHub Actions or another CI/CD tool.

Include automated tests and security checks in the pipeline.

Scalability & Monitoring

Implement auto-scaling for microservices based on load.

Integrate monitoring and alerting (Prometheus, Grafana, CloudWatch).

Documentation Enhancements

Include step-by-step screenshots or a video tutorial for setting up the local environment.

Add a “Lessons Learned” subsection summarizing challenges faced and key takeaways from both local and cloud deployment attempts.

User Experience Enhancements

Improve front-end UI for a more polished demonstration of the retail store application.

Include sample data seeding scripts for quicker testing and demos.


