# Smart BloodLink

A beginner-friendly Flask prototype for coordinating urgent blood requests with a hospital network.

## Features
- Dashboard with hospitals, requests, low-stock entries, and listed blood units
- Create an urgent blood request
- Add hospital records and update blood inventory
- Demo alert history (does not place calls by default)
- Optional Twilio voice-call integration for verified hospitals
- SQLite database created automatically

## Run locally
1. Install Python 3.10 or newer.
2. Open this folder in VS Code.
3. In the VS Code terminal, create a virtual environment (recommended):

   **Windows**
   ```bash
   py -m venv .venv
   .venv\Scripts\activate
   ```

   **macOS/Linux**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
5. Copy `.env.example` to `.env`.
6. Start the app:
   ```bash
   python app.py
   ```
7. Open http://127.0.0.1:5000 in your browser.

The first run creates `smart_bloodlink.db` and adds sample hospitals and sample inventory. The sample data is fictional; replace it with verified information.

## Optional Twilio calling
Real calls require a Twilio account, approved/authorized recipient numbers, account credentials, a public HTTPS URL, and compliance with applicable calling/privacy rules. Put credentials only in `.env`; never publish them. Set all four Twilio settings in `.env`. Only hospital records marked verified are eligible for real calls. In this starter, a call plays a scripted announcement; it is not a full conversational AI agent and it does not automatically confirm blood availability.

**Before any public/production deployment, add authentication and role-based access, CSRF protection, Twilio webhook signature validation, audit logging, rate limits, consent/legal review, encryption and a secure patient-data policy.** The demo verification status is only a manual database flag, not proof of a real hospital's identity. Do not use this prototype for clinical decisions. Always confirm inventory and compatibility directly with qualified hospital/blood-bank staff. In a medical emergency, contact local emergency services and the treating hospital.
