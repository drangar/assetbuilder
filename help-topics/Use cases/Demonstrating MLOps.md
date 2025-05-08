# Demonstrating MLOps
Demonstrating MLOps involves executing a sequence of defined steps. Each step ideally should be run one at a time, and the results observed via the Cloud Pak for Data (CPD) user interface. This ensures clarity and traceability of the deployment pipeline.

If however you want to recreate a MLOps demo environment quickly, you could run all the steps below one after the other without stopping to walk through the CPD UI.

<img width="50%" height="50%" alt="Screenshot 2025-05-08 at 3 48 53 PM" src="https://github.com/user-attachments/assets/d25bdf97-4127-4593-a1d1-17f1b38da927" />

---

## 📌 Steps Overview

1. [Install and configure `cpdctl`](#1-install-and-configure-cpdctl-utility)  
2. [Import the MLOps project](#2-import-the-mlops-project)  
3. [Create QA and PROD deployment spaces, and deploy the ML model to QA](#3-create-qa-and-prod-deployment-spaces)  
4. [Evaluate the ML model](#4-evaluate-the-ml-model)  
5. [Promote ML model to PROD (if evaluation is successful)](#5-promote-ml-model-to-prod)

---

## 1. Install and configure `cpdctl` utility

**Description**:  
Install the `cpdctl` CLI tool and create the profile for CPD.  
For CPDaaS, provide:
- `ibmcloud_api_key`: Set to na if using CPD software  
- `ibmcloud_account_id`: Set to na if using CPD software 

For CPD software, provide:
- `cpd_url`  
- `cpd_username`  
- `cpd_apikey`  

---

## 2. Import the MLOps Project

**Description**:  
Set up the demo project by importing assets from a zip file.  
You will need:
- `ibmcloud_api_key`: Set to na if using CPD software  
- `ibmcloud_account_id`: Set to na if using CPD software  
- `project_name`  

---

## 3. Create QA and PROD Deployment Spaces

**Description**:  
Create two deployment spaces (`QA` and `PROD`) and deploy the ML model to the QA space.

**Inputs**:
- `ibmcloud_api_key`: Set to na if using CPD software  
- `ibmcloud_account_id`: Set to na if using CPD software  
- `qa_deployment_space`  
- `prod_deployment_space`  
- `project_name`  

---

## 4. Evaluate the ML Model

**Description**:  
Evaluate the ML model deployed in the QA space using accuracy and precision metrics.

**Inputs**:
- `ibmcloud_api_key`: Set to na if using CPD software  
- `ibmcloud_account_id`: Set to na if using CPD software  
- `cpd_url`  
- `cpd_username`  
- `cpd_password`  
- `qa_deployment_space`  
- `project_name`  
