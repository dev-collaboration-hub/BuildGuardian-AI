# BuildGuardian AI 🏗️🤖

An open-source, offline, and lightweight AI assistant for construction site management, worker tracking, payment monitoring, defect recording, and question answering.

BuildGuardian AI is designed mainly for homeowners and small construction projects where records are often scattered across notebooks, WhatsApp messages, photos, and verbal conversations.

The system stores construction data and allows users to ask simple questions in natural language. It can also speak the generated answer using an offline voice system.

---

## Project Goal

The goal of BuildGuardian AI is to create a lightweight construction assistant that helps property owners:

* Track workers and daily attendance
* Record payments and pending balances
* Monitor construction progress
* Manage materials
* Record defects and incomplete work
* Ask questions about stored construction data
* Receive spoken answers
* Detect possible overcharging or suspicious entries
* Maintain room-wise and floor-wise construction records

The project will initially use rule-based, retrieval-based, and symbolic AI techniques instead of relying on large language models or external AI APIs.

---

## Example Interaction

```text
User:
How much payment is pending for Sitaram?

BuildGuardian AI:
₹38,000 is pending for Sitaram. Underground water tank repair and mathod work are still incomplete.
```

```text
User:
How long did Ramesh work today?

BuildGuardian AI:
Ramesh arrived at 10:00 AM and left at 1:00 PM. His total recorded working time is 3 hours.
```

```text
User:
Which work is still pending on the second floor?

BuildGuardian AI:
The second-floor window adjustment, primer inspection, and two electrical switchboard fixes are still pending.
```

---

## Core Features

### Worker Management

* Store worker details
* Record worker role and skill
* Track attendance
* Record arrival and departure time
* Calculate total working hours
* Maintain worker quality ratings
* Track assigned and completed work

### Payment Management

* Record every payment
* Track total agreed amount
* Track paid and pending amount
* Link payments with specific work
* Store payment date and payment method
* Generate worker-wise payment history
* Warn about duplicate or unclear payments

### Material Management

* Record material purchases
* Track material quantity
* Store supplier and price information
* Maintain material usage records
* Track missing or damaged materials
* Record which worker received a material

### Construction Progress

* Track progress by floor
* Track progress by room
* Record completed and pending work
* Store daily construction updates
* Attach site photographs
* Generate progress summaries

### Defect Management

* Record construction defects
* Assign defects to workers
* Add location and severity
* Track repair status
* Store before-and-after photographs
* Maintain inspection history

### Question Answering

The AI will answer questions using stored construction records.

Supported question categories may include:

* Worker attendance
* Working hours
* Payments
* Pending balances
* Material usage
* Pending work
* Defects
* Room progress
* Daily progress
* Worker performance

### Voice Assistant

* Convert AI answers into speech
* Work without an internet connection
* Support simple voice commands
* Provide clear and short spoken responses

---

## AI Approach

BuildGuardian AI will not depend on a large language model in its first version.

The initial AI system will use:

* Keyword extraction
* Intent detection
* Entity recognition
* Rule-based reasoning
* Construction knowledge graphs
* Database retrieval
* Template-based response generation
* Context memory
* Confidence scoring

Example processing pipeline:

```text
User Question
      ↓
Text Normalization
      ↓
Intent Detection
      ↓
Entity Extraction
      ↓
Construction Database Search
      ↓
Reasoning Engine
      ↓
Response Generation
      ↓
Offline Text-to-Speech
```

---

## Planned Architecture

```text
buildguardian-ai/
│
├── src/
│   ├── assistant/
│   │   ├── question_parser.py
│   │   ├── intent_detector.py
│   │   ├── entity_extractor.py
│   │   ├── reasoning_engine.py
│   │   └── response_generator.py
│   │
│   ├── construction/
│   │   ├── workers.py
│   │   ├── attendance.py
│   │   ├── payments.py
│   │   ├── materials.py
│   │   ├── progress.py
│   │   └── defects.py
│   │
│   ├── memory/
│   │   ├── construction_memory.py
│   │   ├── conversation_memory.py
│   │   └── knowledge_store.py
│   │
│   ├── voice/
│   │   ├── speech_input.py
│   │   └── speech_output.py
│   │
│   ├── database/
│   │   ├── connection.py
│   │   ├── schema.py
│   │   └── repositories.py
│   │
│   └── interface/
│       ├── cli.py
│       └── web_dashboard.py
│
├── data/
│   ├── workers/
│   ├── payments/
│   ├── materials/
│   ├── progress/
│   └── defects/
│
├── tests/
├── documentation/
├── examples/
├── scripts/
├── LICENSE
├── CONTRIBUTING.md
├── ROADMAP.md
└── README.md
```

