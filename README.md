# Dr. Hafiz Anwaar Ahmad Sangra — Official Website

> **Consultant Cardiologist & Heart Specialist (کنسلٹنٹ کارڈیالوجسٹ / ماہر امراضِ قلب)**  
> **MBBS, Dip. Card (UHS)** | Faisalabad, Pakistan

---

## 📋 Overview (تعارف)

Official clinical website for **Dr. Hafiz Anwaar Ahmad Sangra**, Consultant Cardiologist practicing at **Rubina Memorial Hospital**, Batala Colony, Faisalabad, and **Govt. Nusrat Fateh Ali Khan DHQ Hospital**, Faisalabad.

This repository contains the clean, high-performance, accessible, and mobile-responsive production code for the website.

---

## 🚀 Repository Structure (کلین کوڈ کا ڈھانچہ)

```text
├── index.html           # Main landing page & interactive clinical portfolio
├── 404.html             # Custom error 404 page with emergency routing
├── styles.css           # Modern CSS3 styling, responsive grid & typography
├── script.js            # Client-side interactions & performance optimizations
├── _headers             # Production security & cache-control HTTP headers
├── robots.txt           # Search engine indexing directives
├── sitemap.xml          # XML sitemap for SEO discovery
├── favicon.ico          # Browser tab icon
├── images/              # Optimized WebP/PNG production visual assets
│   ├── dr_sangra_executive_headshot_portrait.webp
│   ├── dr_sangra_consultation_desk_with_echocardiography_machine.webp
│   ├── dr_sangra_clinic_entrance_and_standee.webp
│   ├── dr_sangra_clinical_services_standee_banner.webp
│   └── ...
└── .gitignore           # Git ignore rules ensuring only clean code is tracked
```

---

## ⚡ Key Highlights & Features

- **Clean Vanilla Architecture:** Zero bulky dependencies or unnecessary frameworks; pure HTML5, CSS3, and modern JavaScript.
- **Responsive Design:** Fully responsive layout with mobile-first approach, tested for all viewport sizes.
- **Fast Performance:** Optimized WebP imagery, modern typography, zero render-blocking bloat.
- **SEO & Schema.org Ready:** Integrated `MedicalBusiness` and `Physician` JSON-LD structured data for Google Search.
- **Patient Convenience:** Instant WhatsApp and phone booking integrations with OPD timetables.

---

## 🛠️ Local Development & Preview

To preview the website locally:

```bash
# Using Python built-in HTTP server
python -m http.server 8000

# Open in browser:
# http://localhost:8000
```

---

## 🚀 Hostinger Auto-Deployment Methods (ہوسٹنگر پر ڈپلائمنٹ کے دو طریقے)

This repository includes a multi-mode automated GitHub Actions CI/CD pipeline (`.github/workflows/hostinger-deploy.yml`) supporting two deployment methods:

### طریقہ نمبر 1: ہوسٹنگر گٹ ویب ہک (Hostinger hPanel Git — سب سے آسان)
1. لاگ ان کریں **Hostinger hPanel** ➡️ **Websites** ➡️ **Manage**۔
2. بائیں مینو میں **Advanced** ➡️ **Git** پر جائیں۔
3. درج ذیل معلومات درج کریں:
   - **Repository:** `https://github.com/ahs1st/dr-hafiz-anwaar-ahmad.git`
   - **Branch:** `main`
   - **Install directory:** `public_html`
4. **Create** پر کلک کریں۔ ہوسٹنگر آپ کو ایک **Auto-Deployment Webhook URL** دے گا۔
5. اپنے گٹ ہب ریپوزٹری میں جائیں: **Settings** ➡️ **Secrets and variables** ➡️ **Actions** ➡️ **New secret**:
   - **Secret Name:** `HOSTINGER_WEBHOOK_URL`
   - **Value:** ہوسٹنگر سے حاصل کردہ ویب ہک یو آر ایل۔
   
*(اس طریقہ سے ہر گٹ پش پر ہوسٹنگر خودکار طور پر نیا کوڈ فوری پل کر لیتا ہے)*

---

### طریقہ نمبر 2: سیکیور FTPS ٹرانسفر (FTPS Deploy)
اگر آپ FTP/FTPS استعمال کرنا چاہتے ہیں تو گٹ ہب ریپوزٹری سیکرٹس میں درج ذیل ویلیوز شامل کریں:

| Secret Name | Description | Example Value |
| :--- | :--- | :--- |
| `HOSTINGER_FTP_SERVER` | Hostinger FTP Hostname or Server IP | `ftp.yourdomain.com` or `185.xxx.xxx.xxx` |
| `HOSTINGER_FTP_USERNAME` | Hostinger FTP Account Username | `u123456789` or `ftpuser` |
| `HOSTINGER_FTP_PASSWORD` | Hostinger FTP Account Password | `YourSecureFtpPassword` |
| `HOSTINGER_TARGET_DIR` *(Optional)* | Target directory in Hostinger | `public_html/` (Default) |
| `HOSTINGER_FTP_PROTOCOL` *(Optional)* | Secure Transfer Protocol | `ftps` (Default) |


