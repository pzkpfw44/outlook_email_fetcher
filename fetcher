import requests
import webbrowser
from msal import PublicClientApplication

# Azure AD App Details (Replace with your app details)
CLIENT_ID = "your-client-id"
TENANT_ID = "your-tenant-id"
AUTHORITY = f"https://login.microsoftonline.com/{TENANT_ID}"
SCOPES = ["https://graph.microsoft.com/Mail.Read"]

# Create an MSAL App
app = PublicClientApplication(CLIENT_ID, authority=AUTHORITY)

def get_access_token():
    accounts = app.get_accounts()
    if accounts:
        result = app.acquire_token_silent(SCOPES, account=accounts[0])
    else:
        flow = app.initiate_device_flow(scopes=SCOPES)
        print(flow["message"])
        webbrowser.open(flow["verification_uri"])
        result = app.acquire_token_by_device_flow(flow)
    return result.get("access_token")

def fetch_emails():
    token = get_access_token()
    if not token:
        print("Authentication failed.")
        return
    
    url = "https://graph.microsoft.com/v1.0/me/messages"
    headers = {"Authorization": f"Bearer {token}"}
    response = requests.get(url, headers=headers)
    
    if response.status_code == 200:
        emails = response.json().get("value", [])
        for email in emails[:5]:  # Fetch first 5 emails
            print(f"From: {email['from']['emailAddress']['name']} - {email['subject']}")
    else:
        print("Failed to fetch emails:", response.json())

if __name__ == "__main__":
    fetch_emails()
