# What will you learn 

## Introduction to EC2:

What is EC2, and why is it important?

An EC2 instance is a virtual server in AWS that you can use to run applications, websites, databases, or backend services without buying physical hardware.

Think of it like:

“A computer running in AWS data centers that you can start, stop, resize, and pay only for what you use.”

```
- Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud.
- Access reliable, scalable infrastructure on demand. Scale capacity within minutes with SLA commitment of 99.99% availability.
- Provide secure compute for your applications. Security is built into the foundation of Amazon EC2 with the AWS Nitro System.
- Optimize performance and cost with flexible options like AWS Graviton-based instances, Amazon EC2 Spot instances, and AWS Savings Plans.
```

EC2 usecases

```
Deliver secure, reliable, high-performance, and cost-effective compute infrastructure to meet demanding business needs.
Access the on-demand infrastructure and capacity you need to run HPC applications faster and cost-effectively.
Access environments in minutes, dynamically scale capacity as needed, and benefit from AWS’s pay-as-you-go pricing.
Deliver the broadest choice of compute, networking (up to 400 Gbps), and storage services purpose-built to optimize price performance for ML projects
```

EC2 Instance Types

Recommended to follow [this](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html) page for very detailed and updated information.

General purpose

```
General Purpose instances are designed to deliver a balance of compute, memory, and network resources. They are suitable for a wide range of applications, including web servers,
small databases, development and test environments, and more.
```

Compute optimized

```
Compute Optimized instances provide a higher ratio of compute power to memory. They excel in workloads that require high-performance processing such as batch processing, 
scientific modeling, gaming servers, and high-performance web servers.
```

Memory optimized

```
Memory Optimized instances are designed to handle memory-intensive workloads. They are suitable for applications that require large amounts of memory, such as in-memory databases,
real-time big data analytics, and high-performance computing.
```

Storage optimized

```
Storage Optimized instances are optimized for applications that require high, sequential read and write access to large datasets. 
They are ideal for tasks like data warehousing, log processing, and distributed file systems.
```

Accelerated computing

```
Accelerated Computing Instances typically come with one or more types of accelerators, such as Graphics Processing Units (GPUs),
Field Programmable Gate Arrays (FPGAs), or custom Application Specific Integrated Circuits (ASICs). 
These accelerators offload computationally intensive tasks from the main CPU, enabling faster and more efficient processing for specific workloads.
```

![image](https://github.com/iam-veeramalla/aws-devops-zero-to-hero/assets/43399466/fc8e083c-dba5-41a6-94b9-14ebef0255c1)

Instance families

```
    C – Compute

    D – Dense storage

    F – FPGA

    G – GPU

    Hpc – High performance computing

    I – I/O

    Inf – AWS Inferentia

    M – Most scenarios

    P – GPU

    R – Random access memory

    T – Turbo

    Trn – AWS Tranium

    U – Ultra-high memory

    VT – Video transcoding

    X – Extra-large memory
```

Additional capabilities

```
    a – AMD processors

    g – AWS Graviton processors

    i – Intel processors

    d – Instance store volumes

    n – Network and EBS optimized

    e – Extra storage or memory

    z – High performance
```

## EC2 Instance Basics:

Understanding the concept of virtual servers and instances.
Key components of an EC2 instance: AMI (Amazon Machine Image), instance types, and instance states.
Differentiating between On-Demand, Reserved, and Spot instances.

## Launching an EC2 Instance:

- Step-by-step guide on launching an EC2 instance using the AWS Management Console.
- Configuring instance details, such as instance type, network settings, and storage options.
- Understanding security groups and key pairs for securing instances.

How to Launch an EC2 Instance (Steps):
======================================

    1.Open AWS Console → EC2

    2.Click Launch Instance

    3.Choose AMI

    4.Select Instance Type

    5.Configure network (VPC, Subnet)

    6.Add storage

    7.Configure Security Group

    8.Create / select Key Pair

    9.Launch

## Managing EC2 Instances:

    - Starting, stopping, and terminating instances.
    - Monitoring instance performance and utilization.
    - Basic troubleshooting and accessing instances using SSH (Secure Shell).

EC2 Security Best Practices:
==============================

    1.Use IAM Roles, not access keys

    2.Enable Security Groups with least access

    3.Use MFA on AWS account

    4.Encrypt EBS volumes

    5.Disable public IP if not needed

EC2 Components (what you need to launch an EC2):
==================================================

       1.AMI (Amazon Machine Image) – This is the OS + pre-installed software template (like Ubuntu / Amazon Linux / Windows).

        2.Instance Type – Decides CPU, RAM, network performance (example: t3.micro, t3.medium).

        3.VPC + Subnet – Where the server will live (public subnet for internet apps, private subnet for internal).

        4.Security Group – Firewall for the instance (allow SSH 22, HTTP 80, HTTPS 443).

        5.Key Pair – Used to login securely (SSH key for Linux, RDP password decryption for Windows).

        6.Storage (EBS Volume) – Hard disk for the instance (root volume + optional extra volumes).

        7.Elastic IP (Optional) – Fixed public IP if you don’t want the IP to change.

        8.IAM Role (Optional but best) – Gives EC2 permissions to access S3, CloudWatch, etc. without keys.

        9.User Data (Optional) – Startup script to install apps automatically (like nginx, docker).

Step-by-step: How EC2 is created and works :
=============================================

       1.“First I choose an AMI, like Amazon Linux or Ubuntu.”

        2.“Then I select the instance type based on CPU and RAM needs.”

        3.“Next I pick the VPC and subnet—public subnet if it needs internet access.”

        4.“After that I attach a security group to allow required ports like 22, 80, 443.”

        5.“Then I select or create a key pair to securely login.”

        6.“I configure EBS storage, like 20GB or 50GB based on requirement.”

        7.“If needed, I attach an IAM role so the instance can access AWS services securely.”

        8.“Optionally I add user data to install packages automatically during boot.”

        9.“Finally I launch it, and then I connect using SSH (Linux) or RDP (Windows).”