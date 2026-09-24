# MedFind AI 🩺

> **Find the right doctor, faster.**

MedFind AI is an AI-powered healthcare navigation and appointment-booking prototype that helps users identify the appropriate medical specialty from their symptoms or healthcare needs and find a suitable doctor.

Instead of requiring users to know which specialist they need, MedFind AI allows them to describe their problem in natural language. The Care Navigator analyzes the input, identifies relevant medical specialties, and presents matching doctors with information such as specialization, experience, qualifications, consultation fees, availability, location, ratings, and reviews.

Users can then select a doctor, choose an appointment slot, complete a simulated payment flow, and receive a booking confirmation.

> **Note:** This repository currently represents a prototype/demo. It does not provide medical diagnosis, real payment processing, or production healthcare services.

---

## ✨ Features

### 🤖 AI Care Navigator

* Conversational interface for describing healthcare needs.
* Extracts relevant specialty keywords from user input.
* Maps common phrases to medical specialties.
* Suggests appropriate doctors based on the detected specialty.
* Includes a safety disclaimer that the navigator does not diagnose conditions.

### 👨‍⚕️ Doctor Discovery

Users can explore doctor profiles containing:

* Doctor name
* Medical specialty
* Sub-specialty
* Qualifications
* Experience
* Consultation fee
* Hospital/clinic
* Location
* Languages
* Availability
* Ratings and review counts
* Patient review snippets

### 📅 Appointment Booking

* Select a doctor.
* Select an appointment date.
* Select an available time slot.
* Review appointment details.
* Continue through the booking/payment flow.
* Receive a booking confirmation and booking ID.

### 💳 Demo Payment Flow

The application contains a simulated checkout experience supporting:

* UPI
* Card
* Net Banking
* Wallet

The payment process is intentionally simulated for demonstration purposes and does **not** process real financial transactions.

### 📋 Booking Management

Users can:

* View previous appointments.
* See booking IDs.
* View appointment status.
* View payment status.
* Book the same doctor again.
* Remove bookings.

### 👤 Patient Profile

Users can maintain a basic profile containing:

* Name
* Phone number
* Email
* Preferred location

The prototype stores this information locally in the browser.

### 📱 Responsive Interface

The interface is designed to work across desktop and mobile screen sizes and includes:

* Responsive layouts
* Mobile navigation
* Interactive cards
* Loading states
* Toast notifications
* Modal-based AI Care Navigator
* Appointment and payment states

---

## 🧠 How It Works

The current prototype follows this flow:

```text
User describes symptoms / healthcare requirement
                    │
                    ▼
            AI Care Navigator
                    │
                    ▼
       Specialty / keyword detection
                    │
                    ▼
          Matching doctor profiles
                    │
                    ▼
           Doctor profile review
                    │
                    ▼
          Appointment slot selection
                    │
                    ▼
            Demo payment checkout
                    │
                    ▼
          Booking confirmation
                    │
                    ▼
             Booking history
```

For example:

```text
"I have a skin rash and itching"
              ↓
       Dermatologist
              ↓
     Matching doctors
              ↓
       Select doctor
              ↓
      Select appointment
              ↓
       Confirm booking
```

---

## 🏗️ Current Architecture

The current version is intentionally lightweight and is implemented primarily as a single HTML application.

```text
MedFind AI
│
├── HTML
│   └── Application structure and pages
│
├── CSS
│   └── Responsive UI and visual design
│
├── JavaScript
│   ├── Care Navigator
│   ├── Specialty matching
│   ├── Doctor database
│   ├── Doctor profiles
│   ├── Appointment slots
│   ├── Payment simulation
│   ├── Booking management
│   └── Patient profile
│
└── Browser localStorage
    ├── Patient profile
    └── Appointment history
```

The prototype currently contains a local doctor dataset and performs specialty matching through predefined specialties and aliases rather than calling an external AI model.

---

## 🛠️ Tech Stack

### Frontend

* HTML5
* CSS3
* Vanilla JavaScript
* Responsive CSS Grid/Flexbox
* Browser `localStorage`

### Current Backend

There is currently **no external backend**.

Doctor information, appointments, and profile data are handled within the browser for demonstration purposes.

### AI/NLP

The current prototype uses a rule-based specialty extraction system based on predefined keywords and aliases.

A future production version could replace this layer with:

* OpenAI API
* Google Gemini API
* Claude API
* A dedicated NLP model
* A medical-specialty classification model

---

## 🚀 Getting Started

Because the current version is a standalone HTML application, no complicated setup is required.

### 1. Clone the repository

```bash
git clone https://github.com/your-username/medfind-ai.git
cd medfind-ai
```

### 2. Open the application

Open the HTML file in a modern browser.

Alternatively, run a local development server:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

---

## 🧪 Example Queries

Try entering requests such as:

```text
I need a doctor for skin problems
```

```text
I have been experiencing headaches and dizziness
```

```text
I need a heart specialist
```

```text
I need a doctor for my child
```

