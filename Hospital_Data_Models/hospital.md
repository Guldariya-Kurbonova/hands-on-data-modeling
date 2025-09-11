# Hospital / Clinic Information System

<img width="2740" height="708" alt="Logical_Data_Model_Doctor - Page 1 (1)" src="https://github.com/user-attachments/assets/4c6474fa-2ce5-46a2-a9f2-185306b9cc1b" />


## Business Context
We are building an information system for a **hospital** to manage:
- Patients and their contact information (including addresses).
- Patient visits for consultations.
- Doctors and the visits they conduct.
- Symptoms reported during each visit.
- Patients who have left the hospital system (**dropped patients**).

---

## Walkthrough of Relationships & Business Rules

### 1. **Address – Patient**
- **Business Rule:** A patient must have an address, but multiple patients can share the same address (e.g., family, roommates, group homes).  
- **Relationship:**  
  - One **Address** → Many **Patients**  
  - Each **Patient** → One **Address**  


---

### 2. **Patient – Dropped_Patient**
- **Business Rule:** Some patients stop visiting the hospital (dropped). We need to track them for reporting, compliance, or follow-up.  
- **Relationship:**  
- A **Patient** may or may not have a drop record.  
- Each **Dropped_Patient** → Exactly one **Patient**.  



---

### 3. **Patient – Patient_Visit**
- **Business Rule:** A patient may have multiple visits over time. Each visit is tied to exactly one patient.  
- **Relationship:**  
- One **Patient** → Many **Patient_Visits**  
- Each **Patient_Visit** → One **Patient**  



---

### 4. **Doctor – Patient_Visit**
- **Business Rule:** Each visit is conducted by one doctor. A doctor may attend many visits over time.  
- **Relationship:**  
- One **Doctor** → Many **Patient_Visits**  
- Each **Patient_Visit** → One **Doctor**   




---

### 5. **Patient_Visit – Symptom**
- **Business Rule:** During a visit, a patient may report multiple symptoms. Each symptom record belongs to that specific visit.  
- **Relationship:**  
- One **Patient_Visit** → Many **Symptoms**  
- Each **Symptom** → One **Patient_Visit**    




---

## Analyst’s Narrative

- Each **Patient** must provide an **Address**, but multiple patients may share one address (families, group homes).  
- Patients may continue using hospital services indefinitely. If a patient stops, we record a **Dropped_Patient** entry. Since a patient can only leave once, this is a **one-to-one optional** relationship.  
- Patients may have **multiple visits** over time. Each **Patient_Visit** always belongs to exactly one patient.  
- Each visit is attended by **one Doctor**, but doctors may handle many visits throughout their careers.  
- During a visit, patients may report **multiple Symptoms**, which are tied to that visit to reflect what they experienced at that specific time.  

---

## Suggested Entity Overview
- **Address**  
- **Patient**  
- **Dropped_Patient**  
- **Patient_Visit**  
- **Doctor**  
- **Symptom**

---

*This document outlines the business context and rules for the Hospital/Clinic Information System to support development and database design.*













