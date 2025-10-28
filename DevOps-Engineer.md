# DevOps Engineer Technical Challenge

Thank you for your interest in joining our team! We're excited to see your skills in action. This technical challenge is designed to give you an opportunity to showcase your expertise in modern DevOps practices and tooling, reflecting the kind of work we do here. We understand that you might have other commitments, so we kindly ask you to complete this exercise within 5 days.

## Problem

As a rapidly growing DevOps services company, we embrace the latest technologies to build robust, scalable, and automated solutions for our clients. We need you to demonstrate your ability to design and implement a modern, cloud-native deployment workflow.

Your task is to deploy a simple "Hello World" web application (you can choose any programming language you prefer) to a Kubernetes cluster running on [Amazon Web Services (AWS)](https://aws.amazon.com/). The goal is to automate the entire process, from infrastructure provisioning to application deployment, using industry-standard tools and practices.

We expect the solution to leverage:

- **Cloud Provider:** [AWS](https://aws.amazon.com/)
- **Kubernetes Service:** [AWS Elastic Kubernetes Service (EKS)](https://aws.amazon.com/eks/)
- **Infrastructure as Code:** [Terraform](https://www.terraform.io/) (using [community modules](https://github.com/terraform-aws-modules) is encouraged, e.g., for VPC or EKS)
- **Containerization:** [Docker](https://www.docker.com/)
- **Package Management (Optional but Preferred):** [Helm](https://helm.sh/) (using community charts is acceptable)
- **CI/CD:** [GitHub Actions](https://github.com/features/actions)
- **Ingress (Preferred):** [Traefik Proxy](https://traefik.io/traefik/) or alternatively an AWS LoadBalancer Service.

**Note on Costs:** Provisioning an AWS EKS cluster will incur minor costs (likely a few dollars). We understand this and appreciate your willingness to use these services for the challenge.

## Tasks

1.  **Application:** Create a basic "Hello World" web application. The specific language or framework is your choice.
2.  **Containerization:** Write a `Dockerfile` to containerize your application.
3.  **Infrastructure:** Use [Terraform](https://www.terraform.io/) to provision the necessary AWS infrastructure, including:
    - A VPC (Virtual Private Cloud) suitable for EKS.
    - An [AWS EKS](https://aws.amazon.com/eks/) cluster.
    - Any other required resources (e.g., IAM roles, security groups).
    - _Hint: Leverage existing community Terraform modules where appropriate._
4.  **Deployment:**
    - Configure Kubernetes manifests (Deployments, Services, etc.) to run your application on the EKS cluster.
    - _Preferred:_ Package your application deployment using a [Helm](https://helm.sh/) chart.
    - Expose your application to the internet, preferably using an Ingress controller like [Traefik](https://traefik.io/traefik/), or alternatively using a Kubernetes Service of type `LoadBalancer`.
5.  **Automation:** Set up a [GitHub Actions](https://github.com/features/actions) workflow that automates the following upon pushing changes to the `main` branch:
    - Builds the Docker image.
    - Pushes the image to a container registry (e.g., Docker Hub, AWS ECR).
    - Deploys the updated application to the EKS cluster (e.g., using `kubectl apply`, `helm upgrade`).

## Deliverables

1.  **Git Repository:** A publicly accessible Git repository (e.g., on GitHub) containing all the necessary code:
    - Application source code.
    - `Dockerfile`.
    - Terraform code (`.tf` files).
    - Kubernetes manifests (`.yaml` files) and/or Helm chart (`Chart.yaml`, templates, `values.yaml`).
    - GitHub Actions workflow file(s) (`.github/workflows/*.yaml`).
2.  **README.md:** Clear instructions within the repository's `README.md` file explaining:
    - Prerequisites (e.g., AWS account setup, AWS credentials configuration, GitHub secrets needed for Actions), no need to actually publish secrets.
    - How to provision the infrastructure using Terraform.
    - How to trigger the CI/CD pipeline and deploy the application.
    - How to access the deployed "Hello World" application.
3.  **Reflection:** A short paragraph in the `README.md` reflecting on your solution. Discuss your design choices, any challenges encountered, and potential improvements or areas you would explore further given more time (e.g., monitoring, logging, security hardening, cost optimization).

Good luck! We look forward to seeing your solution.
