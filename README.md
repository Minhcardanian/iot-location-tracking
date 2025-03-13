# IoT Location Tracking Project

## Project Overview
The project involves developing a web-based application to track simulated device positions within a defined area. The main goal is to demonstrate location tracking capabilities using simulated IoT data without any physical hardware.

---

## Specific Problem Addressed

### Problem Statement
Organizations often face challenges in managing and monitoring asset locations within large campuses, warehouses, or industrial facilities. Traditional GPS tracking solutions require costly hardware, making initial deployments expensive and time-consuming.

### How the Project Solves the Problem
This project addresses these challenges by:
- Offering a cost-effective alternative to hardware-based location tracking.
- Allowing organizations to simulate and test location-tracking strategies virtually before actual deployment.
- Reducing deployment time by validating systems in a virtual environment first.
- Facilitating training for personnel in managing asset tracking systems without needing physical devices.

---

## Technology Stack

### Backend
- **Python (3.9.1)**: Main programming language.
- **Flask (2.1.2)**: Web framework for RESTful API creation.
- **CounterFit**: Virtual IoT device simulator generating GPS-like data.
- **SQLite**: Lightweight database for storing location data.

### Frontend
- **React.js**: User interface development.
- **Leaflet.js**: Interactive map visualization for location data.
- **Axios**: API communication between frontend and backend.

### Hosting & Deployment
- **Netlify**: Hosting for frontend.
- **Heroku or similar service**: Hosting backend Flask application.

---

## System Architecture

### 1. Simulation Layer
- **CounterFit** generates virtual GPS data.
- Simulated data represents device movements within a specified area.

### 2. Backend Layer (Flask API)
- Receives simulated data from CounterFit.
- Manages data storage, retrieval, and processing.
- Exposes API endpoints to deliver data to frontend.

### 3. Database Layer
- SQLite used to store simulated positional data.
- Tracks historical location data for each simulated device.

### 4. Frontend Layer
- React.js app fetches data from Flask API via Axios.
- Interactive maps provided by Leaflet.js for real-time visualization.
- Allows tracking and visualization of simulated devices' movements.

### 5. Hosting & Deployment
- Frontend application deployed via Netlify.
- Flask API deployed on cloud-based hosting such as Heroku.

---

## Key Features
- Real-time simulated location tracking.
- Historical data visualization and analysis.
- Interactive and responsive map-based UI.
- Scalable backend infrastructure for multiple simulated devices.

---

## Virtual Environment (`venv`) Setup
To ensure a consistent development environment, use a Python virtual environment (`venv`).

### **1. Create and Activate Virtual Environment**
```bash
python3.9 -m venv venv
source venv/bin/activate
```

### **2. Install Required Packages**
Run the following command to install project dependencies:
```bash
pip install -r requirements.txt
```
If `requirements.txt` does not exist, install manually:
```bash
pip install counterfit==0.1.4.dev9 Flask==2.1.2 Werkzeug==2.0.3 requests==2.32.3
```

### **3. Save Dependencies for Future Installations**
After installing dependencies, run:
```bash
pip freeze > requirements.txt
```
This allows others to install dependencies easily with:
```bash
pip install -r requirements.txt
```

### **4. Start Counterfit and Run Application**
Start the Counterfit server:
```bash
counterfit
```
Then, in another terminal:
```bash
python app.py
```

---

## SSH Configuration for GitHub Repository
To securely connect to GitHub via SSH, follow these steps:

### **1. Check for an Existing SSH Key**
```bash
ls ~/.ssh/id_rsa.pub
```
If the file does not exist, generate a new SSH key.

### **2. Generate a New SSH Key (If Needed)**
```bash
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```
- Press `Enter` to save it in `~/.ssh/id_rsa`.
- **DO NOT** enter a passphrase (just press `Enter`).

### **3. Add SSH Key to GitHub**
1. Copy your SSH key:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
2. Go to **[GitHub SSH Settings](https://github.com/settings/keys)**.
3. Click **"New SSH Key"**.
4. **Title:** `iot-location-tracking`
5. **Key Type:** `Authentication Key`
6. Paste the copied SSH key and click **"Add SSH Key"**.

### **4. Test SSH Connection**
```bash
ssh -T git@github.com
```
Expected output:
```
Hi Minhcardanian! You've successfully authenticated, but GitHub does not provide shell access.
```

### **5. Set SSH Remote for Git Repository**
Navigate to your project directory:
```bash
cd ~/iot-location-tracking
```
Set the SSH remote URL:
```bash
git remote set-url origin git@github.com:Minhcardanian/iot-location-tracking.git
```
Verify the change:
```bash
git remote -v
```
Expected output:
```
origin  git@github.com:Minhcardanian/iot-location-tracking.git (fetch)
origin  git@github.com:Minhcardanian/iot-location-tracking.git (push)
```

### **6. Push Code Using SSH**
If you have uncommitted changes:
```bash
git add .
git commit -m "Configured SSH for GitHub repo"
git push origin main
```

---

## Future Enhancements
- Integration with advanced analytics for predictive tracking.
- Expansion to cloud-based databases (e.g., PostgreSQL, MongoDB).
- Enhanced security and authentication mechanisms.

---


