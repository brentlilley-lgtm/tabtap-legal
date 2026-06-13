# TabTap — Google Play Data Safety Form Answers

Pre-filled answers for the Google Play Console Data Safety form, consistent with the
privacy policy at https://tabtap.co/privacy.

Open **Play Console → App content → Data safety** and work through each section below.

> **Note on "sharing" vs. "service providers":** Google's form treats a transfer to a
> *service provider* that processes data on your behalf as **not** "sharing." TabTap uses
> Anthropic (receipt reading), Supabase (share-link storage), and Sentry (crash reports)
> strictly as service providers, so the rows below mark **Shared: No** and name the
> processor in the notes. Confirm this stance is how you want to represent it before submitting.

---

## 1. Overview

### Does your app collect or share any of the required user data types?

> **Yes**

### Does your app use data encryption in transit?

> **Yes — all data transmitted is encrypted (HTTPS)**

### Do you provide a way for users to request that their data be deleted?

> **Yes**

*Share-link data deletes automatically (receipt photo ~1 hour after a split is finalized and within 24 hours in all cases; the rest of the split record within 48 hours). Users can also email tabtapap@gmail.com to delete a specific shared split or crash reports, and remove all on-device data by uninstalling.*

---

## 2. Data Types

### Personal info

| Sub-type | Collected? | Shared? | Notes |
|---|---|---|---|
| Name | **Yes** | **No** | Owner's name and (for shared splits) guests' chosen display names. Stored in the cloud only for share links, deleted within 48h. Processed by Supabase (service provider). |
| Email address | **No** | **No** | Only if a user enters their own email as a PayPal/Zelle handle (see "Other"). |
| User IDs | **No** | **No** | No accounts, no login. |
| Phone number | **No** | **No** | Only if a user enters their own phone as a Zelle handle (see "Other"). |
| Other (payment handles) | **Yes** | **No** | Venmo/PayPal/Zelle/Cash App handles the owner chooses to include. On-device by default; included in a shared split only if the owner sends a link. Deleted within 48h. |

### Financial info

| Sub-type | Collected? | Shared? | Notes |
|---|---|---|---|
| User payment info | **No** | **No** | Apple/Google handle payment. TabTap never sees card or bank details. |
| Purchase history | **Yes** | **No** | Apple/Google confirm whether a $0.50 split-pass was purchased. |
| Other financial info | **No** | **No** | |

### Photos and videos

| Sub-type | Collected? | Shared? | Notes |
|---|---|---|---|
| Photos | **Yes** | **No** | Receipt photo. Sent to our server + Anthropic to read items (not retained after reading; not used for model training). For share links, also stored privately in Supabase and deleted within 24h. Processed by service providers. |
| Videos | **No** | **No** | |

### App activity

| Sub-type | Collected? | Shared? | Notes |
|---|---|---|---|
| App interactions | **Yes** | **No** | Sentry captures a short breadcrumb trail before a crash. Only if Sentry is configured. |
| Other actions | **No** | **No** | |

### App info and performance

| Sub-type | Collected? | Shared? | Notes |
|---|---|---|---|
| Crash logs | **Yes** | **No** | Sent to **Sentry** (service provider) when configured. No personal data, receipt content, or screenshots. |
| Diagnostics | **Yes** | **No** | Same as crash logs. |

### Device or other IDs

| Sub-type | Collected? | Shared? |
|---|---|---|
| Device or other IDs | **No** | **No** |

---

## 3. Data Usage and Handling

### Personal info → Name
- Collected · Processed by Supabase (service provider) · Stored for shared splits, deleted within 48h · Optional · Purpose: **App functionality**

### Personal info → Other (payment handles)
- Collected · On-device by default; stored in a shared split (deleted within 48h) · Optional · Purpose: **App functionality**

### Financial info → Purchase history
- Collected · Ephemeral · Required · Purpose: **App functionality**

### Photos → Photos
- Collected · Processed by Anthropic to read the receipt (not retained); stored privately in Supabase for share links and deleted within 24h · Required · Purpose: **App functionality**

### App activity → App interactions
- Collected · Ephemeral · Optional (only when Sentry configured) · Purpose: **Analytics / crash diagnostics**

### App info → Crash logs + Diagnostics
- Collected · Processed by Sentry · Retained 90 days · Optional (when Sentry configured) · Purpose: **App functionality / diagnostics**
- Processor: Sentry (https://sentry.io) — stack traces, app version, device model, OS version, breadcrumb trails only. NO receipt photos, parsed text, names, or payment handles.

---

## 4. Additional Declarations

- **Advertising ID:** No
- **Families Policy:** N/A (target audience is 18+)
- **Contains ads:** No
- **Location for ads:** No

---

## 5. Privacy Policy URL

> **https://tabtap.co/privacy**

---

## Pre-Submit Checklist

- [ ] Privacy policy URL resolves (test in incognito)
- [ ] Privacy policy names Anthropic, Supabase, Vercel, and Sentry and links to each policy
- [ ] Privacy policy describes cloud receipt reading and share-link storage
- [ ] Privacy policy states the retention model (photo ~1h/24h, record 48h)
- [ ] Privacy policy mentions Google Play Billing and the $0.50 IAP
- [ ] Contact email (tabtapap@gmail.com) is listed in the privacy policy
- [ ] "Contains ads" is set to No in the Store Listing
- [ ] "In-app purchases" is set to Yes ($0.50 consumable) in the Store Listing
