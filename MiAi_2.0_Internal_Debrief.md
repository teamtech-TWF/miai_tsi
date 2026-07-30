# Internal Debrief
## MiAi 2.0 — TSI Trusted Business Advisory Platform

## 1. Project Context

TSI ต้องการพัฒนา AI Business Advisor Bot บน LINE Official Account สำหรับผู้ประกอบการ SME โดยใช้ฐานความรู้ “TSI Way” เท่านั้น ระบบต้องทำงานตลอด 24 ชั่วโมง ใช้ Claude Haiku 4.5 ร่วมกับ RAG และต้องมี Monitoring, Traceability, Security และ Cost Control อย่างชัดเจน

โครงการนี้เป็นงาน Competitive Pitching และต้องจัดทำ Proposal ร่วมกับ Technical Partner ดังนั้นเป้าหมายในระยะนี้คือ:

- ตีความ TOR ให้ครบและไม่เสนอเกิน Scope
- สร้าง Solution ที่แตกต่างจากคู่แข่ง
- แบ่งบทบาท TWF และ Partner ให้ชัดเจน
- เตรียม Proposal ที่ตอบโจทย์ทั้ง Business, UX, Technology และ Operations

ระบบเดิมของ TSI คือ MiAi บนเว็บไซต์ `https://www.tsi-chat.com/` จึงควรมองโครงการนี้เป็นการยกระดับจาก Web Chat ไปสู่ LINE-based advisory platform มากกว่าการสร้างแนวคิดใหม่ทั้งหมด

---

## 2. Core Interpretation

TOR ปัจจุบันต้องการระบบในระดับ:

> **Closed-domain AI Knowledge Advisor บน LINE OA**

ระบบต้องสามารถ:

1. รับข้อความจาก LINE OA
2. ส่งข้อความผ่าน Secure Webhook
3. เชื่อมต่อ Claude API by Anthropic รุ่น Haiku 4.5
4. ค้นข้อมูลจาก TSI Knowledge Base ผ่าน RAG
5. ตอบจากเอกสาร TSI เท่านั้น
6. ใช้ Fallback เมื่อไม่มีข้อมูล
7. แนบ Disclaimer ทุกคำตอบ
8. ตรวจสอบ Model และ Knowledge Base Version ย้อนหลังได้
9. มี Monitoring, Alerting และ Dashboard
10. ควบคุมต้นทุนด้วย Rate Limiting

TOR ยังไม่ได้ครอบคลุม Personal Assistant เต็มรูปแบบ เช่น:

- Member Profile
- Business Profile
- Personalized Recommendation
- Conversation Memory ระยะยาว
- CRM Integration
- Human Advisor Workspace
- Appointment และ Follow-up
- LINE MINI App
- Campaign Automation

ดังนั้นสิ่งเหล่านี้ควรอยู่ใน Future Roadmap หรือ Optional Scope ไม่ควรรวมใน Base Proposal โดยอัตโนมัติ

---

## 3. Proposed Positioning

# MiAi 2.0
## TSI Trusted Business Advisory Platform

แนวคิดหลัก:

> เปลี่ยนองค์ความรู้ TSI Way ให้เป็นบริการให้คำปรึกษาธุรกิจที่เข้าถึงง่าย เชื่อถือได้ ตรวจสอบย้อนหลังได้ และพร้อมขยายต่อในอนาคต

ระบบประกอบด้วย 4 Layers:

### 3.1 LINE Experience Layer

ดูแลการเข้าถึงและประสบการณ์สนทนาของผู้ประกอบการ

องค์ประกอบหลัก:

- Welcome Journey
- การแนะนำขอบเขตคำปรึกษา
- ตัวอย่างคำถาม
- Rich Menu / Quick Reply
- Business Category Selection
- Conversation Flow
- Fallback Experience
- Rate-limit Notification
- Feedback ต่อคำตอบ

หลักคิดสำคัญ:

> LINE ไม่ควรถูกมองเป็นเพียงช่องทางรับ–ส่งข้อความ แต่เป็น Entry Point ของ TSI Business Ecosystem

### 3.2 AI Advisory Layer

ดูแลการประมวลผลและการสร้างคำตอบจากข้อมูลที่ได้รับอนุมัติ

องค์ประกอบหลัก:

- Claude API by Anthropic
- Claude Haiku 4.5
- Controlled System Prompt
- TSI-only Knowledge Retrieval
- Vector Database
- Retrieval Threshold
- Fallback Response
- Disclaimer
- Model Version Tracking
- Prompt Version Tracking

