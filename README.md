# Azure Automation VM Project

## Project Title

Azure Automation Runbooks for VM Start and Stop Schedules

## Project Overview

This project focuses on automating the start and stop operations of Azure Virtual Machines using Azure Automation Runbooks.

The system is designed to automatically start virtual machines during required working hours and stop them outside business hours. This helps reduce unnecessary VM runtime, manual administration, and cloud resource usage.

## Problem Statement

Non-production, development, and testing virtual machines are often left running even when they are not being used. This can result in unnecessary cloud resource consumption and increased costs.

Manual starting and stopping of VMs also requires administrator intervention and may lead to human errors.

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
