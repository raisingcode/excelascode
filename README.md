v# excelascode v1.3

<img src="assets/banner.png" alt="excel-as-code-banner" width="100%">

[![Version](https://img.shields.io/badge/version-1.3-blue.svg)](https://github.com/raisingcode/excelascode)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Excel_Windows-success.svg)]()

**The bridge between "Right Click -> Deploy" and "Infrastructure as Code."**

**ExcelAsCode** is a zero-dependency macro toolkit that turns standard Excel spreadsheets into a powerful cloud orchestrator. Scaffold virtual machines in rows and columns, check your quota limits instantly, and then choose your path: **Deploy directly to Azure** via REST API, or **Export to Terraform/Bicep** for your DevOps pipeline.

---

## 📖 The Backstory

ExcelAsCode wasn't born in an ivory tower. It was born in the trenches of enterprise migration.

While helping on-prem sysadmins move legacy workloads to the cloud, we kept hitting a wall: The "Cloud First" mandate required complex DevOps tooling (Terraform, CLI, Git), but the Ops teams lived and breathed in **Excel**. They didn't hate the cloud; they hated the friction of learning a new language just to spin up a server.

We built ExcelAsCode to meet them where they were.

It started as a hack to let admins define VMs in a spreadsheet and click "Go." It evolved into a strategic bridge—allowing teams to move at the speed of Excel while automatically generating the IaC artifacts needed for compliance and governance.

---

## 🚀 Why ExcelAsCode?

Most "low-code" tools require heavy installation or complex prerequisites. ExcelAsCode is different.

* **Zero Dependencies:** No Azure CLI. No PowerShell modules. No Python venv. The macro speaks directly to the **Azure REST API**. If you have Excel and an internet connection, you are ready to deploy.
* **The "Bridge" Workflow:** Use Excel for rapid prototyping and scaffolding. Once the architecture is agreed upon, hit "Export" to generate clean Terraform or Bicep code to hand off to your DevOps team.
* **Safety First:** Includes a built-in **Quota Checker**. The tool checks your subscription limits *before* trying to deploy, saving you from failed pipelines and half-baked resource groups.

---

## 📥 Installation & Security Setup

**Important:** Because this tool uses powerful VBA automation, Microsoft Excel's default security settings will likely block the macros if you simply download and double-click the file (due to the "Mark of the Web").

**Follow these steps to run the tool successfully:**

1.  **Download** the latest `excelascode-v1.3.xlsm` from the [Releases](https://github.com/raisingcode/excelascode/releases) page.
2.  **Unblock the File (Critical Step):**
    * Navigate to your download folder.
    * **Right-click** the `excelascode-v1.3.xlsm` file and select **Properties**.
    * At the bottom of the *General* tab, check the box labeled **Unblock**.
    * Click **Apply** and **OK**.
    * *(Note: If you do not see this checkbox, the file is already safe to open.)*
3.  **Open in Excel:**
    * Open the file.
    * Click **"Enable Content"** in the yellow bar at the top to allow the macros to initialize.

---

## ✨ Features (v1.3)

| Feature | Description |
| :--- | :--- |
| **Direct API Deployment** | Deploys resources directly to Azure using native REST API calls. No CLI installation required. |
| **Quota Pre-Flight** | Checks available vCPU capacity in your target region before deployment attempts. |
| **IaC Export** | Generates valid `main.tf` (Terraform), `.bicep`, or ARM templates based on your spreadsheet rows. |
| **Region-Aware** | Validates SKU availability against Azure regions to prevent "SKU not found" errors. |
| **Traceability** | Generates a metadata map linking spreadsheet rows to deployed Resource IDs. |

---

## 🛠️ Prerequisites

* **OS:** Windows 10/11 (Required for ActiveX/VBA support).
* **Software:** Microsoft Excel 2016, 2019, or O365 Desktop.
* **Network:** Outbound HTTPS (Port 443) access to `management.azure.com`.
* **Identity:** A Microsoft Entra ID (Azure AD) account with `Contributor` (or equivalent) rights on the target Subscription.

> **Note:** **You do not need the Azure CLI installed.** The tool handles authentication via standard OAuth interactive prompts.

---

## ⚡ Quick Start

1.  **Open** the unblocked `excelascode-v1.3.xlsm` file.
2.  **Authenticate:**
    * When you run your first action, the tool will prompt for an interactive login via Microsoft Entra ID (standard OAuth flow).
3.  **Fill out the Grid:**
    * Define your Resource Group, VM Name, Image (Ubuntu/Windows), Size (SKU), and Region.
4.  **Execute:**
    * Click **[Validate Quota]** to ensure you have space in the region.
    * Click **[Deploy to Azure]** to build immediately via API.
    * Click **[Export Terraform]** to generate `.tf` files in your working directory.

---

## 🔒 Security & Governance

We take security seriously. Because this tool runs in a corporate environment, we adhere to the following principles:

1.  **Local Execution:** Logic runs locally on your machine. No data is sent to any third-party SaaS.
2.  **No Embedded Secrets:** The workbook **does not** store client secrets or passwords in cells. Authentication is handled via session tokens or secure prompts at runtime.
3.  **Least Privilege:** The tool can only do what *you* can do. It inherits your user permissions via the API token.

---

## 🗺️ Roadmap

* **v1.4 (Planned):**
    * Service Principal (Headless) Authentication for automated pipelines.
    * Integration with Azure Key Vault for admin password handling.
* **Future:**
    * Multi-Cloud Support (AWS EC2 / GCP Compute exports).
    * Reverse Engineering: Import existing Azure Resource Groups *into* Excel.

---

## 🤝 Contributing

We welcome contributions! Whether you're fixing a VBA bug, adding a new Bicep template export, or improving the documentation.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

*Built with ❤️ (and VBA) by [RaisingCode](https://github.com/raisingcode)*
