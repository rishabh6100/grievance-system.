# Intelligent Grievance Redressal & Auto-Categorization System
### Civic-Tech / GovTech B.Tech 3rd-Semester Project (Frontend Subsystem)

---

## 📌 Project Overview
**Title:** Intelligent Grievance Redressal and Auto-Categorization System using Feature Selection-Based Multi-Label Text Classification.  
**Lead & Frontend Developer:** 3rd-Semester B.Tech IT Team Lead.  
**Technology Stack:** HTML5, CSS3, JavaScript (ES6+), Bootstrap 5, Chart.js, Bootstrap Icons.

---

## 🚀 How to Run the Website on Windows 11

### Option 1: Double-Click (Zero Setup Required)
1. Open Windows File Explorer.
2. Navigate to:  
   `C:\Users\risha\project\grievance_system`
3. Double-click **`index.html`**. It will open instantly in Google Chrome, Microsoft Edge, or any modern web browser.

### Option 2: Using VS Code Live Server
1. In VS Code, open the folder: `C:\Users\risha\project\grievance_system`.
2. Right-click on `index.html` and click **"Open with Live Server"**.

### Option 3: Using Python Built-in Server
Open PowerShell in the project directory and run:
```powershell
python -m http.server 5500
```
Then visit `http://localhost:5500` in your browser.

---

## 🌟 Key Features Built into the Frontend

1. **Modern Civic-Tech UI & Responsive Layout:**
   - Designed using a modern government/civic design system with custom CSS variables, glassmorphism navbar, and crisp typography (`Plus Jakarta Sans`).
   - Fully responsive across desktop, tablet, and mobile screens.

2. **Smart Grievance Submission Portal:**
   - **Real-time AI Multi-Label Suggester:** As the citizen or student types their complaint in the description box, an NLP simulation engine actively scans text and suggests multi-label category pills in real-time.
   - **HTML5 Geolocation API:** "Use My Location" button detects device GPS coordinates with latitude and longitude.
   - **Evidence Photo Upload:** Drag-and-drop zone with instant thumbnail preview, file size check (< 5MB), and remove controls.
   - **Tracking ID Generator:** Automatically creates a unique token (e.g. `GRV-2026-1042`) and shows an official printable submission receipt.

3. **Live Status Tracking System:**
   - Instant search by Grievance Token ID.
   - Interactive 5-step visual stepper timeline (Submitted -> AI Categorized -> Department Assigned -> Field Redressal -> Resolved).
   - Sample 1-click test tokens for quick faculty demonstration without manual typing.

4. **Public Grievance Transparency Feed:**
   - Community board displaying grievances with status badges, multi-label pills, and geotags.
   - Filterable by Status (All, Pending, In Progress, Resolved) and Domain/Category.
   - Interactive community upvote counter with `localStorage` persistence.

5. **Interactive AI & Feature Selection Lab (Viva Defense Showcase):**
   - **NLP Preprocessing:** Displays raw text -> tokenization -> stopword removal.
   - **Chi-Square ($\chi^2$) Feature Selection:** Shows high-ranking discriminative terms vs discarded noise words.
   - **Multi-Label Binary Relevance Simulator:** Probability bars with a 50% threshold marker, demonstrating why a single grievance can activate multiple departmental workflows (e.g., Water Supply + Electrical Hazard).
   - **Faculty Viva Defense Cheat-Sheet Modal:** Explains Multi-Label vs Multi-Class, Chi-Square feature selection, Hamming Loss, and Micro/Macro F1.

6. **Interactive Analytics Dashboard:**
   - Real-time charts powered by Chart.js.
   - Category distribution bar chart (tracking multi-label frequencies).
   - Status breakdown donut chart.

---

## 📂 Project Directory Structure

```
grievance_system/
│
├── index.html           # Main single-page application & all portal views
├── README.md            # Project documentation & presentation guide
│
├── css/
│   └── style.css        # Custom Civic-Tech CSS styles, variables, animations
│
└── js/
    ├── data.js          # Default seed complaints & category taxonomy definitions
    ├── app.js           # Core application logic, form handling, tracking, feed, charts
    └── ai-demo.js       # Interactive AI feature selection & multi-label simulator
```

---

## 🤝 How Your Teammates Can Connect Their Backend Later

When your team members build the Flask backend and MySQL database:
1. **Flask API Endpoints:**
   - Change `form.addEventListener('submit')` in `app.js` to send a `fetch('/api/grievances', { method: 'POST', body: formData })`.
   - Change `performTracking(tokenId)` to call `fetch('/api/grievances/' + tokenId)`.
   - Change `renderGrievanceFeed()` to fetch complaints from `fetch('/api/grievances')`.
2. **ML Pipeline:**
   - The ML teammate's Python model endpoint `POST /api/predict` can replace `detectCategoriesFromText()` with actual model predictions.

Everything is decoupled, modular, and ready for seamless backend integration!
