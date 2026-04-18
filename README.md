# ⚡ PULSE: Zero-Knowledge Biometric Payment Switch

![Status: MVP Validated](https://img.shields.io/badge/Status-MVP%20Validated-success)
![Hardware Target: STM32L4](https://img.shields.io/badge/Hardware%20Target-STM32L4-blue)
![Security: RSA-2048 Edge Encryption](https://img.shields.io/badge/Security-RSA--2048%20Encryption-red)
![License: Proprietary](https://img.shields.io/badge/License-Proprietary-darkgray)

> **🔒 INTELLECTUAL PROPERTY NOTICE:** > This repository is a **Public Architecture Showcase** created for the India Innovates summit. Due to the sensitive nature of financial routing and cryptographic biometric handling, the core microservices engine, mobile UI codebase, and hardware firmware are maintained in strict private repositories. 

## 🌍 The Mission
PULSE is the physical bridge to Digital India. While UPI revolutionized digital payments for smartphone users, 300 million citizens remain locked out. Existing Aadhaar Enabled Payment System (AePS) terminals cost upwards of ₹10,000 and dangerously expose raw biometric data. 

**PULSE solves this by decoupling heavy banking logic from physical hardware.** We have engineered an ultra-secure, edge-encrypted IoT terminal architecture that targets a <₹4,000 manufacturing cost and settles transactions in under 5 seconds.

---

## 🏗️ System Architecture & Target BOM

*Note: To validate our zero-knowledge routing protocol rapidly without capital burn, our current Phase 1 MVP utilizes a mobile-simulated edge environment. The architecture below represents our finalized Bill of Materials (BOM) for physical manufacturing.*

### 1. The Target Edge Terminal (Hardware)
Designed exclusively as a secure capture-and-route gateway. 
* **Target MCU:** STM32L4 (Ultra-low power)
* **Secure Element:** ATECC608A for hardware-level cryptographic attestation.
* **Process:** Optical scanner maps ISO-standard minutiae. The Secure Element instantly generates an **RSA-2048 encrypted PID block**. **The raw fingerprint image is destroyed at the edge.**

### 2. The PULSE Cloud Switch (Microservices Backend)
A Node.js-based routing engine that authenticates identity and settles funds without ever storing user biometric data.

---

## 🔄 The 5-Step Transaction Flow

1. **Initiate:** Merchant generates the bill on the PULSE terminal; customer enters their 10-digit mobile number or selects their bank.
2. **Capture & Encrypt:** Hardware captures liveness/minutiae and instantly generates an RSA-2048 encrypted PID block.
3. **Secure Transmission:** Terminal sends the ultra-light encrypted payload via **embedded NB-IoT (M2M eSIM)** to the PULSE Switch (No Wi-Fi dependency).
4. **Zero-Knowledge Verification:** The Switch queries the simulated UIDAI CIDR (`mock-databases/uidai_vault.json`) to authenticate identity. 
5. **Instant Settlement:** The Switch triggers simulated NPCI rails, debiting the Payer's CBS (`mock-databases/sbi.json`) and crediting the Merchant's CBS.

---

## 📱 Live UI Demonstration

*(Because our proprietary merchant interface is optimized for dedicated touch-based IoT screens, we have captured a live transaction flow below utilizing our simulated edge environment.)*

Click to watch live routing demo 👇
[![PULSE Live Demo](https://img.youtube.com/vi/41Ip6RFHzG4/maxresdefault.jpg)](https://youtu.be/41Ip6RFHzG4)
---

## 📩 Get in Touch
 **🤝 Team Pulse Payments**
 
Built by a team of Computer Engineering students focused on high-leverage infrastructure.

**Kanishk**
* 📧 Email: kanishkpanchal007@gmail.com
  
**Open for Incubation & Strategic Partnerships.**
