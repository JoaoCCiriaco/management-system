# Soluinsect - Pest Control Management System

An operations management and automation system designed for bait station monitoring, client tracking, and field inspection control in pest control services.

---

### 🎥 Video Walkthrough
Watch a complete video demonstration of the system in action:
**[Watch the Soluinsect System Demonstration on YouTube](https://youtu.be/YRD8hG1N2X8)**

---

### Overview
In professional pest control operations, tracking monitoring devices and bait stations across multiple client locations requires precise record-keeping. The **Soluinsect Management System** centralizes clients, installed bait stations, and technician field inspections into a single web platform.

Instead of relying on manual paper logs, technicians can scan individual **QR Codes** attached to each bait station in the field to instantly log new inspection data, track bait consumption, and update equipment status.

---

### Key Features

#### Interactive Dashboard
- Summary cards displaying total bait stations, active vs. inactive units, registered clients, total inspections, and bait consumption counts.
- **Chart.js** integration visualizing bait consumption ratios (consumption vs. no consumption).
- Quick-view section showcasing the most recent inspection logs (client, location, station ID, technician, date/time, bait consumption, and notes).

#### Client Management
- Register, edit, and manage client profiles (Name, Phone, Email).
- Cascade deletion logic: removing a client automatically cleans up linked bait stations and past inspection logs to maintain database integrity.

#### Bait Station & Device Tracking
- Associate bait stations and monitoring devices directly with specific clients and locations.
- Track station parameters: Assigned Client, Installation Location, Status (Active/Inactive), and Unique Station ID.
- Dedicated history view for each station to review chronological inspection logs.

#### Inspection Logging
- Record inspection timestamp, assigned technician, bait consumption status (consumed vs. intact), and detailed field notes.
- Linked directly to specific stations to build an auditable service history.

#### QR Code Field Integration
- Automatically generates a unique **QR Code** for each registered station using **QRCode.js**.
- Scanning the physical QR Code on a device redirects technicians straight to the new inspection entry form for that exact unit.
- Includes a print-friendly page layout for easy physical sticker printing.

---

### Tech Stack
- **Backend:** Python, Flask
- **Database:** SQLite
- **Frontend:** HTML5, CSS3, JavaScript
- **Libraries:** Chart.js (Data Visualization), QRCode.js (Dynamic QR Generation)

---

### Database Architecture
The application uses SQLite with relational database design managed by `database.py`:
- **Clients ➔ Stations:** One-to-Many relationship (A client owns multiple monitoring stations).
- **Stations ➔ Inspections:** One-to-Many relationship (A station holds multiple inspection records).

`app.py` handles business logic, route controllers, dynamic database queries, and CRUD operations.

---

### 📁 Project Structure

```text
├── app.py           # Main Flask application, routing, and controller logic
├── database.py      # Database initialization and schema creation
├── database.db      # SQLite database file
├── static/          # Static assets (CSS stylesheets, JS scripts)
│   └── styles.css   # Main UI stylesheet
└── templates/       # Jinja2 HTML page templates
