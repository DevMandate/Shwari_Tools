# 🧰 Shwari Movers - Tools Log System

This is a lightweight, web-based reporting system designed for **Shwari Movers**. It enables Shwari Team Leaders to easily log tool usage via a mobile-friendly form. Submissions are instantly recorded in a **Google Sheet**, and users are redirected to a stylish summary page where they can review and **download their report as a PDF**.

---

## 📉 Project Overview

| Feature               | Description                                                        |
| --------------------- | ------------------------------------------------------------------ |
| Tool Tracking Form    | Responsive HTML form for agents to submit tool reports             |
| Google Sheets Backend | Submissions are logged in real-time using Google Apps Script       |
| Confirmation Page     | Includes summary table and dynamic PDF download button             |

---

## 🌐 Live Demo

This project is not deployed online yet, but you can run it locally by opening the HTML files in your browser.

---

## 🎓 How It Works

1. **Form Submission**

   * A mover team leader fills out the form on `index.html` (Tool counts, location, drill selection, etc).
   * Upon clicking submit, the form data is POSTed to a **Google Apps Script Web App**.

2. **Apps Script Handling**

   * The script stores the data into a Google Sheet called `Sheet1`.
   * The Apps Script uses a `lock` to ensure safe concurrent submissions.

3. **Redirection & Summary**

   * After successful logging, the form redirects to `thankyou.html`.
   * JavaScript reads the submission from `localStorage`, displays a **styled summary table**, and allows the user to **download the report as a PDF**.


---

## 📊 Technologies Used

| Layer           | Technology                            |
| --------------- | ------------------------------------- |
| Frontend        | HTML5, CSS3 (with responsive design)  |
| Interactivity   | Vanilla JavaScript                    |
| Backend         | Google Apps Script                    |
| Database        | Google Sheets                         |
| PDF Generator   | jsPDF (client-side PDF generation)    |
| Optional Alerts | Gmail service from Google Apps Script |

---

## 📁 Project Structure

```
Shwari_Tools/
├── index.html              # Main form for tool submissions
├── thankyou.html           # Summary page with PDF download
├── script.gs               # Google Apps Script backend
├── img/
│   └── Shwari Movers Logo.png
├── .gitignore
└── README.md               # This documentation file
```

---

## ⚙️ Setup Instructions

### A. Set Up Google Sheet & Apps Script

1. Create a new Google Sheet
2. Name the sheet tab as `Sheet1`
3. Click on `Extensions > Apps Script` and paste `script.gs` content
4. Run the `initialSetup()` function once to set the Sheet ID in properties
5. Deploy as Web App:

   * `Deploy > Manage deployments > New deployment`
   * Select type: **Web App**
   * Set access to **Anyone**
   * Copy the deployment URL for the form action

### B. Update HTML

* Open `index.html`
* Replace the form `action` with your deployed Web App URL
* Make sure the image paths are correct if hosted

### C. Running Locally

Just open `index.html` in any browser.

---

## 📝 Sample Submission Flow

1. User visits `index.html` and submits:

   * Team Leader: John
   * Date: 2025-06-27
   * Location: Lavington
   * Tools used: 4 drills, 10 blankets, 5 clear boxes
2. Data sent to Apps Script → Google Sheet
3. Page redirects to `thankyou.html`
4. `thankyou.html` displays the summary as a **styled table**
5. User clicks **Download PDF** to save the submission

---

## 📊 Sample Output (PDF Summary)

* Title: "Shwari Tools Report - John"
* Includes all submitted data in a tabular format
* Auto-generated client-side, no server storage

---

## 📈 Future Improvements

* Admin dashboard to view/export all submissions
* Weekly report automation
* Google Drive storage integration
* Authentication via Google Sign-In
* WhatsApp or SMS alerts via Twilio

---

## 👤 Author

Made with ❤️ by [Caleb Wafula](https://www.linkedin.com/in/caleb-wafula-b25374290/)

---

