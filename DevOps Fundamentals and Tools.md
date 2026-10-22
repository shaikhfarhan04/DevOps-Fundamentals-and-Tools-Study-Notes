Here is a structured, beginner-friendly DevOps study document based on your notes. I’ve organized the concepts, corrected a few technical definitions, grouped the tools by purpose, and added installation and verification steps for your Windows 11 + AWS learning environment.

# DevOps Fundamentals and Tools — Study Notes

# 1. What is DevOps?

DevOps = Development + Operations

DevOps is a set of practices, processes, and tools that help development and IT operations teams collaborate to build, test, release, deploy, and maintain software efficiently.

Main objectives:

- Faster and more reliable software delivery.
- Automation of repetitive tasks.
- Continuous Integration and Continuous Delivery (CI/CD).
- Improved collaboration between development, testing, and operations teams.
- Monitoring, reliability, security, and high availability.

## 2. Important DevOps terminology

| Term       | Full form / meaning             | Explanation                                                                                            |
| ---------- | ------------------------------- | ------------------------------------------------------------------------------------------------------ |
| SDLC       | Software Development Life Cycle | Process of planning, designing, developing, testing, deploying, and maintaining software.              |
| SLA        | Service Level Agreement         | Agreement defining service commitments between a provider and a customer.                              |
| SLO        | Service Level Objective         | A measurable target for service reliability or performance.                                            |
| IT         | Information Technology          | Systems, infrastructure, applications, and services used to manage information.                        |
| SRE        | Site Reliability Engineering    | Applying software engineering and automation to improve service reliability.                           |
| Developer  | Software development            | Writes and maintains application code.                                                                 |
| Operations | IT operations                   | Manages infrastructure, deployments, availability, and production systems.                             |
| Support    | Technical support               | Investigates incidents and helps restore services.                                                     |
| IaC        | Infrastructure as Code          | Managing infrastructure through version-controlled configuration files.                                |
| LB         | Load Balancer                   | Distributes incoming traffic across multiple targets.                                                  |
| HA         | High Availability               | Designing systems to minimize downtime.                                                                |
| Node       | Compute machine                 | A physical or virtual machine that runs workloads; in Kubernetes, a worker node runs application Pods. |
| Deployment | Software release process        | Making an application or application version available in an environment.                              |
| Sprint     | Fixed development iteration     | A time-boxed period in Scrum, usually one month or less.                                               |

Important distinction: SRE stands for Site Reliability Engineering, not Site Recovery Engineering. Site recovery is a related but different disaster-recovery concept.

## 3. Software development methodologies

