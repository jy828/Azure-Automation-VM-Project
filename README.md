# Azure Automation VM Project

## Project Title

Azure Automation Runbooks for VM Start and Stop Schedules

## Project Overview

This project focuses on automating the start and stop operations of Azure Virtual Machines using Azure Automation Runbooks.

The system is designed to automatically start virtual machines during required working hours and stop them outside business hours. This helps reduce unnecessary VM runtime, manual administration, and cloud resource usage.

## Problem Statement

## Problem Statement

Non-production and test environment Virtual Machines are often left running outside business hours, resulting in unnecessary cloud resource consumption and increased Azure costs.

Manual VM start and stop operations require administrator intervention and may lead to operational errors. In addition, failures in Azure Automation Runbooks may go unnoticed if proper monitoring and alerting are not configured.

Another challenge is that Managed Identity permissions may be assigned more broadly than necessary for convenience, which can create unnecessary access privileges.

Therefore, this project aims to automate VM start and stop operations, monitor runbook execution, provide failure alerts, and apply appropriate RBAC permissions following the principle of least privilege.
## Proposed Solution

The project uses Azure Automation Runbooks to automate VM start and stop operations according to predefined schedules.

PowerShell Runbooks communicate with Azure Virtual Machines, while Managed Identity provides secure authentication without storing passwords or access keys in the scripts.

## Objectives

- Automate Azure VM start and stop operations.
- Reduce unnecessary VM runtime.
- Minimize manual administration.
- Use Managed Identity for secure authentication.
- Apply appropriate RBAC permissions.
- Monitor runbook execution.
- Detect runbook failures.
- Improve Azure resource utilization.

## Technologies Used

- Microsoft Azure
- Azure Virtual Machines
- Azure Automation
- PowerShell
- Managed Identity
- Azure RBAC
- Azure Monitor

## Project Architecture
                    AZURE AUTOMATION
                           │
              ┌────────────┴────────────┐
              │                         │
       START SCHEDULE              STOP SCHEDULE
         (9:00 AM)                   (6:00 PM)
              │                         │
              ▼                         ▼
       ┌─────────────────────────────────────┐
       │       AZURE AUTOMATION ACCOUNT      │
       │                                     │
       │   ┌─────────────┐  ┌─────────────┐ │
       │   │  Start-VM   │  │   Stop-VM   │ │
       │   │  Runbook    │  │   Runbook   │ │
       │   └──────┬──────┘  └──────┬──────┘ │
       └──────────┼─────────────────┼────────┘
                  │                 │
                  └────────┬────────┘
                           ▼
                 ┌──────────────────┐
                 │ Managed Identity │
                 └────────┬─────────┘
                          ▼
                 ┌──────────────────┐
                 │  Azure RBAC      │
                 │  Permissions     │
                 └────────┬─────────┘
                          ▼
                 ┌──────────────────┐
                 │   Azure VM       │
                 │                  │
                 │ Running ↔ Stopped│
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │ Automation Job   │
                 │     History      │
                 └────────┬─────────┘
                          ▼
                 ┌──────────────────┐
                 │ Azure Monitor    │
                 │   & Alerts       │
                 └────────┬─────────┘
                          ▼
                    Administrator
## Services / Technologies Required

### Azure Services

- Azure Virtual Machines
- Azure Automation Account
- Azure Automation Runbooks
- Azure Managed Identity
- Azure Role-Based Access Control (RBAC)
- Azure Automation Schedules
- Azure Monitor and Alerts

### Technologies

- Microsoft Azure
- PowerShell
- Azure Portal
- Git
- GitHub
- Markdown
