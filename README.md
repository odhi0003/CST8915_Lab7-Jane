# CST8915 Lab 7: Introduction to Kubernetes Basics

**Student Name**: Jane Akinyi Odhiambo<br/>
**Student ID**: 041268593<br/>
**Course**: CST8915 Full-stack Cloud-native Development<br/>
**Semester**: Fall 2026

---

## Demo Video

[Lab 7 Demo Video](https://youtu.be/PAcExA1J1Ok)

---

## Overview

In this lab, I explored the foundational concepts of Kubernetes, focusing on using kubectl for basic operations, understanding the structure of Kubernetes YAML configuration files, and creating essential Kubernetes resources such as Pods, Deployments, and Services.

---

## Lab Objectives

- Understand the basic structure of a Kubernetes YAML file.
- Learn how to create Kubernetes objects using kubectl and YAML files.

---

## Analysis of the RabbitMQ Configuration Issues

### 1. Is RabbitMQ Stateless or Stateful Application?

RabbitMQ is a stateful application because it manages message queues and other important data.

---

### 2. Implications of Running RabbitMQ Without Persistent Storage

In this lab, the RabbitMQ Deployment does not configure persistent storage. Without persistent storage, this data may be lost when the Pod is deleted or recreated.

Implications of running RabbitMQ without persistent storage include:

- Loss of queued messages
- Loss of queue metadata
- Interruption of services communication

---

### 3. What Happens When the RabbitMQ Pod Is Deleted or Restarted?

When the RabbitMQ pod is deleted, Kubernetes automatically creates a replica pod to replace the deleted pod. The replacement pod begins with a new container filesystem and the previously stored data may be lost.

---

### 4. Potential Solutions to This Problem

There are various ways to potentially solve this issue, such as:

- Configure persistent storage using Azure Managed Disks so that RabbitMQ data is not lost during pod deletion.
- Use a StatefulSet instead of a standard Deployment as they support persistent storage for stateful applications.

---

### 5. Does Azure Service Bus Solve The Issues Identified with RabbitMQ Configuration in This Lab?

Yes, Azure Service Bus can solve the configuration issues because it has a durable message storage, high availability and message handling features.

---

### 6. Setup Challenges and Lessons Learned

In this lab, I learned how to create and manage Kubernetes resources using kubectl CLI and YAML configuration file.

I also understood the importance of persistent storage when deploying stateful applications in Kubernetes.