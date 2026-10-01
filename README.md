# QR Code Attendance Scanner

A Python-based event attendance management system designed to simplify participant verification and attendance tracking using QR codes.

The application provides a Tkinter-based interface for scanning participant QR codes, validating participant information, recording attendance, and sending email confirmations. It also supports participant data management through CSV and Excel files.

## Key Features

- **QR Code Scanning** - Scan unique participant QR codes using OpenCV.
- **Participant Verification** - Match scanned QR data with registered participant records.
- **Attendance Tracking** - Automatically record attendance and update participant status.
- **Duplicate Prevention** - Prevent repeated attendance entries for already scanned participants.
- **Email Confirmation** - Send confirmation emails to participants after successful verification.
- **PDF Ticket Generation** - Generate personalized event tickets containing participant details and unique QR codes.
- **CSV and Excel Integration** - Import and manage participant information using structured data files.
- **Email Templates** - Load reusable email templates and customize the subject and message.
- **Email Preview** - Review email content before sending.
- **Scheduled Emails** - Schedule participant emails for a specified time.
- **Progress Monitoring** - Track the email sending process through a visual progress indicator.

## Tech Stack

- **Python**
- **Tkinter** - Graphical User Interface
- **OpenCV** - QR code scanning and camera processing
- **Pandas** - Participant data handling
- **ReportLab** - PDF ticket generation
- **QR Code** - Unique participant QR generation
- **SMTP** - Email delivery
- **python-dotenv** - Secure environment variable management

## How It Works

```text
Participant Data
       |
       v
Unique QR Code / Ticket
       |
       v
QR Code Scanner
       |
       v
Extract Participant ID
       |
       v
Verify Participant Record
       |
       v
Check Attendance Status
       |
       v
Record Attendance
       |
       v
Send Confirmation
```

The scanner reads the QR code and extracts the participant's unique identifier. The identifier is checked against the participant dataset. After successful verification, the participant's attendance status is updated and a confirmation can be sent through email.

## Project Structure

```text
QR-Code-Attendance-Scanner/
|
|-- attendance_scanner.py
|-- email_ticket_sender.py
|-- requirements.txt
|-- .gitignore
|-- README.md
|-- Features and Functionality.md
`-- PROJECT_DEEP_ANALYSIS.md
```

### Main Files

- `attendance_scanner.py` - Handles QR scanning, participant verification, and attendance tracking.
- `email_ticket_sender.py` - Handles ticket generation and email-related functionality.
- `requirements.txt` - Contains the Python dependencies required to run the project.
- `Features and Functionality.md` - Detailed explanation of the system's functionality.
- `PROJECT_DEEP_ANALYSIS.md` - Extended technical analysis and project documentation.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/GoelAnshul24/QR-Code-Attendance-Scanner.git
cd QR-Code-Attendance-Scanner
```

### 2. Install dependencies

Make sure Python 3 is installed, then run:

```bash
pip install -r requirements.txt
```

### 3. Configure email credentials

Create an environment file locally for the required email credentials.

Example:

```env
EMAIL_USER=your-email@example.com
EMAIL_PASS=your-app-password
```

Never commit real passwords, app passwords, API keys, or other credentials to the repository.

### 4. Run the application

```bash
python attendance_scanner.py
```

## Usage

1. Select the participant data file containing fields such as Name, Email, and Unique ID.
2. Start the QR scanner from the application.
3. Scan the participant's QR code.
4. The system validates the participant against the registered data.
5. Attendance is recorded after successful verification.
6. Duplicate attendance entries are prevented.
7. Confirmation emails can be sent to successfully verified participants.
8. Updated attendance information can be stored for further analysis.

### Sample Participant Data

A fictional sample dataset is included to demonstrate the expected participant data format:

`sample_data/sample_participants.csv`

The dataset follows the structure:

| Name | Email | UniqueID |
|------|-------|----------|
| Anshul Goel | anshul.goel@example.com | EVT001 |
| Meera Gupta | meera.gupta@example.com | EVT002 |
| Rohan Verma | rohan.verma@example.com | EVT003 |

The sample records are fictional and are provided only for testing and demonstration purposes. Real participant information should not be committed to the repository.

## Security

Sensitive information such as email credentials is excluded from version control using `.gitignore`.

Real participant datasets should not be committed to a public repository. Sample or anonymized data should be used when demonstrating the application.

## Project Documentation

For additional technical information, see:

- [Features and Functionality](./Features%20and%20Functionality.md)
- [Project Deep Analysis](./PROJECT_DEEP_ANALYSIS.md)

## Contributors

This project was developed collaboratively as a group project.

**Anshul Goel** - Project contributor

Additional contributors and their respective contributions can be acknowledged here.

## Future Improvements

- Add a centralized database for participant and attendance records.
- Develop a web-based dashboard for attendance analytics.
- Improve QR verification and error handling.
- Add role-based access for event administrators.
- Provide real-time attendance statistics.
- Deploy the system as a web or cloud-based application.

## Disclaimer

This repository is maintained as a portfolio and academic project. Any participant information used for demonstrations should be fictional, anonymized, or used with appropriate permission.
