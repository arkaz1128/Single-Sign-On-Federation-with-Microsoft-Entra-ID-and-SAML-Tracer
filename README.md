# Project 7 – Single Sign-On Federation with Microsoft Entra ID and SAML Tracer

![Azure](https://img.shields.io/badge/Microsoft-Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![SAML](https://img.shields.io/badge/Protocol-SAML%202.0-orange?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Domain](https://img.shields.io/badge/Domain-SSO%20%7C%20Federation%20%7C%20SAML%20%7C%20IAM-blueviolet)

---

## Overview

This project demonstrates the configuration of **Single Sign-On** between **Microsoft Entra ID** acting as the Identity Provider and a test enterprise application called **VaultBridge** acting as the Service Provider. The federation trust was established by configuring the Entity ID, Assertion Consumer Service URL, and SAML metadata. Test users were assigned to the application and a live SAML assertion was captured and inspected using the **SAML Tracer** browser extension, confirming the full authentication flow end to end.

---

## Environment

| Tool | Purpose |
|------|---------|
| Microsoft Azure Portal | Cloud identity platform and IdP configuration |
| Microsoft Entra ID | Identity Provider (IdP) for SAML federation |
| VaultBridge (Enterprise App) | Service Provider (SP) for SAML SSO test |
| SAML 2.0 | Authentication protocol for federated SSO |
| SAML Tracer (Browser Extension) | Live SAML assertion inspection and decode |
| GitHub | Documentation and version control |

---

## Lab Design

### SAML Configuration

| Setting | Value |
|---------|-------|
| Identity Provider | Microsoft Entra ID |
| Service Provider | VaultBridge |
| SSO Method | SAML 2.0 |
| Identifier (Entity ID) | https://vaultbridge-app.com/saml/metadata |
| Reply URL (ACS URL) | https://vaultbridge-app.com/saml/acs |
| Name ID Format | Email Address |
| Test Users Assigned | Aaron Smith, James Davis |

---

## Build Walkthrough

---

### 🟡 Step 1 — Registered VaultBridge as an Enterprise Application

Navigated to Microsoft Entra ID > Enterprise Applications > Browse Microsoft Entra App Gallery and added **VaultBridge** as a new enterprise application. Confirmed the application registered successfully with an Application ID and Object ID. The Getting Started panel showed the two required next steps — Assign users and groups and Set up single sign-on — confirming the app was ready for SSO configuration.

![VaultBridge App Overview](vaultbridge-app-overview.png)
*VaultBridge Enterprise Application registered in Entra ID — Application ID and Object ID confirmed*

---

### 🔵 Step 2 — Configured SAML-Based Single Sign-On

Navigated to VaultBridge > Single Sign-On > SAML-based Sign-on. Configured the Basic SAML Configuration with the Entity ID and Assertion Consumer Service URL from the Service Provider. These two values establish the federation trust between Entra ID as the IdP and VaultBridge as the SP.

**SAML Configuration Applied:**
- Identifier (Entity ID): https://vaultbridge-app.com/saml/metadata
- Reply URL (ACS URL): https://vaultbridge-app.com/saml/acs
