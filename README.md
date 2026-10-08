# For-DASH
# 🚨 For-DASH — Disaster Assistance & Support Hub

**For-DASH** is a web-based disaster assistance and emergency response platform designed to connect **people in need, rescue teams, volunteers, hospitals, and administrators** through a centralized system.

The platform provides emergency SOS alerts, help requests, resource management, rescue coordination, hospital information, blood donation support, missing/found person reporting, disaster-risk information, real-time communication, and administrative monitoring.

---

## 🌟 Key Features

### 🆘 Emergency SOS

* One-click SOS emergency alert
* Automatically shares the user's location
* Rescue teams can monitor active SOS alerts
* Emergency status tracking
* Location-based emergency response

### 🙋 Help Request System

Users can request:

* 🍚 Food
* 🏠 Shelter
* 💧 Water
* 🏥 Medical assistance
* 🚑 Evacuation
* Other emergency support

Each request includes:

* Request type
* Description
* GPS location
* Urgency level
* Request status
* Assigned rescue team

---

### 🚑 Rescue Team Dashboard

Rescue teams can:

* View active SOS alerts
* See urgent help requests
* Accept and manage requests
* Create and manage rescue missions
* Track people helped
* View nearby hospitals
* Monitor missing/found people
* View disaster-risk information

---

### 👨‍💼 Admin Dashboard

Administrators can monitor the overall platform through an analytics dashboard.

Features include:

* Total users
* Active SOS alerts
* Pending help requests
* Available resources
* Hospital management
* User management
* Rescue mission monitoring
* Disaster-risk monitoring
* Community announcements
* Notifications

---

### 🩸 Blood Bank & Donation

The platform supports emergency blood assistance.

Users can:

* Create blood requests
* Specify blood group
* Specify required quantity
* Select urgency level
* Provide hospital information
* Register as blood donors
* Specify blood availability
* Share contact information

Supported blood groups include:

`A+`, `A-`, `B+`, `B-`, `AB+`, `AB-`, `O+`, `O-`

---

### 🏥 Hospital Management

The system maintains hospital information including:

* Hospital name
* Address
* Contact number
* Location
* Total capacity
* Available capacity
* Doctors
* Available services

Users and rescue teams can find nearby hospitals based on their location.

---

### 👥 Missing & Found People

Users can report missing or found people.

Information can include:

* Name
* Age
* Gender
* Description
* Photograph
* Last seen location
* Contact number
* GPS location
* Matching status

This helps communities coordinate during disasters and emergencies.

---

### 🌪️ Disaster Risk Assessment

For-DASH provides disaster-risk information including:

* Disaster type
* Location
* Severity level
* Predicted time
* Weather information
* Risk description
* Recommended actions

Risk levels include:

`Low` → `Moderate` → `High` → `Critical`

---

### 📦 Resource Management

The platform supports emergency resource management.

Resources can include:

* Food
* Water
* Medical supplies
* Blankets
* Other emergency supplies

Administrators/rescue teams can monitor:

* Total quantity
* Available quantity
* Location
* Supplier
* Expiry date
* Low-stock threshold
* Distribution history

---

### 💬 Real-Time Communication

For-DASH uses **Flask-SocketIO** to support real-time communication.

Users can communicate through:

* Direct messages
* Group/SOS rooms
* Location sharing
* Resource-related messages
* Emergency coordination

---

### 📢 Community Bulletin Board

Administrators can publish:

* Announcements
* Warnings
* Emergency instructions
* Updates

Posts can have different priority levels and can be pinned for visibility.

---

### 🔔 Notifications

Users can receive notifications related to:

* SOS alerts
* Weather
* Roadblocks
* Medical camps
* Emergency updates
* Other system events

---

### 🤖 AI-Powered Features

The system includes AI-supported functionality for emergency assistance and information processing.

The application is configured to use the **OpenAI API** for AI-related functionality.

> An API key must be configured locally before using AI-powered features.

---

## 👤 User Roles

For-DASH provides three main user roles:

| Role           | Main Responsibilities                                                                |
| -------------- | ------------------------------------------------------------------------------------ |
| 👤 User        | Request help, send SOS, offer resources, blood donation, report missing/found people |
| 🚑 Rescue Team | Respond to SOS alerts, manage help requests, conduct rescue missions                 |
| 👨‍💼 Admin    | Manage users, hospitals, resources, announcements, analytics and system data         |

