# Oracle-EPM-Groovy
# Oracle EPM: Automated Rolling Forecast Orchestration
### Sequential Data Integration Pipeline Control via Groovy

## 📌 Overview
In complex Oracle EPM environments, running multiple Data Integration (DI) tasks simultaneously can lead to data contention, performance bottlenecks, or race conditions. This repository contains a production-ready **Groovy Business Rule** designed to act as a "Traffic Controller".

The script orchestrates an 8-period rolling forecast by triggering EPM Data Integration Pipelines sequentially. It utilizes the EPM REST API and Named Connections to ensure each period is fully processed and validated before the next begins.

## 🚀 Key Features
* **Sequential Execution:** Logic-driven loop that prevents overlapping jobs.
* **Asynchronous Monitoring:** Active polling of the EPM Job Console to track real-time status.
* **Secure Authentication:** Leverages EPM **Named Connections** to eliminate hardcoded credentials.
* **Robust Error Handling:** Uses `throwVetoException` to stop execution and alert users if a specific period fails.
* **REST API Integration:** Direct interaction with the `pipeline` job type for advanced data movement.

## 🛠️ Prerequisites
1.  **Oracle EPM Cloud Instance:** Planning or Freeform.
2.  **Named Connection:** A connection named `dm` (or as defined in your script) configured in **Tools > Connections**.
3.  **Integration Pipeline:** A pre-configured Pipeline named `Initiate Rolling Forecast`.

## 📂 Repository Structure
* `src/`: Contains the `.groovy` script for the Business Rule.
* `docs/`: Detailed technical documentation and architectural overview.
* `examples/`: Sample JSON payloads for REST API exploration.

## 👨‍💻 Author
**Shubham Panchal** *Oracle Certified EPM Techno-Functional Consultant*

---