ข้อเสนอควรแสดงให้ชัดว่า “ตอบจากเอกสารเท่านั้น” ไม่ได้ควบคุมด้วย Prompt เพียงอย่างเดียว แต่มีหลายชั้นควบคุม ได้แก่:

- จำกัดแหล่งเอกสารที่ค้นได้
- ตรวจสอบ Retrieval Score
- ไม่ตอบเมื่อไม่มี Evidence
- เชื่อมคำตอบกับ Source ที่ค้นพบ
- บันทึก Document และ Chunk ที่ถูกใช้
- มีชุดคำถามทดสอบก่อนขึ้นระบบจริง

### 3.3 Knowledge Governance Layer

ดูแลคุณภาพ ความถูกต้อง และวงจรชีวิตขององค์ความรู้

Suggested Knowledge Lifecycle:

> Upload → Validate → Categorize → Approve → Index → Publish → Monitor → Update / Archive

แนวทาง Scope:

- Base Scope: Manual Knowledge Setup และ Version Tracking
- Optional Scope: Admin Portal และ Approval Workflow
- TSI ต้องแต่งตั้ง Knowledge Owner
- คุณภาพคำตอบขึ้นกับคุณภาพและความครบถ้วนของเอกสาร

### 3.4 Trust & Operations Layer

ดูแลการทำงานของระบบให้มีความปลอดภัย ตรวจสอบได้ และควบคุมต้นทุนได้

องค์ประกอบหลัก:

- Monitoring
- Security
- Cost Control
- Auditability
- Alerting
- Operational Dashboard

---

## 4. Dashboard & Monitoring Scope

Dashboard ควรครอบคลุมมากกว่า Technical Status และช่วยให้ TSI มองเห็นทั้ง Performance, AI Quality, Cost และ Knowledge Gap

### 4.1 System Health

- Webhook Status
- Claude API Status
- Error Rate
- Response Time
- Successful / Failed Requests
- Queue หรือ Processing Status
- Automated Alert

### 4.2 AI Usage

- จำนวนคำถาม
- จำนวนคำตอบสำเร็จ
- Fallback Rate
- Frequently Asked Topics
- Unanswered Questions
- User Feedback

### 4.3 Cost Control

- Token Usage
- Daily / Monthly API Consumption
- Cost per Conversation
- Budget Threshold
- Rate-limit Events

### 4.4 Traceability

- Model Version
- Prompt Version
- Knowledge Base Version
- Document Reference
- Chunk Reference
- Timestamp
- Request ID

### 4.5 Knowledge Intelligence

- เอกสารที่ถูกเรียกใช้บ่อย
- Topic ที่ผู้ประกอบการถามมากที่สุด
- คำถามที่ฐานความรู้ยังตอบไม่ได้
- Knowledge Gap ที่ TSI ควรพัฒนาเพิ่ม

---

## 5. Existing MiAi Context

ระบบเดิมบน `tsi-chat.com` มี Asset สำคัญที่ไม่ควรถูกมองข้าม:

- MiAi Brand
- TSI Way Knowledge
- Existing Chat Experience
- Business Category Selection
- Existing User Behaviour
- Existing Questions และ Feedback

อย่างไรก็ตาม Proposal ไม่ควรรับประกันว่าจะ Reuse ระบบเดิมได้ จนกว่าจะมีการ Audit เรื่อง:

- Source Code
- Repository
- Hosting
- Backend Architecture
- AI Provider และ Model เดิม
- Knowledge Base เดิม
- Vector Database
- Chat History และ Analytics
- Data Ownership

แนวทางที่เหมาะสมคือ:

> Audit Existing MiAi → Identify Reusable Assets → Build New AI Core → Launch LINE OA → Decide Web Coexistence or Migration

---

## 6. Differentiators for Competitive Pitch

คู่แข่งส่วนใหญ่น่าจะเสนอ Architecture พื้นฐานในรูปแบบ:

> LINE OA → Webhook → Claude → Vector Database → Response

หาก Proposal ของเราเสนอเพียงเท่านี้ งานจะถูกเปรียบเทียบด้านราคาเป็นหลัก

จุดแตกต่างที่ควรใช้ใน Pitch:

### 6.1 Existing MiAi Continuity

เราเข้าใจว่า TSI มีระบบเดิมและมองโครงการนี้เป็น Evolution ไม่ใช่ Greenfield Chatbot

### 6.2 Controlled AI, Not Generic Chatbot

- ตอบจาก Approved Knowledge เท่านั้น
- มี Evidence
- ปฏิเสธเมื่อไม่มีข้อมูล
- ตรวจสอบย้อนหลังได้
- มี Human Oversight

### 6.3 Knowledge Governance

