<br>
<p align="center">
 <img  src="AZURE-DO.png" align="center" alt="AZUREDOLogo" />
</p>
<!-- <h1 align="center"> From To-Do to Done </h1> -->
<p align="center">
<img alt="GitHub contributors" src="https://img.shields.io/github/contributors/MohamedAbdelrehem/AZURE-DO">
<img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/y/MohamedAbdelrehem/AZURE-DO">
<img alt="GitHub closed pull requests" src="https://img.shields.io/github/issues-pr-closed/MohamedAbdelrehem/AZURE-DO">
<img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/MohamedAbdelrehem/AZURE-DO">
<img alt="GitHub" src="https://img.shields.io/github/license/MohamedAbdelrehem/AZURE-DO?color=brightgreen">
<br>
<img src="https://img.shields.io/badge/--F05032?logo=git&logoColor=ffffff" />
<img src="https://img.shields.io/badge/--6C33AF?logo=visual%20studio" />
<img  src="https://img.shields.io/badge/--512BD4?logo=.net&logoColor=ffffff" />
<img alt="GitHub top language" src="https://img.shields.io/github/languages/top/MohamedAbdelrehem/AZURE-DO">
<img src="https://badgen.net/badge/icon/windows?icon=windows&label" />
<img alt="GitHub release (latest by date including pre-releases)" src="https://img.shields.io/github/v/release/MohamedAbdelrehem/AZURE-DO?include_prereleases">
 
</p>

<p align="center">
<a href="#-about-clinicxpromax">📖 About ClinicXProMax</a> &nbsp;&bull;&nbsp;
<a href="#-features">🚀 Features</a> &nbsp;&bull;&nbsp;
<a href="#-tech-stack">💻 Tech stack</a> &nbsp;&bull;&nbsp;
<a href="#%EF%B8%8F-installation">🛠️ Installation</a>
<br>
<a href="#-to-do">🔜 To Do</a> &nbsp;&bull;&nbsp;
<a href="#-how-to-contribute">🤝 How to contribute</a> &nbsp;&bull;&nbsp;
<a href="#%EF%B8%8F-license">⚠️ License</a> &nbsp;&bull;&nbsp;
<a href="#-spread-the-word">🌟 Spread the word!</a> &nbsp;&bull;&nbsp;
<a href="#special-thanks-for-minia-university-especially-drabdullah-hassan-and-engal-shaimaa-a-younis-for-there-support-for-this-project">💛Special thanks</a>
</p>




---

## 📖 What is AZURE-DO?

**AZURE-DO** is your Azure DevOps automation assistant. It triggers workflows in **AzureAnalysisAutomate** and **AzureTaskAutomate** to automate work item management, task creation, and sprint analysis — **no coding required**.

---

## 🚀 Key Features

### **Automated Task Creation**  
- **📅 Sprint Scope**: Create tasks for `Current Sprint` or `All Sprints`, filtered by `Web`, `Mobile`, or `All` User Stories.  
- **👥 Team Templates**: Predefined workflows for Testing, Frontend, and Backend teams.  
  - **Testing**: `Test Analysis`, `Test Execution`, etc.  
  - **Frontend**: `[FE][Design]`, `[FE][Review]`, etc.  
  - **Backend**: `[BE][Implementation]`, `[BE][UnitTest]`, etc.  
- **📎 Attachments**: Auto-attach templates (e.g., Excel files) to tasks.  

### **Test Analysis Automation**  
- **💬 User-Friendly Comments**: Convert analysis tables into formatted comments on User Stories.  
- **🆕 Auto-Create Enhancements**: Generate `Enhancement` work items for unresolved issues.  
- **✅ One Click Auto-Close Tasks**: Close tasks when effort matches estimates.  

### **Customization**  
- **⚙️ Dynamic Configurations**: Adjust sprints, tags, and logic via environment variables.  
- **🔗 Team Mentions**: Tag team members using their Azure DevOps IDs.  

---

## ⚡ Quick Start

