# Outlook Email Fetcher 📩

## 🚀 Overview
This project allows you to fetch and display emails from your Outlook inbox using the **Microsoft Graph API**. It authenticates via OAuth and retrieves the latest emails, displaying the sender and subject.

## 📌 Features
- ✅ Authenticate via **Microsoft Graph API**
- ✅ Fetch **latest emails** from your inbox
- ✅ Display **sender and subject**
- ✅ Works with **OAuth device flow** (no need for web authentication)

---

## 🔧 Setup & Installation

### 1️⃣ **Register an Azure AD App**
1. Go to [Microsoft Azure Portal](https://portal.azure.com/)
2. Navigate to **Azure Active Directory** → **App registrations**
3. Click **New registration**, give it a name, and select **Accounts in this organization directory only**
4. Copy **Client ID** and **Tenant ID**
5. Add **API Permissions** → `Mail.Read` under Microsoft Graph
6. **Grant Admin Consent**

### 2️⃣ **Clone the Repository**
```bash
  git clone https://github.com/yourusername/outlook-email-fetcher.git
  cd outlook-email-fetcher
```

### 3️⃣ **Install Dependencies**
```bash
  pip install requests msal
```

### 4️⃣ **Set Up Environment Variables**
Replace placeholders in `outlook_email_fetcher.py` with your actual **CLIENT_ID** and **TENANT_ID**:
```python
CLIENT_ID = "your-client-id"
TENANT_ID = "your-tenant-id"
```

### 5️⃣ **Run the Script**
```bash
  python outlook_email_fetcher.py
```

**Follow the authentication steps** (device login flow) and fetch your latest emails!

---

## 📚 How It Works
1. Uses **MSAL (Microsoft Authentication Library)** for OAuth authentication
2. Retrieves an **access token** via **device flow**
3. Queries Microsoft Graph API for **recent emails**
4. Displays **sender and subject** in the console

---

## 🛠 Future Enhancements
- 🔍 **Filter emails by sender, date, or keyword**
- 📊 **Analyze email activity trends**
- 🤖 **AI-powered email summarization**

---

## 🤝 Contributing
1. Fork the repository
2. Make your changes
3. Submit a pull request 🎯

---

### 🌟 Star this project if you find it useful!