---

## Development Roadmap

### M1 — Construction Record System

Build the core construction data system.

* Worker records
* Attendance tracking
* Payment tracking
* Material records
* Defect records
* Room and floor records
* SQLite database

### M2 — Question Understanding

Create the first question-processing system.

* Text normalization
* Keyword extraction
* Intent detection
* Construction entity extraction
* Date and time understanding
* Question validation

### M3 — Construction Reasoning Engine

Create a rule-based reasoning system.

* Database retrieval
* Payment calculations
* Attendance calculations
* Pending-work reasoning
* Worker performance summaries
* Duplicate-payment detection
* Confidence scoring

### M4 — Response Generation

Generate simple and understandable answers.

* Response templates
* Hinglish response support
* Context-aware answers
* Error and missing-data responses
* Short and detailed answer modes

### M5 — Offline Voice Output

Allow the assistant to speak answers.

* Offline text-to-speech
* Voice configuration
* Speech queue
* Stop and repeat commands

### M6 — Voice Input

Allow users to ask questions by speaking.

* Offline speech recognition
* Voice command detection
* Noise handling
* Construction vocabulary support

### M7 — Owner Dashboard

Create a simple construction management dashboard.

* Worker dashboard
* Payment dashboard
* Material dashboard
* Progress dashboard
* Defect dashboard
* Search and filters

### M8 — Photo Inspection

Add construction image analysis.

* Room image records
* Crack detection
* Tile alignment checks
* Switchboard placement checks
* Surface defect detection
* Before-and-after comparison

### M9 — Risk and Fraud Alerts

Create owner-focused warning systems.

* Unusual payment alerts
* Duplicate charge detection
* Low working-hour warnings
* Material mismatch warnings
* Incomplete-work payment alerts
* Contractor quotation comparison

### M10 — BuildGuardian AI v1.0

Prepare the first stable release.

* Complete testing
* Documentation
* Sample construction dataset
* Installation package
* Performance optimization
* Privacy and backup system

---

## Technology Stack

The initial version may use:

* Python
* SQLite
* HTML
* CSS
* JavaScript
* Standard Python libraries
* Custom rule-based AI
* Lightweight offline speech components

The project aims to minimize heavy dependencies and remain usable on low-end computers.

---

## Design Principles

### Offline First

Construction records should remain accessible without an internet connection.

### Privacy Focused

Personal payments, property records, worker details, and site photographs should remain under the owner’s control.

### Lightweight

The assistant should run on regular CPU-based computers.

### Explainable

The system should explain which record was used to generate an answer.

### Owner Focused

The system should protect the property owner from confusion, missing records, unclear payments, and incomplete work.

### Modular

Every major component should be independently testable and replaceable.

---

## Sample Data Record

```json
{
  "worker_name": "Ramesh",
  "role": "Electrician",
  "date": "2026-07-25",
  "arrival_time": "10:00",
  "departure_time": "13:00",
  "assigned_work": "Install electrical switchboards",
  "completed_work": "Installed three switchboards",
  "payment_status": "Pending",
  "quality_rating": 3
}
```

---

## Target Users

BuildGuardian AI may be useful for:

* Homeowners
* Small contractors
* Site supervisors
* Civil engineering students
* Construction consultants
* Interior renovation teams
* Small property developers

---

## Current Project Status

The project is currently in the planning and architecture stage.

Initial development will focus on:

1. Construction data models
2. SQLite database design
3. Worker and payment records
4. Basic command-line interface
5. Rule-based question answering

---

## Contributing

Contributions are welcome.

You can contribute through:

* Feature development
* Bug fixes
* Documentation
* Test cases
* Construction domain knowledge
* Dataset design
* UI development
* Speech system development
* Computer vision research

Before contributing, please read `CONTRIBUTING.md`.

---

## Contribution Guidelines

* Keep modules small and understandable
* Avoid unnecessary heavy dependencies
* Add tests for new functionality
* Document important design decisions
* Do not include private construction records
* Use sample or anonymized data
* Follow the repository coding standards

---

## Security and Privacy

Do not upload real personal information, worker identification documents, private addresses, payment credentials, or confidential construction records to the public repository.

Use anonymized sample data for development and testing.

---

## License

This project is licensed under the MIT License.

See the `LICENSE` file for details.

---

## Project Vision

BuildGuardian AI aims to become a complete offline construction intelligence system that can understand site records, answer owner questions, identify problems, monitor expenses, and assist with construction decisions.

The long-term vision is to create a Jarvis-like assistant specifically designed for home construction and property management.

---

## Maintained By

Developed and maintained by the Dev Collaboration Hub community.
