# 📊 n8n — Google Sheets & Gmail Integration Guide

> n8n এ Google Sheets ও Gmail সংযুক্ত করে Workflow তৈরির ধাপে ধাপে গাইড।

🔗 **পূর্বশর্ত:** আগে [n8n OAuth2 Setup](https://github.com/Omarmdwasimuddin/n8n-OAuth-02) সম্পন্ন করো।

---

## 🌐 Google Cloud — নতুন API Enable করো

### ✅ ধাপ ১ — Google Drive API Enable করো

🔗 [console.cloud.google.com](http://console.cloud.google.com/) এ যাও।
**"Google Drive API"** সার্চ করো এবং Enable করো।

![Google Drive API](https://imgur.com/XPHPEAe.png)

---

### ✅ ধাপ ২ — Gmail API Enable করো

একইভাবে **"Gmail API"** সার্চ করো এবং Enable করো।

![Gmail API](https://imgur.com/TXwLZ1E.png)

---

## 📋 Google Sheets — Workflow সেটআপ

### ✅ ধাপ ৩ — Google Sheets Node যোগ করো

- নতুন **Workflow** তৈরি করো
- **Nodes Panel** ওপেন করো
- **"Google Sheets"** সার্চ করো
- **"On row added"** সিলেক্ট করো
- **"Set up credential"** এ ক্লিক করো

![Google Sheets Node](https://imgur.com/j8xlkjv.png)

---

### ✅ ধাপ ৪ — OAuth Client তৈরি করো (Sheets এর জন্য)

🔗 [console.cloud.google.com](http://console.cloud.google.com/) এ যাও এবং নিচের ধাপ অনুসরণ করো:

```
APIs & Services
    └── Credentials
         └── OAuth client ID
              ├── Application type: Web application
              ├── Name: যা আছে রাখো
              └── Authorized redirect URIs → Add URIs
```

### ✅ ধাপ ৫ — OAuth Redirect URL কপি করো

![Copy OAuth Redirect URL](https://imgur.com/W4zzXoc.png)

> কপি করা URL টি **Authorized redirect URIs** এ Paste করো এবং **Create** বাটনে ক্লিক করো।

---

### ✅ ধাপ ৬ — Client ID ও Client Secret কপি করো

![Copy Client ID & Secret](https://imgur.com/z1K2JD5.png)

### ✅ ধাপ ৭ — Client ID ও Client Secret Paste করো

![Paste Credentials](https://imgur.com/hzEXLWt.png)

---

### ✅ ধাপ ৮ — Google Sign-In সম্পন্ন করো

নিচের ধাপগুলো একে একে করো:

1. **Sign in with Google** বাটনে ক্লিক করো
2. **Advanced** এ ক্লিক করো
3. **Go to n8n (unsafe)** এ ক্লিক করো
4. **Select all** করো এবং **Continue** বাটনে ক্লিক করো

---

### ✅ ধাপ ৯ — Document ও Sheet সেট করো

তোমার Google Spreadsheet ও Sheet সিলেক্ট করো।

![Set Document & Sheet](https://imgur.com/qNsGy04.png)

---

## 📧 Gmail — Workflow সেটআপ

### ✅ ধাপ ১০ — Gmail Node যোগ করো

- **Nodes Panel** ওপেন করো
- **"Gmail"** সার্চ করো
- **"Send a message"** সিলেক্ট করো
- **"Set up credential"** এ ক্লিক করো

![Gmail Node](https://imgur.com/GwMsrXi.png)

---

### ✅ ধাপ ১১ — OAuth Client তৈরি করো (Gmail এর জন্য)

🔗 [console.cloud.google.com](http://console.cloud.google.com/) এ যাও এবং একইভাবে:

```
APIs & Services
    └── Credentials
         └── OAuth client ID
              ├── Application type: Web application
              ├── Name: যা আছে রাখো
              └── Authorized redirect URIs → Add URIs
```

### ✅ ধাপ ১২ — OAuth Redirect URL কপি করো

![Copy OAuth Redirect URL](https://imgur.com/XaXJ8Eb.png)

> কপি করা URL টি **Authorized redirect URIs** এ Paste করো এবং **Create** বাটনে ক্লিক করো।

---

### ✅ ধাপ ১৩ — Client ID ও Client Secret কপি করো

![Copy Client ID & Secret](https://imgur.com/W65Dods.png)

### ✅ ধাপ ১৪ — Client ID ও Client Secret Paste করো

![Paste Credentials](https://imgur.com/rUvJRlf.png)

---

### ✅ ধাপ ১৫ — Google Sign-In সম্পন্ন করো

একইভাবে নিচের ধাপগুলো করো:

1. **Sign in with Google** বাটনে ক্লিক করো
2. **Advanced** এ ক্লিক করো
3. **Go to n8n (unsafe)** এ ক্লিক করো
4. **Select all** করো এবং **Continue** বাটনে ক্লিক করো

---

## ▶️ Workflow চালাও

### ✅ ধাপ ১৬ — Value দাও এবং Execution Step চালাও

প্রয়োজনীয় Value পূরণ করো এবং **Execution Step** বাটনে ক্লিক করো।

![Execution Step 1](https://imgur.com/AF7nxUc.png)
![Execution Step 2](https://imgur.com/DKJkit2.png)

> ✔️ Workflow সফলভাবে চললে Google Sheets এ নতুন Row যোগ হলে স্বয়ংক্রিয়ভাবে Gmail এ Email পাঠানো হবে।

---

## 📋 Quick Reference

| ধাপ | কাজ | কোথায় |
|-----|-----|--------|
| ১ | Google Drive API Enable | Google Cloud |
| ২ | Gmail API Enable | Google Cloud |
| ৩ | Google Sheets Node যোগ | n8n |
| ৪–৫ | OAuth Client তৈরি (Sheets) | Google Cloud |
| ৬–৭ | Client ID & Secret সংযুক্ত | n8n |
| ৮ | Google Sign-In (Sheets) | Browser |
| ৯ | Document & Sheet সেট | n8n |
| ১০ | Gmail Node যোগ | n8n |
| ১১–১২ | OAuth Client তৈরি (Gmail) | Google Cloud |
| ১৩–১৪ | Client ID & Secret সংযুক্ত | n8n |
| ১৫ | Google Sign-In (Gmail) | Browser |
| ১৬ | Workflow Execute | n8n |

---

*এই Workflow সেটআপ করলে Google Sheets এ নতুন ডেটা যোগ হওয়া মাত্র Gmail থেকে স্বয়ংক্রিয়ভাবে Email পাঠানো যাবে।*
