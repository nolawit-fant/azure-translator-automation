# azure-translator-automation

# Azure Translator Automation

## 📌 Project Objective

This project automates the process of translating text files using **Azure AI Translator**. It is built using **Terraform** for Infrastructure as Code (IaC), an **Azure Function App** to process translations, and **Azure Blob Storage** to manage input/output files. The solution ensures that users can upload a text file in one language and receive a translated version securely and efficiently in another.


---

## 🧩 Project Architecture

![Architecture Diagram](./assets/Architecture.jpg)

### 🔁 Workflow Explanation

1. **User Uploads File**:  
   A user uploads a `.txt` file to the **requests** container in Azure Blob Storage.

2. **Trigger Azure Function**:  
   The upload triggers the **Azure Function App** which is running Python and Azure SDK code.

3. **Translate Text**:  
   The Azure Function reads the file, sends the content to the **Azure AI Translator API**, and receives the translated result.

4. **Store Output**:  
   The translated content along with metadata (logs) is saved in the **responses** container in Blob Storage.

5. **IAM Security**:  
   IAM permissions are provisioned via Terraform to allow secure communication between the Function App and Blob Storage using Managed Identity.

---

## 🛠️ Technologies Used

- **Terraform** – Infrastructure as Code
- **Azure Blob Storage** – For storing input/output files
- **Azure Function App** – Serverless execution of translation logic
- **Azure AI Translator** – Cloud translation API
- **Python** – Translation script using Azure SDK
- **Azure CLI** – Resource deployment

---



