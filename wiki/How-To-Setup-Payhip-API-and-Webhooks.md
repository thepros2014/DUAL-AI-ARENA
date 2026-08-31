# 💳 DUAL-AI-ARENA — Payhip API & Webhook Setup Guide
**Automated License Key Provisioning, Webhook Handlers & Instant In-App Unlocks**

🛒 **Official Store Link**: [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)

---

## 📌 1. Architecture Overview

When customers purchase **DUAL-AI-ARENA** on Payhip, license keys are automatically generated and verified through our dual online/offline cryptographic system:

```
                          ┌───────────────────────────┐
                          │   CUSTOMER CHECKOUT       │
                          │   https://payhip.com/b/Tfz7D│
                          └─────────────┬─────────────┘
                                        │
                         [Payhip Webhook 'paid' Event]
                                        │
                                        ▼
                          ┌───────────────────────────┐
                          │   DUAL-AI-ARENA WEBHOOK   │
                          │   POST /api/webhooks/payhip│
                          └─────────────┬─────────────┘
                                        │
           ┌────────────────────────────┴────────────────────────────┐
           ▼                                                         ▼
  [SIGNATURE VERIFIED]                                      [DPAPI ENCRYPTED]
  - Validates Payhip signature header                       - Machine ID Binding (SHA256)
  - Matches Product Permalink "Tfz7D"                       - Persists to license.enc
           │                                                         │
           └────────────────────────────┬────────────────────────────┘
                                        ▼
                          ┌───────────────────────────┐
                          │    UNLIMITED ENTERPRISE   │
                          │    IMMEDIATELY ACTIVATED  │
                          └───────────────────────────┘
```

---

## ⚙️ 2. Configuring Payhip Webhooks in the Payhip Dashboard

### Step 1: Access Developer Settings
1. Log into your [Payhip Dashboard](https://payhip.com/).
2. Click **Account** (top-right) ➔ **Settings**.
3. Select the **Developer** tab.

### Step 2: Add Webhook Endpoint
1. Under **Webhooks**, click **Add Webhook**.
2. Enter your server's webhook URL:
   ```
   https://your-domain.com/api/webhooks/payhip
   ```
   *(Or for local desktop testing: `http://127.0.0.1:5000/api/webhooks/payhip`)*
3. Select Events: Check **"Paid"** (triggers on successful customer purchase).
4. Copy the generated **Webhook Secret Key** (e.g. `payhip_sec_...`).

---

## 🛠️ 3. Environment Variables & App Configuration

Set the following optional environment variables in your server or local environment:

| Environment Variable | Description | Example / Default |
| :--- | :--- | :--- |
| `PAYHIP_WEBHOOK_SECRET` | Secret token used to verify `X-Payhip-Signature` headers. | `payhip_sec_xxxxxxxxxxxx` |
| `PAYHIP_API_KEY` | Payhip Developer API Key for outbound license querying. | `payhip_api_xxxxxxxxxxxx` |
| `PAYHIP_PRODUCT_ID` | Product permalink for DualAI Arena. | `Tfz7D` |

---

## 📬 4. Webhook Payload Schema

Payhip sends a standard JSON payload upon checkout:

```json
{
  "type": "paid",
  "id": "txn_987654321",
  "email": "enterprise-buyer@acmecorp.com",
  "product_id": "Tfz7D",
  "product_name": "DualAI MID Arena - Enterprise Pro",
  "license_key": "DUALAI-ENT-9A8B-7C6D-5E4F-3G2H",
  "price": "99.00",
  "currency": "USD",
  "signature": "payhip_sec_xxxxxxxxxxxx"
}
```

### Supported In-App API Endpoints:
- `POST /api/webhooks/payhip` (Payhip Webhook Receiver)
- `POST /api/license/activate` (In-App Manual Key Activation)
- `GET /api/license/status` (Current Trial / Enterprise State)

---

## 🧪 5. Testing the Integration

We provide an automated test script to verify your Payhip webhook integration:

```powershell
pwsh .\scripts\test-payhip-webhook.ps1
```

**Test Output**:
```
1. Checking initial license status...
  Edition: Free (2 Max Turns)
2. Dispatching simulated Payhip 'paid' Webhook event...
  Webhook Response Status: activated
  Activated Edition: Enterprise
3. Verifying updated in-app license status...
  Edition: Enterprise (Max Turns: 999999)
  RESULT: 100% PASSED!
```

---

## 🔒 6. Air-Gapped & Offline Verification Fallback

If the customer operates in a **100% air-gapped corporate network without internet access**:
1. The customer enters their Payhip-issued key (`DUALAI-ENT-XXXX-...`) directly in the app.
2. DUAL-AI-ARENA validates the key offline via hardware Machine ID binding and DPAPI storage.
3. Zero outbound calls to Payhip or third-party servers are required.

---

- 🛒 **Official Payhip Store Checkout**: [https://payhip.com/b/Tfz7D](https://payhip.com/b/Tfz7D)
- 📖 **User Manual**: [MANUAL.md](https://github.com/thepros2014/DUAL-AI-ARENA-Discussions/blob/main/MANUAL.md)
- 💬 **Community Discussions**: [https://github.com/thepros2014/DUAL-AI-ARENA-Discussions/discussions](https://github.com/thepros2014/DUAL-AI-ARENA-Discussions/discussions)
