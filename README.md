<div align="center">

# University Examination Scheduling System

*An automated, high-performance Flask application engineered to optimize examination schedules, mitigate resource conflicts, and maximize classroom utilization through algorithmic planning.*

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Framework-black.svg?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![SQLite](https://img.shields.io/badge/SQLite-Database-003B57.svg?logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

---

## Quick Access

| Section | Description |
| :--- | :--- |
| **Purpose & Scope** | System objectives and core deliverables |
| **Installation** | Environment setup and initialization procedures |
| **Execution** | Application startup parameters and commands |
| **Architecture** | System layers, routing, and responsibilities |
| **Configuration** | Environment variables and database connectivity |
| **Workflow** | Dashboard navigation and scheduling lifecycle |

---

## Purpose & Scope

| Objective | Detailed Description |
| :--- | :--- |
| **Automation** | Eliminates manual intervention and dependencies in the exam scheduling lifecycle. |
| **Conflict Resolution** | Mitigates scheduling overlaps for both students and academic personnel. |
| **Resource Optimization** | Maximizes the efficiency of spatial allocations based on classroom capacities. |
| **Administrative Efficiency** | Streamlines operational tracking and generates comprehensive analytical reports. |

---

## Key Features

* **Algorithmic Scheduling:** Automated examination allocation utilizing a custom constraint-satisfaction algorithm.
* **Academic Management:** Comprehensive administration modules for students, courses, and faculty members.
* **Capacity Tracking:** Intelligent classroom management with strict capacity limit enforcement.
* **Secure Authorization:** Role-based access control (RBAC) and secure administrative dashboard operations.
* **Data Integration:** Seamless bulk data import and export operations via CSV pipelines.

---

## Prerequisites & Installation

### System Requirements

| Component | Minimum Version |
| :--- | :---: |
| **Python** | `3.8+` |
| **Package Manager** | `pip` |

### Environment Setup

1. **Initialize a virtual environment:**
   ```bash
   python -m venv venv
   
```

2. **Activate the environment:**
   * **PowerShell:** `.\venv\Scripts\Activate.ps1`
   * **Command Prompt:** `.\venv\Scripts\activate.bat`
   * **Linux/macOS:** `source venv/bin/activate`

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   
```

---

## Execution

| Environment / OS | Execution Command |
| :--- | :--- |
| **Direct Execution** | `python app.py` |
| **Windows Shell** | `.\run.bat` |
| **Linux/macOS Shell** | `./run.sh` |

> **Note:** Once initialized, the application will be accessible at `http://127.0.0.1:5000`.

---

## System Architecture & Directory Structure

```text
project-root/
├── app.py                     # Application entry point
├── config.py                  # Environment configurations
├── requirements.txt           # Dependency declarations
├── models/                    # Data Access Layer (SQLAlchemy ORM)
├── routes/                    # Business Logic Layer (Flask Blueprints)
├── templates/                 # Presentation Layer (Jinja2 Templates)
├── static/                    # Static Assets (CSS, JavaScript)
└── algorithms/
    └── planlama_algoritmasi.py # Core Scheduling Algorithm
```

### Core Scheduling Algorithm

The scheduling logic is centralized within `algorithms/planlama_algoritmasi.py` and strictly evaluates the following criteria:
1. **Student Isolation:** Prevents concurrent exam assignments for any individual student.
2. **Spatial Constraints:** Ensures examination allocations strictly adhere to physical classroom capacities.
3. **Temporal Optimization:** Maximizes the utilization density of available academic time slots.

---

## Database Configuration

| Attribute | Implementation Detail |
| :--- | :--- |
| **ORM Framework** | SQLAlchemy |
| **Default Engine** | SQLite |
| **Connection String** | `sqlite:///data.db` |

To inspect or debug the current database schema state, execute:
```bash
python veritabani_goruntule.py
```

---

## Environment Variables

For production environments, ensure the following variables are properly configured.

| Variable | Purpose | Example Value |
| :--- | :--- | :--- |
| `FLASK_ENV` | Defines the runtime environment | `development` |
| `SECRET_KEY` | Cryptographic key for session management | `your-secure-secret` |
| `DATABASE_URL` | Defines the database target | `sqlite:///data.db` |

*Example configuration (Linux/macOS):*
```bash
export FLASK_ENV=development
export SECRET_KEY=supersecretkey
export DATABASE_URL=sqlite:///data.db
```

---

## Operational Workflow

1. **Initialize Data:** Populate foundational parameters (classrooms, terms) via the administrative panel.
2. **Bulk Import:** Ingest student and course registry data utilizing the CSV integration module.
3. **Execute Algorithm:** Trigger the automated examination scheduling sequence.
4. **Validate & Export:** Review the generated schedules through the analytics interface and export as necessary.


<div align="center">

Distributed under the **MIT License**.

</div>
