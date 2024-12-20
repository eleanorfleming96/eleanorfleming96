---
layout: page
title: Forms Module for Procurement Workflows and Contract Renewals
---

I led the development of a forms module that helps procurement teams create and manage workflows like performance reviews and contract renewals.  

---

## Overview  

The project focused on building an intuitive and flexible forms system. This included creating a customizable data model, supporting multiple submission types, and implementing conditional logic to streamline form submissions.  

---

## Key Features  

### 1. Flexible Data Model  

- **Customizable Layouts**:  
  Designed a data model that allows users to configure layouts, sections, and field types to meet their needs.  

- **Single & Multi-Submission Support**:  
  Defined requirements to support both single and multi-submission workflows, making the platform adaptable for various use cases.  
  - *Example*: A multi-submission form might be used for a performance review workflow, where procurement teams collect feedback from each stakeholder. A single-submission form might be used for a renewal form, where stakeholders collaborate on a single submission.  

- **Data Integration**:  
  Enabled forms to pull and update data from existing entities (e.g., suppliers, contracts).  
  - *Example*: A renewal form can display up-to-date contract details by pulling data from a deal record. Similarly, a form field can be configured such that submitting the form updates data on a deal record, improving data quality and reducing manual entry.  

---

### 2. Intelligent Automation  

- **Rules Engine**:  
  Built logic to automate behaviors like conditional field visibility, calculations, and validations.  
  - *Example*: In a renewal form, if a supplier is flagged for termination, irrelevant follow-up questions are hidden.  

- **User-Friendly Rule Builder**:  
  Designed an interface for creating and editing rules with clear options like AND/OR conditions.  

- **Competitive Analysis**:  
  Researched tools like Jotform and Typeform to incorporate industry-leading practices for conditional logic.  