---

## 🛠️ Technology Stack

### Backend

* **Python**
* **Flask**
* **Flask-SQLAlchemy**
* **Flask-Login**
* **Flask-SocketIO**
* **Werkzeug**

### Database

* **SQLite**
* SQLAlchemy ORM

### Frontend

* **HTML5**
* **CSS3**
* **JavaScript**

### Maps & Location

* **Folium**
* Geolocation
* GPS coordinates
* Geopy distance calculations

### AI

* **OpenAI API**

---

## 📁 Project Structure

```text
For-DASH/
│
├── app.py
├── setup_database.py
├── DASH_TESTING (1).py
│
├── README.md
│
├── style.css
│
├── index.html
├── login.html
├── register.html
├── base.html
│
├── user_dashboard.html
├── rescue_dashboard.html
├── admin_dashboard.html
│
├── all_requests.html
├── blood_bank.html
├── bulletin_board.html
├── disaster_risk.html
├── hospital_list.html
├── manage_hospitals.html
├── manage_users.html
├── missing_found.html
├── resource_inventory.html
└── rewards.html
```

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/abrargazi/For-DASH.git
```

### 2. Enter the project directory

```bash
cd For-DASH
```

### 3. Create a virtual environment

#### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

#### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

---

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

If a `requirements.txt` file is not available in your current version, install the main dependencies with:

```bash
pip install flask flask-sqlalchemy flask-login flask-socketio werkzeug python-dotenv requests geopy folium openai
```

---

### 5. Configure environment variables

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key
```

> Never commit your real API key to GitHub.

---

### 6. Set up the database

Run:

```bash
python setup_database.py
```

The application uses SQLite and stores the database locally.

---

### 7. Run the application

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000
```

in your browser.

---

## 🔐 Security

For-DASH includes several security mechanisms:

* Password hashing using Werkzeug
* Flask-Login authentication
* Login-required routes
* Role-based access control
* Session management
* Input validation
* Protected API endpoints
* Secure file upload handling

---

## 🔌 Important API Endpoints

Some of the application's API functionality includes:

```text
POST /api/update_location
POST /api/send_sos
POST /api/create_help_request
POST /api/offer_resource
```

These APIs support important functionality such as location updates, emergency alerts, help requests, and resource sharing.

---

## 🗄️ Main Data Models

The system uses database models for:

* Users
* Help Requests
* Resource Offers
* SOS Alerts
* Chat Messages
* Bulletin Posts
* Notifications
* Blood Requests
* Blood Donations
* Hospitals
* Rescue Missions
* Missing & Found People
* Disaster Risks
* Resource Inventory
* Resource Distribution
* Injury Reports
* News Posts
* User Rewards
* Reward Transactions
* Call Logs
* Rescue Ratings

---

## 🔄 System Workflow

```text
                    ┌──────────────────┐
                    │      User        │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
          Send SOS       Request Help    Offer Resource
              │              │              │
              └──────────────┼──────────────┘
                             ▼
                  ┌─────────────────────┐
                  │   For-DASH System   │
                  └──────────┬──────────┘
                             │
                 ┌───────────┴───────────┐
                 ▼                       ▼
        ┌─────────────────┐     ┌─────────────────┐
        │  Rescue Teams   │     │     Admin       │
        │                 │     │                 │
        │ Respond &       │     │ Monitor &       │
        │ Manage Missions │     │ Manage System   │
        └─────────────────┘     └─────────────────┘
```

---

## 🎯 Project Goals

The main goals of For-DASH are to:

1. Provide a centralized emergency assistance platform.
2. Reduce communication gaps during disasters.
3. Connect victims with rescue teams quickly.
4. Improve emergency resource coordination.
5. Help rescue teams prioritize critical requests.
6. Provide useful hospital and blood-donation information.
7. Support missing-person coordination.
8. Provide disaster-risk information.
9. Enable real-time emergency communication.
10. Help administrators monitor disaster-response activities.

---

## 🚀 Future Improvements

Possible future improvements include:

* �
