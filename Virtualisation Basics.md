# Virtualisation Basics - TryHackMe

How expensive and inefficient it would be if every piece of software or every website required its own physical server? 
Virtualization was created to solve exactly this problem.

## 1. Virtualization Overview

Before the concept of virtualization, the rule of thumb in IT was:
“One server = one application.”

If a company wanted to run a website, a database, an email service, and an internal app, they would need separate physical servers for each one. The problems were obvious:

- High cost: Buying multiple physical servers is expensive, not just the hardware, but also electricity, cooling, maintenance, and data center space.
- Low utilization: Most applications don’t use the server’s full capacity. Many servers stayed at 5–20% usage, wasting CPU, memory, and storage resources.
- Slow deployment: Setting up new physical servers could take days or weeks.
- Hard to scale: If an application suddenly needed more resources, you often had to buy yet another server.

A virtualization layer, called a **hypervisor**, was introduced to act as a referee between virtual machines and allow each virtual computer to behave independently, like a physical computer.

## 2. Virtualization Components

1. Hypervisor (The Building Manager): is the core technology behind virtualization. It's the software that creates and manages virtual machines.

It is a special piece of software that:
    - Divides a physical computer into multiple virtual ones.
    - Gives each virtual machine its own share of CPU, memory, and storage.
    - Keeps everything isolated and safe.
    - Manages the lifecycle of virtual machines (start, stop, pause, clone, delete).

There are two types:
    - Type 1 hypervisors run directly on the physical hardware, making them fast, efficient, and ideal for servers and professional environments.
    - Type 2 hypervisors run within an existing operating system, making them easier to install and ideal for learning, testing, or small setups.

2. Virtual Machines: is a virtual computer created by the hypervisor.
3. Containers: is a lightweight, isolated environment that runs a single application and all the necessary components to support it. 