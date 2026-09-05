# ⚙️ AutoMechanic AI — Technical Specifications & System Architecture

## 1. Overview
This document outlines the technical architecture, communication protocols, hardware compatibility, and deployment topologies governing the **AutoMechanic AI** ecosystem.

---

## 2. Technology Stack

| Layer | Component | Technology / Framework | Specifications |
|---|---|---|---|
| **Mobile Client** | Driver & Mechanic App | Flutter 3.47.0 / Dart | Material 3, RTL native, SQLite local cache, Dio HTTP client |
| **Edge Gateway** | CDN & Reverse Proxy | Cloudflare Enterprise Edge + Nginx | SSL termination, HTTP/2, DDoS protection, Rate limiting |
| **Core Backend** | Application Services | FastAPI (Python 3.11+) | Async/await ASGI, Pydantic v2 schemas, SQLAlchemy 2.0 ORM |
| **Database** | Relational & Telematics | PostgreSQL 16 + TimescaleDB | ACID transactions, Row-level security, Spatial PostGIS |
| **Object Storage**| Media & Artifacts | Cloudflare R2 (S3-Compatible) | Zero egress fees, presigned URLs for repair attachments |
| **Queue / Cache** | Async Tasks & State | Redis 7 + Celery / ARQ | Push notification dispatch, session state, OTP tokens |

---

## 3. OBD-II & Telematics Interface Specifications

- **Protocol Support**:
  - ISO 15765-4 (CAN-Bus, 11-bit / 29-bit, 250 kbaud / 500 kbaud)
  - ISO 14230-4 (KWP2000)
  - ISO 9141-2 (Asian & European legacy)
  - SAE J1850 (PWM / VPW)
- **Adapter Compatibility**:
  - ELM327 Bluetooth v1.5 / v2.1
  - OBDLink MX+ / LX Bluetooth Low Energy (BLE)
  - Custom IoT CAN-Bridge (ESP32 telemetry module)
- **Supported PIDs**:
  - Mode 01 (Live sensor data: RPM, Coolant Temp, Fuel Pressure, MAF, O2 Sensor)
  - Mode 03 / Mode 07 (Active and Pending Diagnostic Trouble Codes - DTC)
  - Mode 04 (Clear diagnostic codes and reset check engine indicator)
  - Mode 09 (Vehicle Information / VIN retrieval)

---

## 4. Service Order & Signoff State Machine

The order lifecycle adheres to a deterministic, tamper-evident state machine:

```
[DRAFT] 
   └──> [QUOTED] 
           └──> [AWAITING_USER_CONFIRMATION] 
                   └──> [CONFIRMED] 
                           └──> [IN_SERVICE] (Check-in Checklist + Logs)
                                   └──> [AWAITING_USER_SIGNOFF] (OTP Verification)
                                           └──> [COMPLETED] (Warranty Issued)
```

- **Cryptographic Signoff**:
  When a vehicle is checked out, the driver enters an HMAC-SHA256 one-time code (OTP). This permanently commits the invoice line items, odometer reading, and warranty identifier into the immutable vehicle history ledger.

---

## 5. Security & Isolation Matrix

- **Sandbox Gating**:
  Financial endpoints default to sandbox mode during the pilot deployment (`LIVE_PAYMENT_ENABLED=false`).
- **IP Protection**:
  Proprietary machine learning models and internal diagnostic knowledge matrices remain isolated on air-gapped or VPC-internal service nodes.
