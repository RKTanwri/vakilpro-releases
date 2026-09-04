<div align="center">

# ⚖️ VakilPro

### Legal Practice Management System

**Made by a lawyer, for lawyers.**

A modern desktop application for managing legal cases, clients, hearings, diaries, documents, cause lists, invoicing, reminders, and day-to-day law-firm workflows.

<br />

![Electron](https://img.shields.io/badge/Electron-47848F?style=flat-square\&logo=electron\&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square\&logo=react\&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square\&logo=vite\&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square\&logo=nodedotjs\&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square\&logo=sqlite\&logoColor=white)

</div>

---

## Overview

**VakilPro** is a legal practice management system designed around the practical workflow of advocates and law firms.

It brings cases, clients, hearings, diary entries, documents, cause lists, billing, reminders, and related information into a single workspace.

The project focuses on building a practical digital workflow for legal professionals rather than simply providing a generic CRM or document management application.

### Core concept

```text
Client
  ↓
Case
  ├── Hearings
  ├── Diary
  ├── Documents
  ├── Cause List
  └── Billing
```

The goal is to keep information connected to the legal matter it belongs to.

---

## Features

### Case Management

* Create and manage legal cases
* Case numbers and titles
* Court information
* Case types
* Client and opposing-party information
* Case status
* Case notes
* Important dates
* Connected hearings
* Connected documents
* Activity history

### Client Management

* Centralized client records
* Client contact information
* Client-related cases
* Client documents
* Billing information
* Payment history
* Client-specific activity

### Hearings

* Multiple hearings per case
* Hearing dates
* Court information
* Hearing notes
* Hearing outcomes
* Next hearing dates
* Hearing history
* Chronological hearing timeline

### Hearing Reminders

* Upcoming hearing reminders
* Today's hearings
* Tomorrow's hearings
* Future hearing overview
* Client hearing reminders

### Cause Lists

* Daily cause-list management
* Cases listed for specific dates
* Court-wise organization
* Matter and hearing information
* Quick daily court overview

### Legal Diary

* Create diary entries
* Link entries to cases
* Record daily legal activities
* Add notes and follow-ups
* Maintain chronological matter history

### Document Management

* Upload and organize legal documents
* Document cards
* Case-linked documents
* Hearing-linked documents
* Diary-linked documents
* Multiple document uploads
* Document categorization
* Easy access to matter-related files

### Invoicing & Payments

* Create client invoices
* Record professional fees
* Track payments
* Track outstanding balances
* Maintain billing history
* Generate branded documents

### PDF Generation

VakilPro supports generation of professional PDF documents for relevant workflows, including:

* Invoices
* Receipts
* Reports
* Practice records
* Other system-generated documents

### Law-Firm Branding

The application supports configurable branding for individual advocates and law firms.

Possible configuration includes:

* Firm name
* Advocate name
* Logo
* Address
* Contact information
* Document branding

### Dashboard

The dashboard provides an overview of important practice activity, including:

* Total cases
* Active cases
* Today's hearings
* Tomorrow's hearings
* Upcoming hearings
* Recent activity
* Billing information
* Outstanding amounts

### Activity Timeline

A centralized activity timeline provides a chronological view of important actions across the practice.

---

## Application Architecture

VakilPro is built as a desktop application using a modern web technology stack.

```text
┌──────────────────────────────┐
│          VakilPro             │
├──────────────────────────────┤
│          React UI             │
├──────────────────────────────┤
│        Electron Shell         │
├──────────────────────────────┤
│       Application Logic       │
├──────────────────────────────┤
│       SQLite Database         │
└──────────────────────────────┘
```

### Technology Stack

| Technology | Purpose                           |
| ---------- | --------------------------------- |
| Electron   | Desktop application framework     |
| React      | User interface                    |
| Vite       | Frontend tooling and development  |
| Node.js    | Application/backend functionality |
| SQLite     | Local database                    |
| JavaScript | Primary development language      |

---

## Local-First Design

VakilPro is designed with a local-first approach.

The application's core data is stored locally using SQLite, allowing the application to operate without requiring constant internet connectivity.

This architecture is particularly useful for legal practices where:

* Internet connectivity may be unreliable
* Fast local access is important
* Data needs to remain available offline
* The application should work as a standalone desktop system

---

## Data Relationships

VakilPro is designed around interconnected legal entities.

A simplified data relationship can be represented as:

```text
                 ┌─────────────┐
                 │   Client    │
                 └──────┬──────┘
                        │
                        ▼
                 ┌─────────────┐
                 │    Case     │
                 └──────┬──────┘
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
     ┌─────────┐   ┌─────────┐   ┌───────────┐
     │Hearings │   │  Diary  │   │ Documents │
     └────┬────┘   └────┬────┘   └─────┬─────┘
          │             │              │
          └─────────────┼──────────────┘
                        ▼
                 ┌─────────────┐
                 │    Case     │
                 │   History   │
                 └─────────────┘

                        │
                        ▼
                 ┌─────────────┐
                 │   Billing   │
                 └─────────────┘
```

---

## Project Structure

The exact structure may evolve as the application develops, but the project is organized around the separation of UI, application logic, database operations, and desktop functionality.

```text
VakilPro/
│
├── src/
│   ├── components/
│   ├── pages/
│   ├── modules/
│   ├── hooks/
│   ├── services/
│   └── utils/
│
├── electron/
│   ├── main/
│   ├── preload/
│   └── ipc/
│
├── database/
│
├── public/
│
├── assets/
│
├── package.json
├── vite.config.*
└── README.md
```

> The structure may change as development progresses.

---

## Main Modules

```text
Dashboard
│
├── Cases
│   ├── Case Details
│   ├── Hearings
│   ├── Diary
│   ├── Documents
│   └── History
│
├── Clients
│
├── Hearings
│
├── Cause Lists
│
├── Diary
│
├── Documents
│
├── Invoices
│
├── Payments
│
└── Settings
```

---

## Workflow

A typical legal matter can be managed through the following workflow:

```text
Add Client
    ↓
Create Case
    ↓
Add Case Information
    ↓
Schedule Hearing
    ↓
Prepare Cause List
    ↓
Attend Hearing
    ↓
Record Outcome
    ↓
Schedule Next Hearing
    ↓
Update Diary
    ↓
Attach Documents
    ↓
Manage Billing
    ↓
Continue Case History
```

This workflow is one of the core design principles behind VakilPro.

---

## Design Philosophy

VakilPro is built around several principles:

### 1. Workflow First

The application should follow how lawyers actually work rather than forcing users into an artificial software workflow.

### 2. Connected Information

Cases, clients, hearings, documents, diary entries, and billing should remain connected.

### 3. Minimal Data Duplication

Information should be entered once and reused throughout the application wherever possible.

### 4. Offline Accessibility

Core legal information should remain accessible without depending entirely on an internet connection.

### 5. Professional Output

Generated documents should be suitable for professional use and customizable to the advocate or firm's branding.

### 6. Simplicity

Legal software should reduce administrative complexity rather than create more of it.

---

## Security & Privacy

Legal applications handle sensitive information, so privacy and data security are important design considerations.

VakilPro's local-first architecture reduces the need to transmit routine application data to external services.

Security considerations include:

* Local database storage
* Controlled application access
* License validation
* Device identification
* Separation of application and licensing infrastructure
* Protection of sensitive legal records

Production deployments should additionally follow appropriate operating-system security, database protection, backup, and access-control practices.

---

## Licensing

VakilPro uses a licensing system for controlled distribution of the application.

The licensing infrastructure is designed to support:

* Trial periods
* Time-based licenses
* License approval
* License expiration
* License revocation
* Multiple registered devices
* Central license administration

The application itself and its licensing infrastructure are separate components.

---

## Development Status

VakilPro is an actively developed project.

Current development focuses on improving:

* Legal workflows
* User experience
* Case management
* Hearing management
* Document workflows
* PDF generation
* Billing
* Licensing
* Performance
* Reliability
* Offline-first functionality

Features and architecture may change as the product evolves.

---

## Roadmap

Potential areas of future development include:

* Advanced reporting
* Improved analytics
* More document automation
* Advanced client communication
* Expanded notification workflows
* Additional PDF templates
* Improved backup and restore
* Multi-user workflows
* LAN-based office deployment
* Additional automation
* AI-assisted legal workflows

---

## Screenshots

Screenshots of the application will be added here as the interface develops.

### Dashboard

*Add screenshot here*

### Case Management

*Add screenshot here*

### Hearings

*Add screenshot here*

### Documents

*Add screenshot here*

### Client Management

*Add screenshot here*

---

## Who Is VakilPro For?

VakilPro is designed primarily for:

* Advocates
* Law firms
* Legal practitioners
* Legal assistants
* Law-office staff
* Small and medium-sized legal practices

The system is particularly suited to practices that currently rely on a combination of notebooks, spreadsheets, folders, calendars, and messaging applications to manage their legal work.

---

## Project Vision

VakilPro aims to become more than a case-management application.

The long-term vision is to create a **complete digital operating system for legal practices**.

```text
                ┌───────────────────┐
                │     VAKILPRO      │
                │  Legal Practice   │
                │    Workspace      │
                └─────────┬─────────┘
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
       ▼                  ▼                  ▼
   CASEWORK            CLIENTS          DOCUMENTS
       │                  │                  │
       ├── Hearings       ├── Cases         ├── Files
       ├── Diary          ├── Billing       ├── Orders
       └── History        └── Activity      └── Records
                          │
                          ▼
                    BILLING & OPS
```

The objective is to bring the operational side of legal practice into one coherent system.

---

## Built With Purpose

VakilPro is being developed with a simple philosophy:

> **Lawyers should not have to adapt their practice to software. The software should adapt to the way lawyers work.**

---

## Author

**Rehmat Tanwri**

Law Student • Web Developer • Realtor • Forex Trader

Interested in building practical software systems, business workflows, legal technology, and automation.

---

<div align="center">

### ⚖️ VakilPro

**Made by a lawyer, for lawyers.**

</div>
