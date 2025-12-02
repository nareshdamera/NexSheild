# 🛡️ NEXSHEILD  
### **Personalized Security Alerting Platform**

NEXSHEILD is a proactive, full-stack security alerting platform designed to solve the problem of **alert fatigue**.  
Instead of overwhelming users with every new vulnerability, NEXSHEILD intelligently scans, enriches, filters, and notifies users **only when a cybersecurity threat is relevant** to their tracked technologies or organizations.

Built using a modern **MERN-like tech stack**, the platform features automated vulnerability monitoring, LLM-powered data enrichment, personalized alerts, and a smooth, responsive frontend experience.

---

## ✨ **Core Functionality: The Automated Data Pipeline**

At the heart of NEXSHEILD lies an automated backend pipeline that runs daily using a Cron Job.

### **1️⃣ Data Harvesting & Enrichment**
#### **Web Scraping (scraper.cjs)**
- Scrapes the latest CVEs from the **National Vulnerability Database (NVD)** using **Cheerio**.
- Extracts raw vulnerability content for processing.

#### **LLM-Powered Data Enrichment**
- Sends raw vulnerability text to a **HuggingFace LLM**.
- The model extracts:
  - Company / Vendor name  
  - Short, clear vulnerability summary  
- Converts unstructured CVE descriptions into **clean, structured, actionable data**.

---

### **2️⃣ Personalized Alerting**
#### **Targeted Matching (mail.cjs)**
- Retrieves all users who opted in for notifications.
- Compares the LLM-extracted **Company Name** with the **user’s tracking keywords**.

#### **Smart Email Notifications**
Users receive alerts *only* when:
- A vulnerability matches their tracked vendors/technology.
- They have enabled email notifications.

This dramatically reduces **alert noise** and increases the **signal-to-alert ratio**.

---

## 🖥️ **Frontend: Clean, Smooth, User-Centric Experience**

The frontend is a **dark-themed React SPA**, optimized for clarity and speed.

### **Key Routes & Features**

| Route | Purpose | Features |
|-------|---------|----------|
| `/` | Landing Page | About section, testimonials, project overview |
| `/login` / `/register` | Authentication | JWT login, bcrypt password hashing, persistent session storage |
| `/dashboard` | Vulnerability Feed | Search, pagination, protected route |
| `/profile` | User Settings | Keyword updates, password change, account management |

### **Tech Enhancements**
- **Tailwind CSS** for modern styling  
- **Framer Motion** for smooth animations  
- **React Router** for seamless navigation  

---

## ⚙️ **Technology Stack**

### **Frontend**
- React  
- Tailwind CSS  
- Framer Motion  
- React Router  

### **Backend**
- Node.js  
- Express.js  
- node-cron  

### **Database**
- MongoDB (Mongoose)  
- Stores Users, Vulnerabilities, Enriched Metadata  

### **Intelligence Layer**
- HuggingFace Large Language Model  
- Extracts company names & summaries from CVEs  

### **Email Service**
- Nodemailer  
- Sends targeted vulnerability alerts  

---

## 📁 **Project Structure**

├── config/ # JWT token generation
├── controllers/ # Authentication & data processing logic
├── middleware/ # JWT verification (authMiddleware)
├── models/ # Mongoose schemas (User & Vulnerability)
├── routes/ # Express API endpoint definitions
├── services/ # External service handlers (Nodemailer)
├── src/ # React Frontend source code
└── index.js # Server entry point, DB connection, Cron job setup
---

## 🚀 **Key Features Overview**
- 🔍 Automated CVE scraping  
- 🤖 LLM-powered vulnerability enrichment  
- ✉️ Personalized email alerts  
- 🔐 Secure JWT-based authentication  
- ⚡ Real-time dashboard for browsing vulnerabilities  
- 🎛️ Editable keyword tracking system  

---

## 📌 **Future Enhancements**
- AI-based severity scoring  
- Real-time CVE streaming using WebSockets  
- Organization dashboards & team-level alerts  
- Historical analytics & reporting  

---

## 🤝 **Contributions**
Feel free to open issues or submit pull requests — contributions are welcome!

---

## 📝 License
This project is licensed under the **MIT License**.

---

## 💡 **Author**
**Naresh Damera**  
Chief AI Engineer  
GitHub: *github.com/nareshdamera*
