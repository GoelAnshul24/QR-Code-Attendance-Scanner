# System Architecture

## Overview

The QR Code Attendance Scanner is a Python-based event management system that combines participant data management, QR code verification, attendance tracking, and email communication.

## Architecture Flow

```text
Participant Dataset
        |
        v
+---------------------+
| Email Ticket Sender |
+---------------------+
        |
        v
 Generate QR Ticket
        |
        v
     Participant
        |
        | Presents QR Code
        v
+---------------------+
| Attendance Scanner  |
+---------------------+
        |
        v
 Extract Unique ID
        |
        v
 Verify Participant
        |
        v
 Check Attendance Status
        |
        v
 Update Attendance Record
        |
        v
 Send Confirmation Email
```

## Core Components

### 1. Attendance Scanner

`attendance_scanner.py`

Responsible for:

- Accessing the camera
- Detecting and scanning QR codes
- Extracting participant identifiers
- Verifying participant information
- Recording attendance
- Preventing duplicate attendance entries

### 2. Email and Ticket Module

`email_ticket_sender.py`

Responsible for:

- Generating participant tickets
- Creating unique QR codes
- Generating PDF tickets
- Preparing email content
- Sending tickets and confirmations through email

### 3. Participant Data

Participant information is stored in CSV or Excel format.

Typical fields include:

```text
Name
Email
UniqueID
Attendance Status
```

A fictional dataset is available at:

`sample_data/sample_participants.csv`

### 4. Environment Configuration

Email credentials and other sensitive configuration values are stored locally using environment variables.

Real credentials are excluded from Git version control through `.gitignore`.

An example configuration is provided in:

`.env.example`

## Technologies

| Technology | Purpose |
|---|---|
| Python | Core application development |
| Tkinter | Desktop GUI |
| OpenCV | Camera and QR scanning |
| Pandas | Participant data processing |
| ReportLab | PDF ticket generation |
| SMTP | Email communication |
| python-dotenv | Environment configuration |

## Design Goals

The system is designed around:

- Simple participant verification
- Fast event check-in
- Duplicate attendance prevention
- Automated participant communication
- Secure credential handling
- Easy deployment on a local computer
