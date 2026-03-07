# Cloud Computing Fundamentals - TryHackMe

The cloud is built on top of technologies, like virtualization and containers. These enable running many applications efficiently on shared infrastructure and quickly creating or changing environments when needed.

## 1. Cloud Computing Overview

### How Servers Evolved to Cloud?
Before we start diving into cloud details, it’s helpful to understand that cloud computing did not appear suddenly. It is the result of many years of changes in how servers were used and managed. At each step, businesses looked for ways to reduce costs, use resources more efficiently, and make their applications easier to run and scale. 

### Cloud Benefits and Characteristics

The following benefits and characteristics explain how cloud computing makes applications easier to run, scale, and manage:

- Scalability: Easily scale up or down as your application's needs change.
- On-demand self-service: Create or remove servers and storage instantly, without waiting for hardware.
- Pay only for what you use: You are charged based on usage, not upfront costs.
- Security: Cloud providers protect the infrastructure with strong security measures.
- High availability: Applications keep running even if part of the system fails.
- Global access: Your application can be accessed by users anywhere in the world.

### Types of Cloud

**deployment types:**
- Public Cloud: Used by startups, websites, and global apps because it is affordable, easy to scale, and requires no infrastructure management. Public cloud services are preferable for nearly every use case.
- Private Cloud: Used by banks, healthcare, and government organizations because it offers greater control, customization, and compliance for sensitive data.
- Hybrid Cloud: Used by companies like e-commerce platforms that need to keep sensitive data private while still scaling publicly during high demand.

**cloud service model:**
- Infrastructure as a Service (IaaS): You rent basic computing resources such as virtual servers, storage, and networking. You are responsible for managing the operating system and your application, while the provider manages the physical hardware.
- Platform as a Service (PaaS): The cloud provider manages the infrastructure and the operating system. You focus on building, deploying, and running your application without worrying about servers.
- Software as a Service (SaaS): You use a complete application over the internet. The provider manages everything, and you access the software through a browser or app, for example, Gmail or Zoom.

### Major Cloud Vendors
- Microsoft Azure: A strong competitor, especially in enterprise and hybrid cloud environments.
- Google Cloud Platform (GCP): Known for powerful data analytics, AI, and machine learning tools.
- Alibaba Cloud: A major player in Asia, offering competitive cloud services globally.
- IBM Cloud: Focuses on hybrid cloud and AI-driven solutions for businesses.
- Oracle Cloud: Focuses on enterprise applications and databases.

## 2. Basic Cloud Terminology

EC2 (Virtual Computer / Server): EC2 represents a virtual computer in the cloud. Just like a real computer, it has a CPU and memory (RAM) and can run applications. Whenever you add an EC2 instance, you are adding a computer to your environment.
Instance Type (for example: t2, t3, m5): Instance types describe how powerful the virtual computer is. Some have more CPU and RAM and are therefore more expensive. You choose the Instance Type based on your needs, knowing that:
Bigger instances = more power + higher cost
Minor instances = less power + lower cost