นำเสนอการบริหาร Knowledge เป็นระบบ ไม่ใช่เพียง Upload PDF เข้า Vector Database

### 6.4 Knowledge Gap Intelligence

ระบบช่วยให้ TSI เห็นว่าผู้ประกอบการถามเรื่องใด และเนื้อหาส่วนใดยังขาด

### 6.5 Future-ready Architecture

Architecture รองรับการต่อยอดไปสู่:

- Human Handoff
- Business Profile
- Personalized Recommendation
- CRM
- LINE MINI App
- Follow-up Automation

ทั้งหมดควรถูกวางเป็น Roadmap ไม่ใช่ Base Scope

---

## 7. Proposal Scope Structure

### 7.1 Included in Base Scope

- LINE OA Integration
- Secure Webhook
- Claude Haiku 4.5
- RAG
- Vector Database
- Controlled Answer
- Fallback
- Disclaimer
- Monitoring
- Traceability
- Security
- Rate Limiting
- Dashboard / Log
- API Documentation
- Architecture Diagram

### 7.2 Assumptions

- รองรับภาษาไทยเป็นหลัก
- รองรับ Text Message เป็นหลัก
- TSI เตรียมและอนุมัติ Knowledge Documents
- ใช้ LINE OA ที่ TSI จัดเตรียม
- จำนวนเอกสารอยู่ภายใต้ขอบเขตที่กำหนด
- ไม่มี Data Migration จากระบบเดิมใน Base Scope
- Hosting และ SLA Finalize ใน Discovery Phase

### 7.3 Optional Scope

- Human Handoff
- Admin Knowledge Portal
- Approval Workflow
- LINE MINI App
- CRM Integration
- Personalized Profile
- Advanced Analytics
- Web Chat Migration
- Additional Languages

---

## 8. Recommended Implementation Phases

### Phase 0 — Discovery & Existing System Audit

**Estimated duration:** 2 weeks  
**Estimated manday:** 4 UX/UI MD + 10 Other MD  
**Estimated one-time cost:** 117,000 THB

- Audit ระบบ MiAi เดิม
- Review Knowledge Base
- Confirm LINE OA Readiness
- Define User Journey
- Define Evaluation Set
- Confirm Architecture
- Confirm Security และ PDPA Assumptions
- Finalize Technical Scope

### Phase 1 — AI Q&A + LINE Foundation

**Applies to:** Option 1 and Option 2

- Option 1: Zone 1 Core AI Q&A with Claude Haiku 4.5, RAG, basic source reference, fallback
- Option 1: Zone 3 LINE OA essentials, messaging, quick reply, basic rich menu
- Option 2: Zone 1 Trusted AI Q&A with RAG, monitoring, traceability, rate limit, cost control
- Option 2: Zone 3 LINE OA experience with rich menu, quick reply, basic notification, handover preparation
- Secure Webhook
- Controlled Answer
- Disclaimer

### Phase 2 — Go-live or Starter Assistant

**Applies differently by selected option**

- Option 1: Functional test, AI quality check, UAT support, deployment
- Option 1: Basic runbook, training, and launch handover
- Option 2: Zone 2 starter business profile
- Option 2: Guided prompts and simple personalized recommendation
- Option 2: Production readiness, quality review, runbook, training, and handover

### Budget Options by Zone

#### Option 1 — Lean Required Launch

| Zone | Scope Position | Estimated Cost |
|---|---|---:|
| Zone 1 | Core AI Q&A, Claude + RAG, basic source reference, fallback | 650,000 THB |
| Zone 2 | Personal Business Assistant | Not included |
| Zone 3 | LINE OA messaging, quick reply, basic rich menu | 200,000 THB |
| **Total Option 1** |  | **850,000 THB** |

#### Option 2 — Recommended Production Launch

| Zone | Scope Position | Estimated Cost |
|---|---|---:|
| Zone 1 | Trusted AI Q&A, RAG, monitoring, traceability, rate limit, cost control | 700,000 THB |
| Zone 2 | Starter Personal Business Assistant: business profile, guided prompts, simple personalized recommendation | 250,000 THB |
| Zone 3 | LINE OA experience, rich menu, quick reply, basic notification, handover | 250,000 THB |
| **Total Option 2** |  | **1,200,000 THB** |

Advanced personalization, LINE MINI App, CRM, booking, campaign automation, community, and advanced BI remain future roadmap and should not be shown as an immediate purchase total unless TSI requests those modules.

### Use Case Demo by Option

