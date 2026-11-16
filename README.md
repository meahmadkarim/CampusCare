# CampusCare

A centralized, AI-assisted complaint management platform designed for the University of Central Asia, Naryn Campus.

[![Development Status: Actively Under Development](https://img.shields.io/badge/development_status-actively_under_development-yellow.svg)](https://github.com/meahmadkarim/CampusCare)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/meahmadkarim/CampusCare)](https://github.com/meahmadkarim/CampusCare/issues)

---

## Project Overview

CampusCare is a web application that streamlines how students submit campus issues and how university departments receive, assign, track, and resolve them. The system includes student complaint submission, automatic departmental classification, department-specific dashboards, staff assignment, complaint status tracking, and administrative oversight.

**Important:** CampusCare is an independently developed student project and is not an officially deployed University of Central Asia service. The repository **does not** imply university endorsement or operational status.

---

## Problem Statement

University campuses generate numerous student complaints and notifications each day. Without a centralized system, complaints are often:
- Lost in email inboxes or paper filing systems
- Misdirected to incorrect departments
- Delayed in receiving initial responses
- Difficult to track from submission to resolution
- Lacking analytics and oversight

CampusCare addresses these challenges by providing a single platform for complaint management, automated routing, status tracking, and departmental analytics.

---

## Project Objectives

1. **Centralize** complaint collection in one accessible platform
2. **Automate** initial routing using AI-assisted classification
3. **Enable** transparent status tracking for students
4. **Support** department heads in managing complaint workflows
5. **Provide** administrative oversight and analytics
6. **Ensure** data privacy and security
7. **Demonstrate** the value of ML-assisted campus services

---

## Planned Core Features

| Feature | Status |
|---------|--------|
| Student authentication and authorization | Planned |
| Complaint submission using text and optional photographs | Planned |
| Automatic departmental classification using ML models | Planned |
| Five administrative departments (Maintenance, IT, Security, Academic, Student Affairs) | Planned |
| Department-specific dashboards | Planned |
| Department heads assigning complaints to individual staff members | Planned |
| Complaint status tracking | Planned |
| Dashboard and email notifications for department heads | Planned |
| Student complaint history | Planned |
| Administrative oversight | Planned |
| Human review of uncertain AI predictions | Planned |
| Security, privacy, and access control | Planned |

*Note: These are planned features, not completed features.*

---

## Departmental Routing

Complaints are routed to these primary departments:

1. **Maintenance & Facilities** — Building and physical campus issues
2. **IT Department** — Hardware, software, network, and technical problems
3. **Security** — Campus safety, access control, and security incidents
4. **Academic Administration** — Grades, exams, attendance, course-related issues
5. **Student Affairs** — Housing, scholarships, student records, and peer support

A human review process handles uncertain or ambiguous predictions.

---

## High-Level System Architecture

```
┌─────────────┐
│   Students  │
└──────┬──────┘
       │ Submit complaints
       ▼
┌─────────────────────────────────────────────────────────────┐
│                    Backend API Layer                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐        │
│  │ Complaint    │  │ Classification│  │ Authorization│        │
│  │ Submission   │  │ Service       │  │ Service      │        │
│  └──────────────┘  └──────────────┘  └──────────────┘        │
└───────────────────────┬─────────────────────────────────────┘
                        │
         ┌──────────────┼──────────────┐
         ▼              ▼              ▼
┌───────────────┐ ┌───────────────┐ ┌───────────────┐
│  Database     │ │ ML Model      │ │   External    │
│  (PostgreSQL) │ │   Service     │ │ Services      │
└───────┬───────┘ └───────┬───────┘ └───────────────┘
        │                │
        └────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│                    Department Dashboards                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐        │
│  │   Maintenance│  │     IT       │  │    Security  │        │
│  └──────────────┘  └──────────────┘  └──────────────┘        │
│  ┌──────────────┐  ┌──────────────┐                          │
│  │  Academic    │  │  Student     │                          │
│  └──────────────┘  └──────────────┘                          │
└─────────────────────────────────────────────────────────────┘
```

*Note: The ML classification service shown above is an independent research project.*

---

## Relationship to CampusCare ML

CampusCare relies on an independent machine learning research project, **[CampusCare ML](https://github.com/meahmadkarim/campuscare-ml)**, to classify incoming complaints and route them to appropriate departments.

The two projects are independently maintained:

- **CampusCare**: Full-stack web application for complaint management, user workflows, authentication, and administrative dashboards.
- **CampusCare ML**: Machine learning research focusing on complaint classification using NLP, neural networks, and multimodal learning models.

The ML system will eventually communicate with CampusCare through a self-hosted inference interface. No external AI inference APIs (OpenAI, Gemini, Claude, etc.) will be used for classification.

For more information about ML research approaches and experimental plans, see the [CampusCare ML Repository](https://github.com/meahmadkarim/campuscare-ml).

---

## Technology Stack

 technologies marked with **⬜ TBD** have not been selected yet.

### Frontend
- **Framework:** ⬜ TBD
- **Language:** ⬜ TBD (JavaScript/TypeScript or Python)
- **UI Component Library:** ⬜ TBD
- **Styling:** ⬜ TBD
- **State Management:** ⬜ TBD

### Backend
- **Language/Framework:** ⬜ TBD (FastAPI/Flask or Django)
- **Database:** 🟡 **PostgreSQL**
- **ORM/Object Mapper:** ⬜ TBD
- **Authentication:** ⬜ TBD (JWT or OAuth)

### Machine Learning
- **Classification Engine:** ⬜ TBD (hosted separately in CampusCare ML)
- **ML Framework for Our System:** ⬜ TBD
- **Provided by:** ⬜ TBD (self-hosted inference interface)

### DevOps & Infrastructure
- **Containerization:** ⬜ TBD (Docker or Podman)
- **Cloud Provider:** ⬜ TBD
- **CI/CD:** ⬜ TBD

---

## Development Roadmap

See `docs/ROADMAP.md` for detailed milestones and progress tracking.

### Summary

- **Phase 1: Requirements and Architecture** — Requirements gathering, system design, database schema
- **Phase 2: User Interface and Student Workflows** — Student complaint submission, history view
- **Phase 3: Authentication and Database** — User authentication, data model implementation
- **Phase 4: Department Dashboards and Staff Assignment** — Admin workflows, staff management
- **Phase 5: ML Integration** — Connect to CampusCare ML classification service
- **Phase 6: Notifications and Tracking** — Email notifications, status updates
- **Phase 7: Testing, Security, and Deployment** — Testing strategy, secure deployment

---

## Current Progress

**Code Status:** Initial project structure established
**Status:** Actively Under Development

See `docs/ROADMAP.md` for detailed progress tracking.

---

## Planned Improvements

1. Implement core feature set (authentication, complaint submission, department routing)
2. Develop comprehensive test suite
3. Add email notification system
4. Implement analytics dashboards for administrators
5. Create mobile-responsive design
6. Add multi-language support
7. Enhance security with role-based access control
8. Deploy to staging and production environments

---

## Getting Started

> This repository currently contains only project planning and documentation. Core application code is not yet available.

### Prerequisites

- **Node.js** or **Python** (depending on chosen stack) — ⬜ TBD
- **Git** — See the [official Git documentation](https://git-scm.com/doc)
- **PostgreSQL** 12+ — For development database
- **Python 3.10+** (if not using Node.js) — ⬜ TBD

### Setup Instructions

**Coming Soon:** Detailed setup instructions will be added to `docs/SETUP.md` once the technology stack is selected.

If you wish to contribute before core features are implemented, please coordinate with the maintainers.

---

## Privacy and Security Considerations

### Student Data Privacy

- Student personal information is stored in the database with proper encryption at rest
- Access to sensitive data is restricted to authorized personnel only
- Data retention policies will be defined and implemented
- Students have the right to view and download their own complaint history

### Security Measures

- Authentication and role-based access control (status: ⬜ TBD)
- Rate limiting and abuse detection (status: ⬜ TBD)
- HTTPS/TLS encryption for all communications (status: ⬜ TBD)
- Regular security audits and penetration testing (status: ⬜ TBD)
- Secure password storage and handling (status: ⬜ TBD)

### Data Handling

- All data is stored and processed according to applicable data protection regulations
- Complaint content is handled in accordance with institutional policies
- No personally identifiable information (PII) is disclosed without authorization

---

## Project Status and Maintenance

**Status:** Actively Under Development

**Maintainer:** Ahmad Karim

**Contributing:**
- ✅ Feedback, ideas, and contributions are welcome
- ✅ Please read `docs/CONTRIBUTING.md` (coming soon) before submitting pull requests
- ✅ For urgent issues, use the [GitHub Issue Tracker](https://github.com/meahmadkarim/CampusCare/issues)

**Changes:**
This project is a work in progress. Do not make claims about completed features unless they are listed in the [Planned Core Features](#planned-core-features) table.

**Links:**
- **GitHub Repository:** [meahmadkarim/CampusCare](https://github.com/meahmadkarim/CampusCare)
- **ML Research Project:** [meahmadkarim/campuscare-ml](https://github.com/meahmadkarim/campuscare-ml)

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

**© 2025 Ahmad Karim. CampusCare is an independent student project.**