[Min Thep - Blog SWE201c](https://images.openai.com/static-rsc-4/JFdVdJqH-rMBinxvEos0quhhcWEx66JFneW1X-6KV2TkXbe3K0Vq8YtZfgHxHkh73ku725Hthc1Djj8bPfpYOCpUHPLJZNx0K9HyERSot2BcDDuMet5xSGJ_WGxnEox5vijn7FCy-yfNArWsyiRNHMJu5sgYeiYOddBtmH8Ri7w?purpose=inline)

Waterfall Model

A sequential approach in which work progresses through defined phases, such as requirements, design, development, testing, deployment, and maintenance.

- Best suited to projects with stable, well-defined requirements.
- Changes late in the process can be expensive.

[Agile Model of Software Development the Development Cycle – Charts | Diagrams | Graphs](https://images.openai.com/static-rsc-4/n-ME24VQUfE4zDxakpx0whyKZgbcLej_CTVL8nuv3opTGghxiHiN2vU6IWAQBIWARef29abBtpj3wPMUVfF_dn668IsV4k34T63GJPKmDCA0wZTm5h6B0swUewa0txeuqu78H5T4ZJLODXnKoQtAatzuI2CIK5m5256QEv4gfVw?purpose=inline)

Agile Process

An iterative approach that delivers software in smaller increments, gathers feedback, and adapts to changing requirements.

- Encourages collaboration and continuous improvement.
- Supports frequent delivery and feedback.

[Scrum Framework: What Is It, and How Does It Work?](https://images.openai.com/static-rsc-4/n3UsqwQuaTNaxszC9BuP7emo5YYr0B36ryvy3aQVfazz15nHqryzsw1bWdFeB4PcGSWvg7Hy7pQUFabp6xIeQ0yZDuyIpD7-FIHkSLs5kXgEU1Q3EFoyyhXiQVLOr-clBxweIIvmc6-coJSm8onQSBshUlVz3zR2igrioJY1khY?purpose=inline)

Scrum

An Agile framework that organizes work into Sprints with defined accountabilities, events, and artifacts.

- Product Backlog and Sprint Backlog.
- Sprint Planning, Daily Scrum, Sprint Review, and Sprint Retrospective.
- Developers collaborate to deliver a usable Increment.

### Development and testing teams

- Development team: Writes code, fixes bugs, reviews changes, and implements features.
- Testing / QA team: Validates functionality, performance, security, and application quality through manual and automated testing.
- DevOps / platform team: Automates builds, deployments, infrastructure provisioning, and operational workflows.
- Operations / support team: Monitors production systems, handles incidents, and maintains service availability.

These responsibilities can overlap in modern DevOps teams.

## 4. Infrastructure as Code (IaC) and Terraform

Terraform is an IaC tool used to provision and manage infrastructure through declarative configuration.

Examples of resources you can manage:

- AWS EC2 instances, VPCs, subnets, and security groups.
- Load balancers and Auto Scaling resources.
- Databases, storage, and IAM resources.
- Kubernetes-related infrastructure.

Typical Terraform workflow:

Write configuration — `.tf` files

`terraform init`

`terraform plan`

`terraform apply`

Infrastructure created or updated

Example Terraform configuration:

```
resource "aws_s3_bucket" "demo" {
  bucket = "replace-with-a-globally-unique-name"
}
```

The example creates an S3 bucket when applied with valid AWS credentials and appropriate permissions. Always review the plan before applying changes.

## 5. DevOps tools and their purposes

[Git logo Icons, Logos, Symbols – Free Download PNG, SVG](https://images.openai.com/static-rsc-4/Sb9O7jvMvZHvARi9aABeXIsBR0rd39FouCmFfFC--ZTHNXo79OH1i9deenC1xIJDeNhErgpYvCNupQ86CyufXxgmC_VQuaWQJaVMQ1Bu_NZ1pz9CTE0V2o-hLrSXkvABahTtp3cJmsi0qPnuLXNK6XMJdccgzbVA2YTQJZF6slM?purpose=inline)

Git — Version Control

Tracks code changes, branches, merges, and collaboration.

Common commands: `git init`, `git add`, `git commit`, `git push`, `git pull`

[Docker Logo Icon by Those Icons – download in PNG, SVG](https://images.openai.com/static-rsc-4/Mif5Qzd0qx3Jbj-4TuWVI_O9UDwBlSBL30CyUxSUfYZGP9oKeaWHiWDAVPpobyT8lL6Wrb-lZ1pWXRD-zaUMMUg2XXOaEPzknWtoW7BVHHjTTjHFXwt7f9DNRNV8bPVbZOCAXIqXMgnyelx4CBxJ_ZSfEsqXafuxj078-zWQ5fI?purpose=inline)

Docker — Containerization

Packages applications and their dependencies into portable containers.

Common commands: `docker build`, `docker run`, `docker ps`, `docker logs`

[fResult Sila / K8s Skooldio Workshop · GitLab](https://images.openai.com/static-rsc-4/1zdPJJlmhXFCCOgxGYo3lWdvPxbgnAqsUyq87sWyYYk7QCIZqZ8bb271m-3GHCvuW7ahdN2J1fndQw3oSN7vRbKhaUQEqY1CVWIBjVdrW4A_G1Ypl1QJ2KYXi7eIN1nurdIi_3ONf8iUy_Nkn72fp-vu15lhf2QotoJdzL3ki_U?purpose=inline)

Kubernetes (K8s) — Container Orchestration

Automates container deployment, scaling, networking, and recovery.

Common commands: `kubectl get pods`, `kubectl get nodes`, `kubectl apply -f`

[Terraform and Layered Infrastructure (part I) | gchiesa.dev](https://images.openai.com/static-rsc-4/kZtq-27Plqdyn0cAmR_JoKlwTPGdoFzunewV0mTfnn32h2h7Z3Xo05J_TV6xiK085oE0KTsUbYuXhIpRkcF4ryyRfw_W1_9U8_DmvWvt_Z4OYU0B1N5YGXEXGk10jh2lomQYTYnxaZln0GB2FDjCgXzEOlvFXZB7eZFb5uMiT-8?purpose=inline)

Terraform — Infrastructure as Code

Provisions cloud resources using declarative configuration.

Common commands: `terraform init`, `terraform plan`, `terraform apply`

[Jenkins Logo Vector PNG | Jenkins Automation Butler Emblem  - freepng](https://images.openai.com/static-rsc-4/62I10ATSsHYrADkr1-J8bcuuWFRp3V5eA3pO0ivRDCVU8H013EggI7-nSqJtJ59sg8_yAVoRXUHqYvbwSLfvF5dZ-wzcwZUSxQn0gFi_oxcMPMaC60kpyEKQks7atwBWfuOhQukfvG2d2YzTaukbfwQ3_uHEn91nPJtIO764G4M?purpose=inline)

Jenkins — CI/CD Automation

Automates builds, tests, and deployments using pipelines defined in a `Jenkinsfile`.

Typical stages: Checkout → Build → Test → Deploy

[Récupérer les informations sur la distribution avec les facts Ansible](https://images.openai.com/static-rsc-4/m0hm56UcDI7frQU0sw2iyf5ja2pG7kV6OTssn-1O58iuvIzuaAYhjta15xVU3SIeYMGk8PtJ5Az9NIOVWPnvboox2i9_Hma0t34U0dsJ-z_8dyC2epmYG2AJm2NAflChAY_6vnNsydmvjgVRaqjecBnMXEqh2mHAUOkfNJehTyw?purpose=inline)

Ansible — Configuration Management

Automates software installation, OS configuration, service management, application deployment, and orchestration.

Uses YAML playbooks. Linux SSH is commonly used for remote Linux hosts; Windows hosts can be managed using supported Windows connection methods.

[Fichier:Prometheus software logo.svg - Wikisource](https://images.openai.com/static-rsc-4/fepPjY_neWlerRDx3jGoMbIOODcqUKFP-xK4JCE9gDYjfgE0oZnQot03AShEimFI4xKFWOI5UkXjaTG5Dwy-Y6sHZ8WssrPUsV611AhkfF-bWCojn6LHVlZJ72EWwkfGYPP-yz9x7o0jRJ2iAd1ocItnGSxJJ8IUWLVCqGrrn3I?purpose=inline)

Prometheus — Metrics Monitoring

Collects and stores time-series metrics, commonly by scraping configured targets at regular intervals.

[File:Grafana logo.svg - Wikimedia Commons](https://images.openai.com/static-rsc-4/wFlazXwUNtzBWhhYsfsO-iUHvVSX5psinU3cIyRBrPH-55jhN6vA1HJ-mF2Hp100x3Tof5pLNGXUx0-pTz7u8q_JpmVgKgCX44IZUc_4hgiVbRagjB30d5GhTLYc6_wu5rfBVxWTQQ0KKNKianfSW18M10GjLFTQJ_SxujesfgQ?purpose=inline)

Grafana — Visualization and Dashboards

Queries Prometheus and other supported data sources to create dashboards, charts, and alerts.

### How Prometheus and Grafana work together

Application / EC2 / Node Exporter

Produces metrics

Prometheus

Scrapes and stores metrics

Grafana

Displays dashboards and visualizations

Configuration formats to remember

| Tool       | Common configuration                                                      |
| ---------- | ------------------------------------------------------------------------- |
| Git        | `.gitconfig`, `.gitignore`                                                |
| Docker     | `Dockerfile`, `compose.yaml`                                              |
| Kubernetes | YAML manifests                                                            |
| Terraform  | HCL (`.tf` files)                                                         |
| Jenkins    | `Jenkinsfile`                                                             |
| Ansible    | YAML playbooks and inventory files                                        |
| Prometheus | YAML configuration                                                        |
| Grafana    | YAML for provisioning; dashboards can use JSON and UI-based configuration |

Corrections to your original notes:

- Ansible does not work only on Linux. Its control node is commonly Linux or WSL Ubuntu, and it can manage supported Windows targets too.
- Ansible commonly connects to Linux servers over SSH (port 22), but it can use other connection methods and ports.
- Kubernetes is not limited to a single operating system; its supported node operating systems depend on the Kubernetes distribution and version.
- Docker containers are not the same as virtual machines. Containers share the host kernel, whereas VMs run their own guest operating system kernel.

## 6. Installation guide — Windows 11

The following setup uses Windows PowerShell for your local DevOps workstation. Install Docker Desktop before setting up Minikube, and use WSL Ubuntu for Ansible.

### Step 1: Check whether Winget is available

Open PowerShell and run:

```
winget --version
```

If the command works, use the installation commands below. If not, install or update App Installer from the Microsoft Store.

### Step 2: Install the core tools

Run these commands individually in PowerShell:

1\. Git

```
winget install --id Git.Git -e
git --version
```

2\. AWS CLI

```
winget install --id Amazon.AWSCLI -e
aws --version
```

Configure credentials only after installation, using `aws configure` or a suitable AWS IAM Identity Center / role-based setup.

3\. Python

```
winget install --id Python.Python.3.13 -e
python --version
python -m pip --version
```

If Python is already installed, check it first. Restart PowerShell after installation if commands are not recognized.

4\. Docker Desktop

```
winget install --id Docker.DockerDesktop -e
docker --version
docker compose version
```

Start Docker Desktop, enable its WSL 2 backend if prompted, and verify that the Docker engine is running:

```
docker run hello-world
```

5\. Terraform

```
winget install --id Hashicorp.Terraform -e
terraform --version
```

Open a new PowerShell window after installation.

### Step 3: Install Kubernetes tools

Minikube runs a local Kubernetes cluster. It requires a supported driver; Docker is a convenient option for your workstation.

```
winget install --id Kubernetes.kubectl -e
winget install --id Kubernetes.minikube -e
```

Verify:

```
kubectl version --client
minikube version
```

Start a local cluster after Docker Desktop is running:

```
minikube start --driver=docker
kubectl get nodes
kubectl get pods -A
```

Expected result: a Kubernetes node should appear with `Ready` status once the cluster finishes starting.

To stop the cluster when you are finished:

```
minikube stop
```

### Step 4: Install Ansible using WSL Ubuntu

Ansible's control node is best set up in Linux rather than native Windows PowerShell.

First, open PowerShell as Administrator:

```
wsl --install -d Ubuntu
```

Restart Windows if requested, then open Ubuntu and run:

```
sudo apt update
sudo apt install -y ansible
ansible --version
```

Check that the Ansible playbook command is available:

```
ansible-playbook --version
```

You can use WSL Ubuntu to manage Linux EC2 instances through SSH. Ensure your SSH private key permissions are appropriate for WSL and that your AWS security group allows SSH only from trusted sources.

## 7. Install Jenkins, Prometheus, and Grafana

For a beginner-friendly lab, Docker Compose can run these services without installing each server directly on Windows. This is useful for learning CI/CD and monitoring locally.

### Step 1: Create a monitoring lab

Run in PowerShell:

```
mkdir C:\DevOps-Lab
cd C:\DevOps-Lab
mkdir monitoring
cd monitoring
notepad compose.yaml
```

Paste the following configuration into `compose.yaml` and save it.

```

services:
  prometheus:
    image: prom/prometheus:latest
    ports:
      - "9090:9090"
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml:ro

  grafana:
    image: grafana/grafana:latest
    ports:
      - "3000:3000"
    depends_on:
      - prometheus

```

Create the Prometheus configuration file:

```
notepad prometheus.yml
```

Paste and save:

```

global:
  scrape_interval: 15s

scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets: ["prometheus:9090"]

```

Start both services:

```
docker compose up -d
docker compose ps
docker compose logs
```

Open these addresses in your browser:

- Prometheus: [http://localhost:9090](http://localhost:9090?utm_source=chatgpt.com)
- Grafana: [http://localhost:3000](http://localhost:3000?utm_source=chatgpt.com)

For a fresh local Grafana container, the default login is commonly `admin` / `admin`; change the password when prompted. Add Prometheus as a Grafana data source using the URL `http://prometheus:9090`.

This basic setup monitors Prometheus itself. To monitor Windows, Linux, EC2, or application metrics, you must configure the appropriate exporter or metrics endpoint and scrape target.

> For a learning lab, pin image versions instead of relying on `latest` in long-lived environments. Do not expose these services publicly without appropriate authentication and network controls.

### Step 2: Install Jenkins

You can run Jenkins in Docker as well. The following is a simple local learning setup:

```
docker volume create jenkins_home

docker run -d --name jenkins `
  -p 8080:8080 -p 50000:50000 `
  -v jenkins_home:/var/jenkins_home `
  jenkins/jenkins:lts
```

Check the service:

```
docker ps
docker logs jenkins
```

Open [http://localhost:8080](http://localhost:8080?utm_source=chatgpt.com). Retrieve the initial administrator password using:

```
docker exec jenkins `
  cmd /c type C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword
```

If that command does not work, the Jenkins container uses a Linux filesystem, so use:

```
docker exec jenkins `
  cat /var/jenkins_home/secrets/initialAdminPassword
```

Complete the initial setup in your browser. Jenkins can then be connected to GitHub to build a sample CI/CD pipeline.

## 8. Installation on Amazon Linux 2023

Since you are also practicing AWS EC2, you can install Grafana on an Amazon Linux 2023 instance separately. Run these commands on the instance over SSH.

First, update the package index and install the required tools:

```
sudo dnf update -y
sudo dnf install -y wget
```

Add the official Grafana RPM repository:

```
sudo tee /etc/yum.repos.d/grafana.repo > /dev/null <<'EOF'
[grafana]
name=grafana
baseurl=https://rpm.grafana.com
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://rpm.grafana.com/gpg.key
EOF
```

Install and start Grafana:

```
sudo dnf install -y grafana
sudo systemctl daemon-reload
sudo systemctl enable --now grafana-server
```

Verify:

```
sudo systemctl status grafana-server
grafana-server -v
```

If the installation succeeds, Grafana normally listens on TCP port `3000`. To access it remotely, configure the EC2 security group to permit port `3000` only from your trusted IP address, or access it through an SSH tunnel. Avoid exposing the dashboard directly to the public internet.

## 9. DevOps tool verification checklist

After installation, open a new PowerShell terminal and check each tool.

## Installation checklist

0 of 13 checked

Git

git --version

AWS CLI

aws --version

Python

python --version

pip

python -m pip --version

Docker

docker --version

Docker Compose

docker compose version

Terraform

terraform --version

kubectl

kubectl version --client

Minikube

minikube version

Ansible (WSL Ubuntu)

ansible --version

Grafana (Docker)

docker exec grafana grafana server --version

Prometheus (Docker)

docker exec monitoring-prometheus-1 prometheus --version

Jenkins (Docker)

docker exec jenkins java -version

&#x20;Copy commandsReset checklist

Notes about the verification commands:

- Run Ansible's version command inside WSL Ubuntu, not PowerShell.
- Grafana and Prometheus commands above assume the containers are named `grafana` and `monitoring-prometheus-1`, respectively. Check `docker ps` if your container names differ.
- `grafana --version` is not a universally available command on Windows; verify Grafana using its actual installation method.
- Jenkins requires Java, which is bundled in the official Jenkins Docker image.
- AWS CLI version output confirms installation, not that your AWS credentials or permissions are valid. Test those with `aws sts get-caller-identity`.

## 10. Recommended learning order

Phase 1 — Fundamentals

Linux, networking, Git, GitHub, Python basics, and shell scripting.

Phase 2 — Cloud and Infrastructure

AWS IAM, EC2, VPC, security groups, S3, Terraform, and Ansible.

Phase 3 — Containers and CI/CD

Docker, Docker Compose, Jenkins pipelines, Kubernetes, and Minikube.

Phase 4 — Monitoring and Reliability

Prometheus, Grafana dashboards, alerting, logs, incident response, SLA/SLO, and high availability.

Your final goal should be a complete project: GitHub → Jenkins CI/CD → Docker → Kubernetes → Terraform-provisioned AWS infrastructure → Prometheus and Grafana monitoring.

This sequence will help you connect the concepts to real hands-on projects and DevOps interview scenarios.
