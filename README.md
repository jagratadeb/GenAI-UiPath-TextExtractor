# 🧾 GenAI UiPath TextExtractor (GPT-4o)

This UiPath project demonstrates how to extract and process data from scanned PDFs using OCR (Tesseract) and UiPath GenAI Activities powered by OpenAI's GPT-4o.

## 📁 Packages Required
* UiPath.PDF.Activities
* UiPath.System.Activities
* UiPath.IntegrationService.Activities
* UiPath.Testing.Activities
* UiPath.UIAutomation.Activities



## ⚙️ Workflow Overview

### 1. Read PDF With OCR
- **Activity:** `Read PDF With OCR`
- **Input:** File path to a scanned PDF.
- **OCR Engine:** Tesseract OCR is used to extract raw text content from the scanned document.

### 2. Connector Activity (GenAI)
- **Activity:** `Connector activity`
- **Service:** UiPath GenAI Activities (OpenAI GPT-4o)
- **Model Name:** `gpt-4o-2024-11-20`
- **Prompt:**
```text
  "From the input" + pdf + "extract the Consumer Number, Units Used, Total Amount, and Due Date and then show them in this example format 

Details From The Bill
Consumer Number : <the consumer number will go here>
Units Used: <units used will go here>
Total Amout: <total amount will go here>
Due Date: <due date will go here>
"
```
- **PII Detection:** Disabled (`False`)
- **System Prompt:** `"You are a helpful assistant"`

### 3. Display Result
- **Activity:** `Message Box`
- **Content:** The extracted and processed information from the GPT response is displayed using a simple message box.

## 🛠 Prerequisites

- UiPath Studio installed
- UiPath GenAI Activities package installed
- OpenAI (or Azure OpenAI) key connected via UiPath account
- PDF file with scanned text content

## 🚀 How to Run

1. Open `Main.xaml` in UiPath Studio.
2. Modify the file path in the `Read PDF With OCR` activity to point to your own scanned PDF.
3. Run the workflow.
4. The extracted content will be displayed in a message box.

## 📌 Notes

- Ensure OCR is accurate enough; low-quality scans may affect extraction.
- You can modify the prompt for different kinds of data extraction.
- Add error handling for production scenarios.

## 📄 License

This project is provided as-is for educational purposes.

---

Created with ❤️ using [UiPath](https://www.uipath.com) and [OpenAI GPT-4o](https://platform.openai.com/docs/models/gpt-4o) by [Jagrata Deb](https://github.com/jagratadeb)