### 1️⃣ **Fork the Repository**  
Click [**Fork**](https://github.com/your-repo/fork) to create your copy of AZURE-DO.  

---

### 2️⃣ **Configure Secrets & Variables**  
Go to your **forked repository** ➝ **Settings ➝ Secrets and Variables ➝ Actions**.

and add the following secrets:

#### **🔒 Required Secrets**  

| Secret Name       | Description                                               | Where to Get It                                                                                          |
| ----------------- | --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `AZURE_PAT`       | Personal Access Token for Azure DevOps                    | 1. Go to your Azure DevOps Project. <br> 2. Click on your profile ➝ **Personal Access Tokens**. <br> 3. Generate a token with Work Item Read & Write permissions. |
| `privateRepoAuth` | GitHub token to trigger workflows | Use the following read-only token, which will be added publicly in the repository settings: `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`. |

https://github.com/user-attachments/assets/3e8c74a2-88ce-41ab-ae3a-9799b9a863b1


### 3️⃣ Set Up Repository Variables
Navigate to **.github/workflows** ➝ **Azure-Do_Trigger.yml** <br>
*OR* go to **Actions ➝ Trigger Workflow Dispatch ➝ Azure-Do_Trigger.yml (displayed as a blue hyperlink under the workflow)** <br>
, then Edit the following variables in the Json that in the YAML file to align with your project:

### **Shared Variables**

| Variable Name  | Scope | Description                                                  | Example             |
|----------------|-------|--------------------------------------------------------------|---------------------|
| `Organization` | Both  | Name of your Azure DevOps organization.                      | `"OrgnizationName"` |
| `ProjectName`  | Both  | Name of your Azure DevOps project (use `%20` for spaces).    | `"Project%20Name"`  |


---

### **Task Automate**

| Variable Name        | Scope         | Description                                                                 | Example                           |
|----------------------|---------------|-----------------------------------------------------------------------------|-----------------------------------|
| `ActivateAutoClose`  | Task Automate | Automatically closes tasks when effort matches estimates (`true`/`false`). | `true`                            |
| `TaskTypesTitle`     | Task Automate | Comma-separated task titles to create (e.g., team-specific templates).      | `"Test Analysis,Test Execution"`  |
| `TaskScope`          | Task Automate | Sprint scope: `Current Sprint` or `All Sprints`.                            | `"Current Sprint"`                |
| `TaskUSScope`        | Task Automate | Filters User Stories by platform: `Web`, `Mobile`, or `All`.                | `"Web"`                           |
| `TaskTags`           | Task Automate | Tags to add to created tasks (comma-separated). Use `""` to skip.           | `"tag1,tag2"`                     |

---

### **Analysis Automate**

| Variable Name         | Scope             | Description                                                         | Example                     |
|-----------------------|-------------------|---------------------------------------------------------------------|-----------------------------|
| `POName`              | Analysis Automate | Product Owner’s name for mentions in comments.                      | `"Mohamed Abdelrehem"`      |
| `FrontEndIDs`         | Analysis Automate | Azure DevOps user IDs for Frontend team mentions (comma-separated).| `"id1,id2,id3"`             |
| `BackEndIDs`          | Analysis Automate | Azure DevOps user IDs for Backend team mentions (comma-separated). | `"id1,id2,id3"`             |
| `MobileIDs`           | Analysis Automate | Azure DevOps user IDs for Mobile team mentions (comma-separated).  | `"id1,id2,id3"`             |
| `StateReflectKeyword` | Analysis Automate | Work item state to trigger analysis (e.g., `Ready For Review`).     | `"Ready For Review"`        |


### 3️⃣ **Trigger the Workflow**  
1. Make sure the `Azure-Do_Trigger.yml` file has no empty variables and that commas are placed correctly between the variables.
> It's recommended to comment out one of the two flows when running the other to avoid conflicts.
2. Go to **Actions ➝ Trigger Workflow Dispatch**.  
3. Click **Run workflow**.  
4. **Done!** AZURE-DO will:  
   - ✅ Create tasks based on your `TASK_TITLES`.  
   - 📊 Process Test Analysis and post comments.  
   - 🔄 Sync sprint data automatically. 

## 🛠️ Advanced Configuration

### **Customize Task Templates**  
Edit the Task Titles using `TaskTypesTitle` variable to match your team’s workflow.
You can dynamically add any custom task titles. 
```yml
# Testing Team Example
"TaskTypesTitle": "Test Analysis,Test Case Preparation,Test Execution",

# Frontend Team Example
"TaskTypesTitle": "FE-CreatUI,FE-Review,FE-APIIntegration",

# Backend Team
"TaskTypesTitle":"[BE][Supplier][Design],[BE] [Supplier][Implementation]",
```

### 📌 How to Get Team Member IDs for Mentions

To mention team members in automated comments, you need their **Azure DevOps User IDs**:

1. **Go to Azure DevOps** ➝ **Organization Settings**.
2. **Select Users** and find the team member.
3. Click on the user profile and copy their **ID from the URL**.
4. Add multiple IDs separated by a comma `,`.

### How to use analysis Table

> still not documented now

### Auto-Close Tasks
Set ActivateAutoClose: "true" in your workflow to close tasks when effort matches estimates.

## ❓ FAQ
> Q: Do I need access to AzureAnalysisAutomate/AzureTaskAutomate? <br> A: No! AZURE-DO triggers these workflows automatically, just configure your secrets.




## 🔜 To Do

- [x] Trigger Analysis Automation
- [x] Automate Task Creation
- [x] Implement Work Item State Updates
- [x] Handle Missing Tasks Automatically
- [x] Extract and Update Effort Estimations
- [ ] Enhance Debug Logging
- [ ] Send report to a specific mail or drive
- [ ] Integrate with Jira (including Zephyr or Xray for test management)
- [ ] Create UI to make process more user friendly

---

## Let’s build something amazing together! 🚀
**have feedback or Need help?** <br>
Feel free to reach out on **[LinkedIn](https://www.linkedin.com/in/mohamed-abdelrehem)** or open an issue on GitHub.
Stay connected for updates!



## 🌟 Spread the Word!

If you find AZURE-DO helpful, **give it a ⭐ on GitHub!** Your support means a lot. 💙
