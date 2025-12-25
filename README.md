##Authica 🔐

Authica is an integrated access provisioning platform that connects a locally hosted Python-based chatbot with Red Hat Ansible, ServiceNow, and Microsoft Windows Active Directory Domain Services (AD DS) to automate and govern identity and access management workflows.

The project is designed for enterprise environments that require secure, auditable, and automated access provisioning without relying on cloud-hosted AI services.

🚀 Features

🤖 Local Python Chatbot
- Runs fully on-premises
- Acts as the user interaction layer for access requests

⚙️ Red Hat Ansible Integration
- Automates provisioning and de-provisioning tasks
- Ensures idempotent and repeatable operations

🧾 ServiceNow Integration
- Creates and updates incidents / service requests
- Maintains audit trails and approval workflows

🏢 Microsoft AD DS Integration
- User creation, group assignment, and access control
- Supports enterprise directory structures

🔒 Security-First Design
- No external AI or third-party chatbot dependencies
- Works entirely within controlled infrastructure

🏗️ Architecture Overview
<img width="499" height="347" alt="Final Authica Architecture" src="https://github.com/user-attachments/assets/4e3ee02e-2db8-4121-b4da-08d179fdf416" />


🧰 Tech Stack
Language: Python
Automation: Red Hat Ansible
ITSM: ServiceNow
Directory Services: Microsoft Windows Active Directory Domain Services (AD DS)
Platform: On-prem / Enterprise infrastructure

📂 Project Structure (Example)
Authica/
├── chatbot/
│   ├── main.py
│   └── intents/
├── ansible/
│   ├── playbooks/
│   └── roles/
├── servicenow/
│   └── api/
├── ad/
│   └── provisioning/
├── config/
│   └── settings.yaml
└── README.md

⚙️ Setup & Installation

⚠️ Prerequisites
- Python 3.9+
- Red Hat Ansible
- ServiceNow developer instance with API access
- Windows Server with AD DS

Appropriate credentials and permissions
1. Clone the Repository
git clone https://github.com/your-org/authica.git
cd authica
2. Configure Environment
Update configuration files in config/
Set ServiceNow API credentials
Configure AD DS connection details
Define Ansible inventory and roles

3. Run the Chatbot
python chatbot/main.py


🔄 Workflow Example
1) User requests access via the chatbot
2) Chatbot validates request and creates a ServiceNow request
3) Request is sent for approval to the User's Manager
4) Notifications enabled via Gmail, Outlook
5) Approval processed in ServiceNow
6) **Approval**
   - Notifications to the user and manager
   - Ansible Playbooks triggered for creation of user in AD DS and added to the required Assignment Group
   - Upon assignment closes ServiceNow request
          
   **Rejection**
   - Notifications to the user and manager
   - Request closed in ServiceNow
     
📊 Use Cases
- Automated employee onboarding
- Role-based access provisioning
- Temporary access requests
- De-provisioning during offboarding
- Compliance-driven access management

🛡️ Security & Compliance
- Designed for air-gapped or restricted networks
- Full auditability via ServiceNow
- Least-privilege automation using Ansible
- No data leaves the local environment
