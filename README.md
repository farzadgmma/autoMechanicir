<div dir="rtl" align="center">

# 🚗 اکوسیستم هوشمند مکانیک خودرو (AutoMechanic AI)
### سامانه جامع عیب‌یابی دیاگ هوش مصنوعی، مارکت‌پلیس خدمات تخصصی و پایش سلامت خودرو

[![Release](https://img.shields.io/badge/Release-v1.0.0--Pilot-blue?style=for-the-badge&logo=android)](https://automichanic.mobtakerai.ir/download)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20Web-green?style=for-the-badge)](https://automichanic.mobtakerai.ir)
[![Engine](https://img.shields.io/badge/AI%20Engine-Multi--Model%20RAG%20%2B%20Vision-purple?style=for-the-badge)](https://automichanic.mobtakerai.ir/invest/)
[![Security](https://img.shields.io/badge/Security-Strict%20Sandbox%20%2B%20HMAC-red?style=for-the-badge)](SECURITY.md)

[🌐 وب‌سایت و وایت‌پیپر](https://automichanic.mobtakerai.ir/) • 
[📥 دانلود مستقیم اپلیکیشن](https://automichanic.mobtakerai.ir/download/) • 
[📄 مشخصات فنی و معماری](SPECIFICATIONS.md) • 
[English Section](#-english-overview)

---

</div>

## 🇮🇷 درباره پروژه (Persian Overview)

پروژه **AutoMechanic AI** اولین پلتفرم جامع و بومی خدمات هوشمند خودرو در ایران است که تلفیقی از **هوش مصنوعی پیشرفته چندوجهی (Multi-Modal AI)**، **اتصال بلادرنگ به پورت دیاگ (OBD-II / CAN-Bus)** و **مارکت‌پلیس مناقصه خدمات تعمیراتی** را ارائه می‌دهد.

این سیستم با هدف حذف واسطه‌های غیرضروری، شفاف‌سازی کامل هزینه‌ها، ارائه دیاگ تخصصی برای عموم رانندگان و تضمین کیفیت قطعات و دستمزدها طراحی و پیاده‌سازی شده است.

---

### 🌟 قابلیت‌های کلیدی نسخه ۱.۰.۰ (Pilot Edition)

1. **عیب‌یابی هوشمند چندوجهی (Multi-Modal Diagnostics):**
   - تحلیل توصیف صوتی/متنی راننده با مدل‌های پردازش زبان طبیعی
   - خواندن کدهای خطا (DTC) از طریق پورت OBD-II با دانشنامه جامع خودروهای داخلی و مونتاژی (ایران خودرو، سایپا، چینی و وارداتی)
   - تحلیل چشمی تصاویر موتور، قطعات و علائم هشدار کیلومترشمار
2. **مارکت‌پلیس مناقصه تعمیرات و خدمات (Reverse Auction Marketplace):**
   - ارسال درخواست خدمت به مکانیک‌های معتمد محدوده
   - مقایسه بلادرنگ پیش‌فاکتورها بر اساس قیمت، امتیاز و فاصله
3. **پروتکل پذیرش دیجیتال و تحویل با امضای یکبارمصرف (OTP Signoff):**
   - ثبت چک‌لیست سلامت بدنه و متعلقات خودرو هنگام تحویل به تعمیرگاه
   - لاگ مرحله‌به‌مرحله فرآیند تعمیر و تعویض قطعه همراه با تصویر
   - امضای رمزنگاری‌شده دیجیتال توسط مالک خودرو برای پایان خدمت و فعال‌سازی گارانتی
4. **تضمین گارانتی خدمات و حل اختلاف هوشمند:**
   - صدور کد یکتای ضمانت خدمت در پایان هر سفارش
   - پنل داوری و پایش متمرکز برای رسیدگی به شکایات احتمالی

---

## 📥 دانلود و نصب اپلیکیشن اندروید (Official Release v1.0.0)

| مشخصه | مقدار |
|---|---|
| **نسخه** | `1.0.0 (Canary Pilot Release)` |
| **نام بسته** | `com.automechanic.mobile` |
| **حجم فایل** | `56.18 مگابایت` |
| **سیستم‌عامل هدف** | اندروید 8.0 به بالا (Android Oreo+) |
| **هش اعتبارسنجی (SHA-256)** | `96c41422d54cde3924faba87f6c7c8aa01121fb3922870dad594318f45ab191d` |

### لینک‌های دریافت:
- 🚀 **[دانلود مستقیم نسخه پایلوت (سرور رسمی)](https://automichanic.mobtakerai.ir/download/automechanic-latest.apk)**
- 📱 **[صفحه اختصاصی راهنمای گام‌به‌گام نصب](https://automichanic.mobtakerai.ir/download/)**
- 📦 **[بخش Releases در گیت‌هاب](../../releases/tag/v1.0.0)**

---

<div dir="ltr">

## 🇬🇧 English Overview

### AutoMechanic AI — Intelligent Vehicle Diagnostic & Service Ecosystem

**AutoMechanic AI** is an enterprise-grade automotive ecosystem combining telematics edge-diagnostics, multi-modal generative AI, and a decentralized reverse-auction service marketplace.

### System Architecture Highlights
- **Client Layer**: Flutter 3.47.0 high-performance reactive mobile application with offline-first caching and telemetry synchronization.
- **Backend Architecture**: High-throughput FastAPI asynchronous microservices with PostgreSQL (ACID relational domain) and TimescaleDB for telematics series.
- **Security & Integrity**: Zero-trust API gateway, HMAC request verification, and cryptographic OTP signoff for physical vehicle checkout.
- **Payment Sandbox**: During the Phase 13 Pilot Rollout, all payment rails are hard-gated to sandbox validation (`LIVE_PAYMENT_ENABLED=false`).

---

### Verification & Checksum
You can verify the authenticity of downloaded APK binaries using PowerShell or bash:

```bash
# Linux / macOS
sha256sum automechanic-latest.apk

# Windows PowerShell
Get-FileHash automechanic-latest.apk -Algorithm SHA256
```
**Expected Digest**: `96c41422d54cde3924faba87f6c7c8aa01121fb3922870dad594318f45ab191d`

---

## 🏛 Intellectual Property & Source Code Notice

This repository serves as the **official public showcase, technical documentation, and distribution channel** for the AutoMechanic AI ecosystem. 
In accordance with enterprise IP governance, the core proprietary inference models, custom diagnostic heuristics, and internal infrastructure configurations are maintained in private repositories. Public users, testers, and investors are welcome to review specifications, submit issues, and install official releases.

---

## 🤝 Management & Investor Relations

For investment inquiries, partnership proposals, or technical feedback, connect directly with the executive team:

- **Telegram**: [@Farzadasaadi](https://t.me/Farzadasaadi)
- **Bale Messenger**: [https://ble.ir/mobtakerai1](https://ble.ir/mobtakerai1)
- **Instagram**: [@mobtakerAi](https://instagram.com/mobtakerAi)
- **Email**: `info@mobtakerai.ir`
- **Whitepaper**: [https://automichanic.mobtakerai.ir/invest/](https://automichanic.mobtakerai.ir/invest/)

---
<div align="center">
  <sub>© 2026 AutoMechanic AI & MobtakerAI Ecosystem. All Rights Reserved.</sub>
</div>
</div>
