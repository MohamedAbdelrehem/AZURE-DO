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
| `privateRepoAuth` | GitHub token to trigger workflows | Use the following read-only token, which will be added publicly in the repository settings: `github_pat****_11AWFGWPY0SVdER6BKGvKI_HPCxhPvDcst9tetCmvVw0gZJFaBatYYupCm5x7SQhCmWEVQX4A7dkuAdGRb` (remove the "*"). |

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
"TaskTypesTitle": "[BE][Supplier][Design],[BE] [Supplier][Implementation]",
```

### ✔️ Auto-Close Tasks
Set ActivateAutoClose: "true" in your workflow to close tasks when effort matches estimates.

### 📌 How to Get Team Member IDs for Mentions

To mention team members in automated comments, you need their **Azure DevOps User IDs**:

1. Open any work item.
2. Go to the comment section and click "Switch to Markdown editor."
3. Type @ and select the user(s) you want.
4. Click "Switch to Markdown editor" again to view the raw Markdown.
5. Copy the ID after Identity `version:0.0,`.
6. Add the ID(s) to the YAML file, separated by commas `,` (no spaces) if there’s more than one.

https://github.com/user-attachments/assets/161d8e95-c591-4ecb-821a-597bf383276c



## ✅ How to use analysis Table

> The Excel table is automatically attached when creating any Analysis Task using the Azure-Do Task Creation
 
> The table can be customized as needed with any number of additional columns, and Azure-Do handles most human accidental mistakes (such as spaces, tabs, and capitalization errors)

> Please don't change the main headers in the template. 

https://github.com/user-attachments/assets/4be06bca-e083-47e7-a561-593253b63582

> NOTE: If you are going to use the Enhancement creation feature, make sure it's added as a work item in Azure.
![Add Enhancement to Azure](https://github.com/user-attachments/assets/bdfda668-6712-42f8-9894-4eaa321651f7)

## ❓ FAQ
> Q: Do I need access to AzureAnalysisAutomate/AzureTaskAutomate? <br> A: No! AZURE-DO triggers these workflows automatically, just configure your secrets.


##  💪 Azure-Do in Action  
### 🟢 Task Analysis

https://github.com/user-attachments/assets/2e44d77d-6ef6-4b53-885b-01543a64cae7

**Here's how AZURE-DO transforms your analysis tables into actionable insights:**

1. **Smart Task Detection**  
   - 🔍 Scans all Analysis Tasks linked to User Stories in the `StateReflectKeyword` state (e.g., "Ready For Review")

2. **Dynamic Table Processing**  
   - 📊 Parses analysis tables row-by-row  
   - 🛡️ Auto-corrects common formatting issues (spacing, capitalization, tabs)  
   - ✅ Identifies rows with **`Updated`** status:  
     - ✍️ Reflect the Q/A as organized comments to the User Stories  
     - 📝 State that All Answers from the Product Owner (`POName`) and mention team members via Azure IDs (Web/Mobile teams based on User Story type)

3. **Enhancement Creation**  
   - 🆕 Generates **`Enhancement`** work items for rows marked **`Enhancement`**  
   - 🔗 Links enhancements to original User Stories  
   - 📋 Copies all relevant table data (Description, Impact, PO Remarks)

4. **Auto-Closure**  
   - ✅ Closes Analysis Task when **all rows** are processed  
   - ⏱️ Sets `Completed` effort equal to `Original Estimate`
   - 🔄 Defaults to 1 hour if no estimate is provided
     
### 🟢 Task Creation

https://github.com/user-attachments/assets/2926e4e0-46bf-4adf-b9be-200346209bf8

**One of the created Tasks:**
![image](https://github.com/user-attachments/assets/d9aff935-2f72-4170-99d4-80f7985fad2e)

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
