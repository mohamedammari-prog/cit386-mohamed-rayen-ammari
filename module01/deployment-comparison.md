# Module 1 — Deployment Comparison

## Scenario

**Business:** Cedar Lane Bike Repair, a small neighborhood bicycle repair and sales shop.

Cedar Lane Bike Repair has **6 employees**: two mechanics, two sales associates, one shop manager, and the owner. The shop sells bicycles and parts and performs repairs by appointment. The business has a modest technology budget and can spend up to **$200 per month** on infrastructure and related hosting costs.

## Workload

**Workload:** Online shop operations application for appointments, inventory, and sales.

The application is a small web application with a database. Employees use it at the shop, while customers need to reach the appointment page from outside the building. The workload should run **24/7**, because customers may make appointments after business hours. It should have room to **grow** as the shop adds customers and inventory. Staff should **not need physical access to the host hardware** during normal operation. The monthly infrastructure budget is **$200 or less**.

### Requirements

| Requirement | Needed? |
|---|---|
| Reachable from outside the building | Yes |
| Stay up overnight | Yes |
| Grow with the business | Yes, moderately |
| Physical access to hardware | No |
| Maximum infrastructure budget | $200/month |

## Five Deployment Options

### 1. VirtualBox on a laptop

**Works:** The application can run in a Linux virtual machine on a laptop, and it is inexpensive to start with existing hardware.

**Breaks:** A laptop is not a good 24/7 business server. It adds a single physical point of failure, depends on the laptop remaining powered and connected, and is awkward to expose securely to the Internet for customer access. Growth is also limited by the laptop's hardware.

**Verdict:** Works for testing or a temporary lab, but not a reliable production deployment.

### 2. Hyper-V on a workstation

**Works:** Hyper-V can isolate the application in a virtual machine, and a workstation can provide enough resources for a small workload. It can run continuously and can be configured for network access.

**Breaks:** The workstation is still a single physical host in the shop. Internet access, firewalling, backups, power protection, and hardware failure become the business's responsibility. Scaling beyond the workstation is limited.

**Verdict:** Technically workable, but it creates too much on-site responsibility for a small shop.

### 3. Proxmox host

**Works:** Proxmox provides a dedicated virtualization platform with stronger server-oriented management than a laptop or ordinary workstation. The workload can run in a VM, remain online, and be expanded with additional resources or VMs later.

**Breaks:** The business must buy and maintain a dedicated host, handle electricity, backups, networking, and hardware replacement, and provide a secure path from the Internet to the application. The workload is still tied to an on-site server unless additional infrastructure is added.

**Verdict:** A strong small-business virtualization option, but it requires more hardware and administration than this business wants to take on.

### 4. Physical PC

**Works:** A dedicated PC can run the application directly without a virtualization layer. The initial hardware cost can fit the budget, and the application can remain online if the PC is configured as a server.

**Breaks:** The PC becomes a single point of failure. The business must manage the operating system, backups, power, Internet exposure, security, and hardware replacement. Scaling means replacing or adding hardware.

**Verdict:** Affordable and simple, but weak for a customer-facing workload that must stay available without on-site hardware management.

### 5. Azure

**Works:** Azure can host the workload without requiring the shop to own the server. A virtual machine can use Internet-facing connectivity, and Azure provides availability and scaling options as the workload grows.

**Breaks:** Cloud costs must be monitored so compute, storage, networking, and related services remain within the **$200/month** limit. The business also needs basic cloud administration and security configuration.

**Verdict:** Best overall fit because it removes the need for the shop to maintain server hardware while supporting external access, overnight operation, and future growth.

## Recommendation

**Recommendation: Azure.**

The deciding requirement is **reachability from outside the building**. The workload needs a customer-facing web endpoint while the business does not want to operate and secure an Internet-facing server on its own premises. Azure provides a cloud-hosted deployment model with supported public Internet connectivity and options for scaling without buying additional physical hardware.

The **$200/month** ceiling still matters, so the deployment should start small and use cost controls and monitoring. The recommendation is not that Azure is automatically the cheapest choice; it is that external availability without maintaining on-site server hardware is the requirement that most strongly separates Azure from the other four options.

## AI Disclosure

AI assistance: ChatGPT was used to help organize and phrase this assignment and to research current Azure documentation. The business scenario, workload requirements, comparison judgments, and final deciding requirement should be reviewed and defended by the student.
