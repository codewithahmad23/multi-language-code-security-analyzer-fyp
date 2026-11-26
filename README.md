<div align="center">

# Multi-Language Code Security and Quality Analyzer

**A Local Static Application Security Testing (SAST) & Code Quality Portal**

[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Django REST](https://img.shields.io/badge/Django%20REST-Framework-092E20?logo=django&logoColor=white)](https://www.django-rest-framework.org/)
[![React](https://img.shields.io/badge/React-Vite-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15%2B-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![SRS Version](https://img.shields.io/badge/SRS-v1.1%20Complete-success)](#documentation)

</div>

---

## Academic Information

| Attribute | Details |
| :--- | :--- |
| **Project Title** | Multi-Language Code Security and Quality Analyzer |
| **Student Name** | Muhammad Ahmad |
| **Roll Number** | `F23BINFT1E02015` |
| **Program** | BS Information Technology (8th Semester — Final Year Project) |
| **Supervisor** | Mr. Omer Riyaz |
| **Department** | Department of Information Technology, Faculty of Computing |
| **University** | The Islamia University of Bahawalpur (IUB) |

---

## Overview

Web applications developed in **Python** and **JavaScript/React** frequently accumulate security vulnerabilities and maintainability debt during active development. Executing untrusted student or team archives to test them dynamically poses security and environment-setup risks.

The **Multi-Language Code Security and Quality Analyzer** solves this through **100% local static analysis**—uploaded `.zip` archives are parsed into Abstract Syntax Trees without executing a single line of target code or sending source code to external cloud/AI services.

---

## Key Capabilities

* **Zero-Execution Multi-Language Parsing:**
  * **Python (`.py`):** Parsed via Python's native `ast` module.
  * **JavaScript & React (`.js`, `.jsx`):** Parsed via `tree-sitter` language bindings.
* **Hardened Archive Ingestion:** Enforces a 20 MB compressed limit, 100 MB extracted limit, 2,000-entry cap, SHA-256 integrity hashing, and strict rejection of path traversal (`..`), absolute paths, symbolic links, and encrypted archives.
* **Security Rule Engine (CWE-Mapped):**
  * **Hardcoded Secrets** (`CWE-798`) — High
  * **Intra-Function SQL String Construction** (`CWE-89`) — High
  * **Dangerous Execution Calls** (`eval`, `exec`, `os.system`, `shell=True`) (`CWE-78` / `CWE-95`) — High
  * **Debug Configuration Left Enabled** (`DEBUG = True`) (`CWE-489`) — Medium
  * **Weak Cryptographic Hashing** (`MD5`, `SHA1`) (`CWE-327`) — Medium
* **Code Quality Rule Engine:** Detects oversized functions (`> 50` physical lines), unused imports, and normalized AST duplicate function bodies.
* **Independent Dual Scoring & Triage:** Computes separate **Security Grade (`A–F`)** and **Quality Score (`0–100`)** normalized per `KLOC`, with interactive false-positive dismissal and live score recalculation.
* **Audit & Machine-Readable Exports:** Generates formatted **PDF** audit reports (via ReportLab), structured **JSON**, and compact **SARIF** outputs.

---

## Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend** | React (Vite), Tailwind CSS, Recharts |
| **Backend API** | Django REST Framework, JWT Authentication |
| **Static Analysis Engine** | Python `ast`, `tree-sitter` (JS/JSX grammars) |
| **Database** | PostgreSQL 15+ |
| **Reporting** | ReportLab (PDF), JSON, SARIF |

---

## Documentation

All formal project documentation is maintained inside the [`docs/`](./docs) directory:

| Document | Version | Direct Download | View in Repository | Status |
| :--- | :---: | :--- | :--- | :--- |
| **Software Requirement Specifications (SRS)** | `v1.1` | **[Download PDF (30 Pages)](https://raw.githubusercontent.com/codewithahmad23/multi-language-code-security-analyzer-fyp/main/docs/SRS_Multi_Language_Code_Securit.pdf)** | [DOCX](./docs/SRS_Multi_Language_Code_Security_Analyzer-2.docx) · [PDF](./docs/SRS_Multi_Language_Code_Securit.pdf) | Complete |
| **Software Design Document (SDD)** | — | *Upcoming* | — | Planned |

> **Note:** Click **Download PDF (30 Pages)** above to open or download the complete SRS v1.1 document (`FR001–FR012`, `NFR001–NFR013`, `UC001–UC012`, 15 UML Diagrams, Logical Data Dictionary, and Requirement Traceability Matrix) directly in your browser.

---

## Planned Empirical Evaluation

Following implementation, detection accuracy will be benchmarked on a labeled ground-truth corpus of **40–60 multi-language source files** using **Precision**, **Recall**, and **F1-Score**, including a direct Python-side baseline comparison against **Bandit**.
