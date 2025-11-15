# Master Thesis – Transparency in Algorithmic Decision-Making

This repository contains the practical component of the master’s thesis:

> **_Transparency in Business Processes: Comparing White-Box and Black-Box Algorithmic Decision-Making_**

Authored by **Niels Bodendorfer** under the supervision of  
[**Prof. Dr. Michael zur Muehlen**](https://www.stevens.edu/profile/mmuehlen),  
**Stevens Institute of Technology**

---

## Source Structure

The following overview illustrates the complete folder structure used in this project, including all components relevant to the implementation and datasets.
```
src/
│
├── reference-process/
│   ├── appearances/                # Visualization of Reference Process (BPMN 2.0)
│   │
│   ├── dataset/
│   │   ├── evaluation/             # Data from MySQL database
│   │   │   ├── phase1.xlsx
│   │   │   ├── phase2.xlsx
│   │   │   ├── phase3.xlsx
│   │   │   ├── phase4.xlsx
│   │   │   ├── candidateInfos_all.xlsx
│   │   │   ├── table_candidates.csv
│   │   │   ├── table_job-position.csv
│   │   │   └── table_performance-report.csv
│   │
│   ├── reference_process/          # Camunda 8 workflow components
│   │   ├── BPMN model(s)
│   │   ├── task forms
│   │   ├── workers / handlers
│   │   └── configuration files
│
└── website/
    ├── appearances/                # Website icons and visual assets
    │   ├── AI.ico
    │   ├── Automization.ico
    │   └── Workflow.ico
    │
    ├── screenshots/                # Documentation of the participant UI flow
    │   ├── Website-Landingpage-1.png
    │   ├── Website-Landingpage-2.png
    │   ├── Website-Landingpage-3.png
    │
    ├── index.html                  # Static landing page for participants
    └── keepalive.sh
```

## Website Component

### Study Context

The static website serves as the **onboarding interface** for study participants.  
Its primary functions are to:

- Introduce the study and collect informed consent.
- Trigger the **Camunda-based evaluation workflow** by forwarding participant information.
- Provide participants with **login credentials** after form submission.
- Redirect participants to the **Camunda Tasklist**, where they complete their assigned tasks.

This implementation provides a transparent, simple, and reproducible mechanism to guide participants into the experimental workflow.

---

### Tech Stack

- **HTML / CSS** (vanilla)
- **JavaScript** (basic DOM handling, form submission logic, popup trigger)
- Fully static implementation — **no backend**, no frameworks required

---

### Notes for Use

- The site uses a **popup window** to initiate the workflow; participants must allow popups in their browser.
- **Credentials** are displayed after the form is submitted and the popup closes.
- This design **replaces earlier, more complex implementations** (e.g., the `develop` branch and `feature/web-process-start`) and represents the **final, stable version** used in the study.

---
### Access to the Study Portal

The participant-facing version of the website, used during data collection, is available at:

**https://human-ai-study.onrender.com/**

This link corresponds to the deployed static site that introduced the study, collected informed consent, and forwarded participants to the Camunda Tasklist for completing their evaluation tasks.

---

## Research Context

This project investigates how **transparency** and **explainability** in algorithmic workflows affect human **trust** and **decision quality**.  
The study specifically explores the **acceptance of AI-generated decisions**, asking whether they are trusted to the same extent as human-generated ones.

---

## Reference Model

The experiment is based on a **BPMN reference process model**, implemented in **Camunda 8** and extended across different feature branches.

![Reference Process](/appearances/HR_Evaluation_Experiment_MasterThesis_final.svg)
_Figure: Experimental reference process (BPMN model)_

The reference model defines the workflow logic through which participants are guided in the study.

---

## Study Design

- **Procedure:** Participants are presented (via an online portal) with **fictitious employee profiles** including performance ratings and justifications.
- **Conditions:** Some profiles are described as **human-generated**, others as **AI-generated**.
- **Tasks:**
  1. Indicate agreement with the given rating and justification (0–100 scale).
  2. Optionally adjust the rating and provide their own evaluation.
- **Population:** Adults (general population, anonymous participation).
- **Consent & Privacy:** Informed consent is displayed at the beginning; participants can opt out at any time.
- **Privacy Protection:** Participants log in with **proxy accounts**; no personal or identifying data is collected, and ratings cannot be traced back to individuals.


---

## Academic Contribution

This thesis contributes to research on:

- The role of **transparency** in automated decision-making,
- **Human–algorithm interaction**,
- The **acceptance and trust of AI-generated vs. human-generated decisions**,
- Integration of workflow engines (**Camunda 8**) into controlled experimental studies.

---

## License

This project is intended for academic and personal research purposes only.  
Please cite appropriately when using results or code components in your own work.
