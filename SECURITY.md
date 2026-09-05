# 🛡️ Security Policy — AutoMechanic AI

## Reporting Security Issues

We take the security of our platform and user telemetry extremely seriously. If you identify a potential security vulnerability or sensitive data leak:

1. **Do not disclose publicly** in GitHub issues or discussions.
2. Email full technical details, proof-of-concept steps, and impact assessment directly to:
   - **Email**: `security@mobtakerai.ir`
   - **Direct Management Telegram**: [@Farzadasaadi](https://t.me/Farzadasaadi)
3. You will receive an acknowledgment within 24 hours and regular status updates until resolution.

---

## Architecture & Data Protection Controls

- **Zero-Trust Telematics Ingestion**: All OBD-II telemetry transmitted over cellular connections uses TLS 1.3 encryption with certificate pinning on mobile devices.
- **Role-Based Access Control (RBAC)**: Fine-grained permissions segregate Driver, Mechanic/Vendor, and Administrator access layers.
- **Financial Sandbox Constraint**: In accordance with the project's Master Operating Protocol (Phase 13 Pilot Rollout), real-world automated bank deductions remain strictly disabled (`LIVE_PAYMENT_ENABLED=false`). All pilot payments are validated against isolated sandbox ledger accounts.
- **Tamper-Evident Logs**: Repair steps, check-in checklists, and customer sign-off timestamps are cryptographically hashed upon order finalization.
