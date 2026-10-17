# Graph Report - Dr. Hafiz Anwaar Ahmad  (2026-10-17)

## Corpus Check
- 25 files · ~170,655 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 29 nodes · 30 edges · 5 communities
- Extraction: 93% EXTRACTED · 7% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.95)
- Token cost: 1,250 input · 850 output

## Community Hubs (Navigation)
- Website Presentation & Layout
- Cardiologist Identity & Credentials
- WEB-100 Quality Framework
- Clinical Services & Diagnostic Equipment

## God Nodes (most connected - your core abstractions)
1. `Doctor Portfolio Homepage (index.html)` - 14 edges
2. `Dr. Hafiz Anwaar Ahmad Sangra (Consultant Cardiologist)` - 7 edges
3. `WEB-100 Protocol v1.1 Standard` - 5 edges
4. `Clinical Cardiac Services & Diagnostics` - 3 edges
5. `Institutional Appointments (DHQ Faisalabad, Ex-FIC)` - 2 edges
6. `Rubina Memorial Hospital Clinic (Batala Colony)` - 2 edges
7. `Oladoc Verified Profile #566307 & 5.0 Star Rating` - 2 edges
8. `Quality Audit & Verification Report` - 2 edges
9. `Consultant Cardiologist Executive Portrait` - 2 edges
10. `Cardiology Credentials (MBBS, Dip. Card UHS)` - 1 edges

## Surprising Connections (you probably didn't know these)
- `Doctor Portfolio Homepage (index.html)` --references--> `Consultant Cardiologist Executive Portrait`  [EXTRACTED]
  index.html → images/dr_sangra_executive_headshot_portrait.webp
- `Dr. Hafiz Anwaar Ahmad Sangra (Consultant Cardiologist)` --references--> `Consultant Cardiologist Executive Portrait`  [EXTRACTED]
  DR_HAFIZ_ANWAAR_AHMAD_SANGRA_DATA.md → images/dr_sangra_executive_headshot_portrait.webp
- `Clinical Cardiac Services & Diagnostics` --references--> `Consultation Desk & Echocardiography Machine`  [INFERRED]
  DR_HAFIZ_ANWAAR_AHMAD_SANGRA_DATA.md → images/dr_sangra_consultation_desk_with_echocardiography_machine.webp
- `Doctor Portfolio Homepage (index.html)` --references--> `Brand Favicon & Stethoscope Logo`  [EXTRACTED]
  index.html → images/favicon.svg
- `Institutional Appointments (DHQ Faisalabad, Ex-FIC)` --references--> `DHQ Hospital Clinical Signboard`  [EXTRACTED]
  DR_HAFIZ_ANWAAR_AHMAD_SANGRA_DATA.md → images/dhq_hospital_chiniot_exterior_signboard.webp

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Doctor Professional Clinical Identity** — dr_hafiz_anwaar_ahmad_sangra_data_doctor_profile, dr_hafiz_anwaar_ahmad_sangra_data_qualifications, dr_hafiz_anwaar_ahmad_sangra_data_institutional_roles, dr_hafiz_anwaar_ahmad_sangra_data_clinical_services [EXTRACTED 1.00]
- **Production Medical Website Core Components** — index_html, script, 404_html, robots_txt [EXTRACTED 1.00]
- **WEB-100 Continuous Compliance Framework** — web_100_protocol, quality_report, quality_changelog, quality_questions [EXTRACTED 1.00]

## Communities (5 total, 0 thin omitted)

### Community 0 - "Website Presentation & Layout"
Cohesion: 0.20
Nodes (10): Custom 404 Emergency Error Page, Brand Favicon & Stethoscope Logo, Doctor Portfolio Homepage (index.html), Direct Call & WhatsApp Appointment CTA, Hospital & Clinic Schedule Timetable, Hero & Doctor Trust Architecture, Schema.org MedicalBusiness JSON-LD, Interactive Cardiac Services Grid (+2 more)

### Community 1 - "Cardiologist Identity & Credentials"
Cohesion: 0.22
Nodes (9): Dr. Hafiz Anwaar Ahmad Sangra (Consultant Cardiologist), Institutional Appointments (DHQ Faisalabad, Ex-FIC), Oladoc Verified Profile #566307 & 5.0 Star Rating, Cardiology Credentials (MBBS, Dip. Card UHS), Rubina Memorial Hospital Clinic (Batala Colony), DHQ Hospital Clinical Signboard, Rubina Memorial Hospital Clinic Entrance, Consultant Cardiologist Executive Portrait (+1 more)

### Community 2 - "WEB-100 Quality Framework"
Cohesion: 0.40
Nodes (5): Engineering & Architectural Decisions, Quality Audit & Verification Report, WEB-100 Protocol v1.1 Standard, Core Web Vitals & Lighthouse 100/100 Benchmark, Zero-Vulnerability CSP & Security Headers

### Community 3 - "Clinical Services & Diagnostic Equipment"
Cohesion: 0.67
Nodes (3): Clinical Cardiac Services & Diagnostics, Clinical Services Standee Display, Consultation Desk & Echocardiography Machine

## Knowledge Gaps
- **16 isolated node(s):** `Cardiology Credentials (MBBS, Dip. Card UHS)`, `Hero & Doctor Trust Architecture`, `Interactive Cardiac Services Grid`, `Hospital & Clinic Schedule Timetable`, `Direct Call & WhatsApp Appointment CTA` (+11 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 19 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Doctor Portfolio Homepage (index.html)` connect `Website Presentation & Layout` to `Cardiologist Identity & Credentials`, `WEB-100 Quality Framework`, `Client-Side Interaction Logic`?**
  _High betweenness centrality (0.796) - this node is a cross-community bridge._
- **Why does `Dr. Hafiz Anwaar Ahmad Sangra (Consultant Cardiologist)` connect `Cardiologist Identity & Credentials` to `Website Presentation & Layout`, `Clinical Services & Diagnostic Equipment`?**
  _High betweenness centrality (0.579) - this node is a cross-community bridge._
- **Why does `WEB-100 Protocol v1.1 Standard` connect `WEB-100 Quality Framework` to `Website Presentation & Layout`?**
  _High betweenness centrality (0.206) - this node is a cross-community bridge._
- **What connects `Cardiology Credentials (MBBS, Dip. Card UHS)`, `Hero & Doctor Trust Architecture`, `Interactive Cardiac Services Grid` to the rest of the system?**
  _16 weakly-connected nodes found - possible documentation gaps or missing edges._