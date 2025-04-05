<br>
<p align="center">
 <img  src="AZURE-DO.png" align="center" alt="AZUREDOLogo" />
</p>
<!-- <h1 align="center"> From To-Do to Done </h1> -->
<!-- Badges -->

<p align="center">
   <a href="https://github.com/your-repo/AZURE-DO/stargazers">
      <img src="https://img.shields.io/github/stars/MohamedAbdelrehem/AZURE-DO?logo=github&color=yellow&logoColor=black" alt="Stars">
    </a>
    <a href="https://github.com/your-repo/AZURE-DO/issues">
      <img src="https://img.shields.io/github/issues/MohamedAbdelrehem/AZURE-DO?color=green&logo=git&logoColor=white" alt="Issues">
    </a>
 <br><br>
    <img src="https://img.shields.io/badge/Azure-DevOps-0078D7?logo=azure-devops&logoColor=white" alt="Azure DevOps">
<img src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" >
<img src="https://img.shields.io/badge/REST_Assured-009688?logo=rest&logoColor=white" >
    <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white" alt="GitHub Actions">
<img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" >
    <img src="https://img.shields.io/badge/YAML-000000?logo=yaml&logoColor=white" alt="YAML">
    <img src="https://img.shields.io/badge/Excel-217346?logo=microsoft-excel&logoColor=white" alt="Excel">
<img src="https://img.shields.io/badge/Postman-FF6C37?logo=postman&logoColor=white" >
</p>

<!-- Index -->
<p align="center">
<a href="#-what-is-azure-do">📖 What is AZURE-DO?</a> &nbsp;&bull;&nbsp;
<a href="#-key-features">🚀 Key Features</a> &nbsp;&bull;&nbsp;
<a href="#-quick-start">⚡ Quick Start </a> &nbsp;&bull;&nbsp;
<a href="#️-advanced-configuration">🛠️ Advanced Configuration</a>
<br>
<a href="#-azure-do-in-action">💪 Azure-Do in Action (Demo)</a> &nbsp;&bull;&nbsp;
<a href="#-to-do">🔜 To Do</a> &nbsp;&bull;&nbsp;
<a href="#-faq">❓ FAQ</a> &nbsp;&bull;&nbsp;
<a href="#-spread-the-word">🌟 Spread the Word!</a>
</p>

---

## 📖 What is AZURE-DO?

**AZURE-DO** is your Azure DevOps automation assistant. It triggers workflows in **AzureAnalysisAutomate** and **AzureTaskAutomate** to automate work item management, task creation, and sprint analysis **no coding required**.

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
Click **Fork** to create your copy of AZURE-DO.  

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

![Organization and ProjectName](https://github.com/user-attachments/assets/fb7971e1-1828-4678-8809-0afd07c8c62d)

---

### **Task Automate**

| Variable Name        | Scope         | Description                                                                 | Example                           |
|----------------------|---------------|-----------------------------------------------------------------------------|-----------------------------------|
| `ActivateAutoClose`  | Task Automate | Automatically closes tasks when effort matches estimates (`true`/`false`). | `true`                            |
| `TaskTypesTitle`     | Task Automate | Comma-separated task titles to create (e.g., team-specific templates).      | `"Test Analysis,Test Execution"`  |
| `TaskScope`          | Task Automate | Sprint scope: `Current Sprint` or `All Sprints`.                            | `"Current Sprint"`                |
| `TaskUSScope`        | Task Automate | Filters user stories by platform based on the title: `Web`, `Mobile`, or `All`.                | `"Web"`                           |
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


### 4️⃣ **Trigger the Workflow**  
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


##  💪 Azure-Do in Action  
### Task Creation

https://github.com/user-attachments/assets/2926e4e0-46bf-4adf-b9be-200346209bf8

**One of the created Tasks:**
![image](https://github.com/user-attachments/assets/d9aff935-2f72-4170-99d4-80f7985fad2e)

### Task Analysis


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
