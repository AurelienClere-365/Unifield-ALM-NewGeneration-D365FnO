# Unifield ALM – New Generation for Dynamics 365 Finance & Operations

A modern, unified, and fully automated ALM framework for **Dynamics 365 Finance & Operations (D365 F&O)**, built to embrace Microsoft’s *Unified Developer Experience* and deliver a Git‑based, cloud‑native, end‑to‑end DevOps ecosystem.

This repository provides **Azure DevOps YAML pipelines**, **environment automation workflows**, and **PAC Model Builder integrations** that enable teams to adopt the next generation of ALM for F&O — consistent with Dataverse and Power Platform ALM practices.

---

## 🌐 Vision and Purpose

This project aims to solve the long‑standing fragmentation in the F&O development lifecycle by delivering a **coherent, unified, and future‑proof ALM experience**.

It addresses challenges such as:

- Legacy build VMs and manual LCS operations  
- TFVC vs Git inconsistencies  
- Siloed ALM between X++ and Power Platform  
- Manual environment refreshes and user enablement  
- Lack of automation for UDE (Unified Development Environment) provisioning  
- Disconnected deployment pipelines  

The repository implements the principles of Microsoft’s *Unified Developer Experience*:

- Git as the single source of truth  
- Cloud-hosted build agents  
- PAC CLI for model building  
- Unified Dev Environments (UDEs)  
- Automated environment operations  
- Cross-platform ALM with Power Platform Build Tools  

---

## 📁 Repository Structure

### 1. Build Pipelines

| Pipeline | Description |
|---------|-------------|
| `azure-build-pipelines-main.yml` | Main branch build pipeline for production-ready builds. |
| `azure-build-pipelines-test.yml` | Test branch build pipeline for validation and PR integration. |
| `d365bap-tools.yml` | Integrates Power Platform Build Tools for hybrid ALM scenarios. |
| `pac-modelbuilder-create-ude.yml` | Creates a Unified Development Environment (UDE) using PAC Model Builder. |
| `pac-modelBuilder-EnableUser.yml` | Automates user enablement in UDE environments. |

These pipelines compile X++ models, generate deployable packages, validate metadata, and publish artifacts using cloud-hosted agents.

---

### 2. Environment Automation Pipelines

| Pipeline | Description |
|---------|-------------|
| `copy-environment.yml` | Automates environment copy operations (Sandbox → Dev, Dev → Test, etc.). |
| `lcs-db-refresh-export.yml` | Automates LCS DB refresh/export using the new LCS API. |

These workflows eliminate manual LCS navigation and support fully automated refresh workflows.

---

### 3. Dataverse & Power Platform Integration

| Pipeline | Description |
|---------|-------------|
| `bpa-apps-dataverse.yml` | Build & deploy pipeline for Dataverse and Power Apps components. |

This enables **true cross-platform ALM** between F&O and Dataverse.

---

## 🧱 Core Concepts Implemented

### Unified Development Environment (UDE)

A UDE is a lightweight, cloud-hosted, Git-connected development environment replacing legacy VMs.

This repo includes pipelines to:

- Provision a UDE  
- Enable developers automatically  
- Deploy models into the UDE  
- Validate metadata using PAC CLI  

### PAC Model Builder

The new PAC CLI replaces legacy build tools and supports:

- Model compilation  
- Package generation  
- Metadata validation  
- Unified build logic across F&O and Power Platform  

### Unified ALM

This repository aligns with Microsoft’s new ALM strategy:

- One Git repository  
- One pipeline architecture  
- One build system (PAC CLI)  
- One environment provisioning model  
- One ALM approach for F&O + Dataverse  

---

## ⚙️ Prerequisites

Before using the pipelines, ensure you have:

- Azure DevOps project with Git repository  
- Service connections for:
  - Azure Resource Manager  
  - LCS API authentication  
  - Power Platform Build Tools  
- Access to D365 F&O environments  
- Variable groups for:
  - LCS project ID  
  - Environment ID  
  - Client ID / Secret  
  - Azure subscription details  

PAC CLI installation is handled automatically by the pipelines.

---

## 🏗️ Pipeline Architecture

### Build Stage

- Restore NuGet packages  
- Compile X++ models  
- Generate deployable packages  
- Validate metadata  
- Publish artifacts  

### Release Stage

- Deploy packages to target environments  
- Run post-deployment scripts  
- Trigger Dataverse solution deployment (optional)  

### Environment Operations

- Automated DB refresh  
- Automated environment copy  
- Automated UDE provisioning  
- Automated user enablement  

---

## 📘 How to Use This Repository

### 1. Clone the repository

```bash
git clone https://github.com/AurelienClere-365/Unifield-ALM-NewGeneration-D365FnO