| Option | Included Zones | Demo Sequence | What This Proves |
|---|---|---|---|
| Option 1 — Lean Required Launch | Zone 1 Core AI Q&A + Zone 3 LINE OA Essentials | 1. Ask MiAi → 5. Connect to TSI | Trusted Q&A, source reference, fallback, and LINE next action |
| Option 2 — Recommended Production Launch | Zone 1 Trusted AI + Zone 2 Starter Assistant + Zone 3 LINE OA Experience | 1. Ask MiAi → 2. Diagnose My Business → 3. Start Improvement Mission | Starter personalization through business profile, guided prompts, and simple recommendation |
| Future Roadmap | Advanced Zone 2 + expanded Zone 3 | 4. Learn from Similar Business; advanced Connect to TSI flows | Case matching, MINI App, CRM, booking, campaign, community, and BI stay outside immediate launch |

### Phase Cost Reference

| Phase | Scope Position | Reference Cost |
|---|---|---:|
| Phase 0 | Discovery, audit, architecture, evaluation design | 117,000 THB |
| Phase 1 | LINE OA MVP, Claude Haiku 4.5, RAG, controls, basic dashboard | Included in commercial package |
| Phase 2 | Production hardening, quality analytics, testing, runbook, handover | Included in commercial package |
| **Recommended Production Launch** |  | **1,200,000 THB** |

### Recurring Cost Estimate

Recurring cost should be separated from development cost because real usage depends on active users, message volume, document volume, monitoring retention, and SLA expectation after go-live.

To reduce monthly cost, the proposal should present a minimum-to-scale operating model: open-source/self-hosted components by default, paid API only when higher answer quality or fallback is required, and support/SLA separated from the baseline.

| Cost Model | Components | Estimated Monthly Cost |
|---|---|---:|
| Minimum open-source baseline | Small cloud VM, open-source model / embeddings where feasible, Postgres + pgvector, open-source monitoring | 15,000–35,000 THB |
| Hybrid paid-source fallback | Claude API for selected answers, managed backup / logs, higher reliability cloud resources | 35,000–75,000 THB |
| LINE Messaging API | Keep cost low by prioritizing reply messages; push / broadcast depends on TSI package and volume | Separate |
| Maintenance / SLA Retainer | Optional monthly support, knowledge update service, incident response | Separate or on-demand |
| **Recommended Minimum Launch Assumption** | Open-source baseline with limited paid-source fallback | **20,000–45,000 THB / month** |

Scale triggers:

- Move from minimum baseline to hybrid paid-source when answer quality, response consistency, or sensitive advisory topics require stronger model quality.
- Increase cloud and monitoring budget when active users, document volume, log retention, or uptime requirements increase.
- Add monthly retainer only when TSI requires guaranteed response time, regular knowledge updates, or incident handling.

Third-party usage cost should not be bundled into development cost until the expected launch volume is confirmed. Maintenance should be offered as either on-demand support or a separate monthly retainer, not hidden inside the base recurring estimate.

### Phase 3 — Future Expansion

Phase 3 should remain optional roadmap scope and should not be included in the base project investment unless TSI explicitly selects these modules.

- Human-assisted Advisory
- Business Profile
- Personalized Assistance
- CRM Integration
- LINE MINI App
- Appointment และ Follow-up
- Community และ Campaign Integration

---

## 9. Working Model with Partner

| Workstream | Suggested Owner |
|---|---|
| Business proposition และ Storytelling | TWF |
| Client Context และ Existing MiAi Understanding | TWF |
| UX Journey / LINE Experience | TWF |
| Solution Architecture | Technical Partner + TWF |
| Claude / RAG Implementation | Technical Partner |
| Vector Database / Knowledge Ingestion | Technical Partner |
| Cloud และ DevOps | Technical Partner |
| Monitoring และ Dashboard | Technical Partner |
| Knowledge Preparation | TSI + TWF / Partner |
| Security และ PDPA Assumptions | Joint |
| Project Management | TWF |
| Proposal Consolidation | TWF |
| Technical Costing | Technical Partner |
| Final Commercial Model | TWF + Partner |

### Partner Deliverables Required for Proposal

1. Recommended Architecture
2. Proposed Technology Stack
3. Claude API Integration Approach
4. Vector Database Recommendation
5. Monitoring Stack
6. Security Approach
7. Deployment Model
8. Development Timeline
9. Team Composition
10. Cost Breakdown
11. Monthly Infrastructure Estimate
12. Maintenance และ SLA Options
13. Assumptions และ Exclusions
14. Relevant Case Study / Credentials

---

## 10. Key Risks

### Risk 1: เสนอใหญ่เกิน TOR

Personal Assistant, MINI App และ CRM อาจทำให้ราคาสูงกว่าคู่แข่ง

