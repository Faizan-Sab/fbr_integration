# FBR Integration for ERPNext

🇵🇰 **Pakistan Federal Board of Revenue (FBR) Integration for ERPNext**

Complete ERP solution for FBR compliance, e-invoicing, and tax reporting.

## 📦 What's Included

### DocTypes (12)
- HS Code
- FBR UoM
- Sale Type
- Buyer Province
- Tax Payer Type
- Invoice Type
- Scenario ID
- SRO Schedule No
- SRO Item SNo
- And 3 more...

### Custom Fields (60)
Automatically adds FBR-required fields to:
- **Sales Invoice** (15+ fields)
- **Sales Invoice Item** (10+ fields)
- **Item Master** (10+ fields)
- **Customer** (5+ fields)
- And other DocTypes

### Scripts
- **2 Client Scripts**: Frontend validation and calculations
- **Server Scripts**: Backend tax calculations and FBR API integration

### Other Customizations
- **3 Property Setters**: Field property modifications
- **Print Formats**: FBR-compliant invoice printing
- **Notifications**: Automated alerts
- **Workspace**: Dedicated FBR workspace

---

## 🚀 Installation

### Prerequisites
- ERPNext v14 or v15
- Frappe Framework
- Python 3.10+

### Step 1: Get the App
```bash
cd /path/to/frappe-bench
bench get-app https://github.com/Faizan-Sab/fbr_integration.git
```

### Step 2: Install on Site
```bash
bench --site your-site-name install-app fbr_integration
```

### Step 3: Migrate Database
```bash
bench --site your-site-name migrate
```

### Step 4: Clear Cache & Restart
```bash
bench --site your-site-name clear-cache
bench restart
```

---

## ✅ Post-Installation Verification

After installation, verify these are created:

1. **Check DocTypes**: Search for "HS Code", "FBR UoM", etc.
2. **Check Custom Fields**: Open Sales Invoice, you should see FBR fields
3. **Check Workspace**: Look for "FBR Integration" workspace
4. **Check Scripts**: Go to Client Script List, you should see FBR scripts

---

## 📊 Features

### 1. **E-Invoicing**
- Generate FBR-compliant invoices
- Automatic QR code generation
- Real-time submission to FBR portal

### 2. **Tax Calculations**
- Automated sales tax computation
- Support for multiple tax scenarios
- SRO (Statutory Regulatory Order) compliance

### 3. **Master Data Management**
- 7000+ HS Codes pre-loaded
- Province and tax payer type management
- Unit of measurement mappings

### 4. **Reporting**
- FBR-compliant reports
- Tax summaries
- Audit trails

---

## ⚙️ Configuration

### 1. FBR API Settings

Go to: **FBR Integration Settings**

Configure:
- API URL
- API Credentials
- Certificate paths
- Tax rates

### 2. Company Setup

Ensure your Company has:
- Valid NTN (National Tax Number)
- STRN (Sales Tax Registration Number)
- Complete address with province

### 3. Item Master

For each item, set:
- HS Code
- FBR UoM
- Sale Type
- SRO details (if applicable)

---

## 📖 Usage Guide

### Creating FBR-Compliant Invoice

1. **Create Sales Invoice**
2. **Fill Customer Details**:
   - Customer NTN
   - Province
   - Tax Payer Type

3. **Add Items** with:
   - HS Code
   - FBR UoM
   - Sale Type

4. **Tax Calculation**: Auto-calculated based on configuration

5. **Submit Invoice**: Click "Send to FBR"

6. **Get Response**: FBR Invoice Number and QR Code generated

---

## 🐛 Troubleshooting

### Issue: Custom Fields Not Showing
```bash
bench --site your-site clear-cache
bench restart
```

### Issue: DocTypes Not Created
```bash
bench --site your-site migrate --skip-failing
bench --site your-site clear-cache
```

### Issue: HS Code Data Missing

The HS Code data should be automatically imported. If not, check fixture files exist:
```bash
ls -la apps/fbr_integration/fbr_integration/fixtures/hs_code.json
```

To manually import:
```bash
bench --site your-site console
```
```python
import frappe
frappe.reload_doc('fbr_integration', 'doctype', 'hs_code')
```

### Issue: Scripts Not Working

Clear cache and rebuild:
```bash
bench --site your-site clear-cache
bench build --app fbr_integration
bench restart
```

---

## 🔄 Uninstalling
```bash
bench --site your-site uninstall-app fbr_integration --yes --force
```

**Warning**: This will remove all custom fields and data!

---

## 📁 Project Structure
```
fbr_integration/
├── fbr_integration/
│   ├── fbr_integration/
│   │   └── doctype/          # All 12 DocTypes
│   ├── fixtures/              # Exported customizations
│   │   ├── custom_field.json
│   │   ├── doctype.json
│   │   ├── client_script.json
│   │   ├── server_script.json
│   │   ├── hs_code.json
│   │   └── ...
│   ├── hooks.py               # App hooks and fixtures
│   ├── fbr_api.py            # FBR API integration
│   └── handler.py            # Event handlers
├── README.md
├── license.txt
└── pyproject.toml
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📝 License

MIT License - See [LICENSE](license.txt)

---

## 🆘 Support

- **Issues**: https://github.com/Faizan-Sab/fbr_integration/issues
- **Discussions**: https://github.com/Faizan-Sab/fbr_integration/discussions

---

## 📋 Changelog

### Version 1.0.0 (Initial Release)
- ✅ 12 DocTypes for FBR compliance
- ✅ 60 Custom Fields across ERPNext
- ✅ Client and Server Scripts
- ✅ 7000+ HS Codes pre-loaded
- ✅ FBR API integration
- ✅ QR Code generation
- ✅ Tax calculations

---

## 👨‍💻 Developer

**Faizan Sabir**
- GitHub: [@Faizan-Sab](https://github.com/Faizan-Sab)

---

## 🌟 Star This Repo

If this app helped you, please ⭐ star this repository!

---

**Made with ❤️ for Pakistani ERPNext Community**