```text
I need help with a bone problem
```

The prototype maps recognized phrases to specialties such as:

* Dermatologist
* Cardiologist
* Neurologist
* Pediatrician
* Orthopedic Surgeon
* Gynecologist
* Ophthalmologist
* ENT Specialist
* Nephrologist
* Gastroenterologist
* Diabetologist
* Dentist
* Psychiatrist
* Physiotherapist
* General Physician

---

## ⚠️ Important Limitations

MedFind AI is currently a **prototype and demonstration project**.

### Not a medical diagnostic system

The Care Navigator is intended to help users navigate to an appropriate medical specialty. It should not be used to diagnose diseases or determine treatment.

The interface itself communicates that the navigator does not diagnose and directs users toward emergency services for emergencies.

### Demo doctor data

Doctor profiles are currently stored as application data rather than retrieved from a verified healthcare provider database.

### Demo payments

Payment authorization is simulated. No real financial transaction is processed.

### Local storage

Patient profiles and booking information are stored in the browser using `localStorage`, rather than a secure healthcare backend.

### No real appointment provider integration

The current appointment slots are demonstration slots and are not synchronized with real hospital/doctor calendars.

---

## 🔐 Production Roadmap

A production-ready version would require significantly more infrastructure.

### Phase 1 — Real AI

Replace rule-based keyword matching with an actual NLP/LLM pipeline.

```text
User symptoms
     ↓
LLM / NLP model
     ↓
Structured symptom extraction
     ↓
Specialty classification
     ↓
Doctor matching
```

The AI should return structured data rather than simply generating free-form text.

Example:

```json
{
  "specialty": "Dermatologist",
  "confidence": 0.91,
  "symptoms": [
    "skin rash",
    "itching"
  ]
}
```

### Phase 2 — Backend

Introduce a backend such as:

* Node.js / Express
* FastAPI
* Django
* Spring Boot

with a database such as:

* PostgreSQL
* MySQL
* MongoDB

### Phase 3 — Authentication

Add:

* Patient accounts
* Doctor accounts
* Secure authentication
* Role-based authorization
* Password hashing
* Session/token management

### Phase 4 — Real Doctor Data

Integrate a verified provider database containing:

* Doctor credentials
* Specializations
* Locations
* Availability
* Consultation fees
* Appointment calendars

### Phase 5 — Real Appointment Scheduling

Connect doctor calendars and appointment management systems so availability is real-time rather than simulated.

### Phase 6 — Secure Payments

Integrate a real payment provider such as a supported payment gateway and move all payment processing to a secure backend.

### Phase 7 — Healthcare Security

A production healthcare system would need appropriate privacy and security controls, including:

* Encryption
* Secure authentication
* Access control
* Audit logging
* Data minimization
* Secure API design
* Appropriate regulatory/privacy compliance for the target jurisdiction

---

## 🎯 Future Improvements

Potential extensions include:

* Multilingual symptom input
* Voice-based Care Navigator
* Location-aware doctor discovery
* Hospital search
* Telemedicine appointments
* Prescription/document uploads
* Doctor-side dashboard
* Hospital administration dashboard
* Appointment reminders
* Email/SMS notifications
* Calendar integration
* Insurance information
* Emergency-care routing
* Accessibility improvements
* Explainable specialty recommendations
* AI confidence indicators
* Medical knowledge retrieval with citations
* Structured symptom extraction
* Conversation history

---

## 📊 Project Status

| Component                        | Status            |
| -------------------------------- | ----------------- |
| Landing page                     | ✅ Complete        |
| Care Navigator UI                | ✅ Complete        |
| Specialty keyword matching       | ✅ Prototype       |
| Doctor discovery                 | ✅ Complete        |
| Doctor profiles                  | ✅ Complete        |
| Appointment slots                | ✅ Demo            |
| Payment UI                       | ✅ Demo            |
| Booking confirmation             | ✅ Complete        |
| Booking history                  | ✅ Complete        |
| Patient profile                  | ✅ Complete        |
| Backend                          | ❌ Not implemented |
| Real AI/LLM integration          | ❌ Not implemented |
| Real doctor database             | ❌ Not implemented |
| Real appointment synchronization | ❌ Not implemented |
| Real payment processing          | ❌ Not implemented |
| Production healthcare security   | ❌ Not implemented |

---

## 💡 Why MedFind AI?

Healthcare navigation can be difficult when users know their symptoms but do not know which medical specialist they should consult.

MedFind AI addresses this specific usability problem by creating a simple conversational entry point:

> **Describe the problem → Find the relevant specialty → Compare doctors → Book an appointment**

The goal is not to replace doctors or provide diagnoses. The goal is to reduce friction between a patient's healthcare concern and the process of finding the appropriate medical professional.

---

## 👨‍💻 Project

**MedFind AI**

An AI-assisted healthcare navigation and appointment-booking prototype.

Built as a demonstration of conversational healthcare navigation, doctor discovery, appointment scheduling, and user-centered frontend design.