**Mitigation:** นำเสนอเป็น Vision และ Optional Roadmap

### Risk 2: Proposal เป็น Technical เกินไป

Architecture อย่างเดียวไม่สร้างเหตุผลให้เลือกเรา

**Mitigation:** เชื่อม Technology กับ Accessibility, Trust และ Knowledge Governance

### Risk 3: สมมติว่า Reuse ระบบเดิมได้

อาจเกิด Scope และ Timeline ผิดพลาด

**Mitigation:** Base Proposal บน New AI Core และยืนยัน Reuse หลัง Audit

### Risk 4: รับประกัน Accuracy โดยไม่มีเกณฑ์

AI Quality ขึ้นกับเอกสารและชุดคำถามทดสอบ

**Mitigation:** ใช้ Evaluation Framework และ Acceptance Test

### Risk 5: ตีความ 24/7 เป็น Human Support 24/7

อาจเกิดภาระ Operational ที่ไม่ได้รวมในราคา

**Mitigation:** แยก System Availability, Automated Monitoring และ Human Support SLA

---

## 11. Presentation Direction — 4 Slides / 3–5 Minutes

### Slide 1 — MiAi 2.0 Vision

**Key Message:**

> From AI Chatbot to a Trusted Business Advisory Platform on LINE

นำเสนอ 4 Layers:

- LINE Experience
- AI Advisory
- Knowledge Governance
- Trust & Operations

### Slide 2 — LINE Experience Layer

แสดง Journey:

> Welcome → Business Context → Ask → Trusted Answer → Feedback / Fallback

Key Message:

> LINE คือ Entry Point ของ TSI Business Ecosystem ไม่ใช่เพียง Chat Channel

### Slide 3 — AI Advisory & Knowledge Governance

แสดง Multi-layer Answer Control และ Knowledge Lifecycle

Key Message:

> คำตอบที่เชื่อถือได้ต้องควบคุมทั้ง Source, Retrieval, Evidence, Version และ Evaluation

### Slide 4 — Trust, Monitoring & Business Intelligence

แสดง Dashboard 4 กลุ่ม:

- System Health
- AI Usage
- Cost Control
- Traceability / Knowledge Insight

Closing Message:

> MiAi 2.0 เปลี่ยน TSI Way จากชุดเอกสารให้กลายเป็นบริการให้คำปรึกษาที่เข้าถึงได้ เชื่อถือได้ และพัฒนาให้ดีขึ้นจากทุกคำถามของผู้ประกอบการ

---

## 12. Immediate Internal Actions

### TWF

- Finalize Proposal Storyline
- สรุป Current MiAi → MiAi 2.0
- ออกแบบ User Journey
- แบ่ง Base / Optional / Roadmap
- เตรียม Assumptions และ Exclusions
- เตรียม Credentials และ Case Study
- Consolidate Final Proposal

### Technical Partner

- เสนอ Architecture
- ยืนยัน LINE, Claude และ RAG Capability
- เสนอ Technology Stack
- ประเมิน Team และ Timeline
- ประเมิน Development Cost
- ประเมิน Monthly Run Cost
- เสนอ Monitoring และ Security Approach
- ระบุ Dependencies และ Limitations

### Joint

- Lock Solution Direction
- Lock Scope Boundary
- Lock Partner Roles
- Lock Commercial Model
- Review TOR Compliance
- Prepare Compliance Matrix
- Rehearse 3–5 Minute Presentation

---

## Final Internal Conclusion

งานนี้ไม่ควรถูกนำเสนอว่าเป็นเพียงการสร้าง Chatbot บน LINE แต่ควรถูก Position เป็น:

> **การยกระดับ MiAi จาก Web Chat ไปสู่ TSI Trusted Business Advisory Platform**

แนวทางที่เหมาะสมคือ:

- ใช้ TOR เป็น Base Scope
- ใช้ MiAi เดิมเป็น Context
- ใช้ Discovery / Audit ปิดข้อมูลที่ยังไม่ชัด
- ให้ Technical Partner รับผิดชอบ AI Core, Infrastructure และ Operations
- ให้ TWF รับผิดชอบ Storytelling, UX, Proposal และ Client Alignment
- ใช้ Knowledge Governance และ Future-ready Architecture เป็นจุดสร้างความแตกต่าง
- ไม่รวม Personal Assistant, CRM หรือ MINI App ใน Base Scope เว้นแต่ถูกเลือกเป็น Option

หัวใจของ Proposal คือการทำให้ TSI เชื่อว่าเราสามารถดูแลได้ครบทั้ง:

> **Experience + AI + Knowledge + Operations**
