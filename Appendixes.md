# MiAi 2.0 Appendix  
## Zone 1–3 Detailed Explanation

---

# Appendix A — Zone 1: AI Q&A  
## Trusted Answers from TSI Knowledge

### บทบาทของ Zone นี้

เป็นจุดเริ่มต้นที่ผู้ประกอบการสามารถสอบถามปัญหาธุรกิจผ่าน LINE OA และได้รับคำตอบจากองค์ความรู้ที่ TSI อนุมัติเท่านั้น

MiAi 2.0 ไม่ได้ทำหน้าที่เป็น General AI แต่เป็น **Closed-domain Business Advisor** ที่ควบคุมแหล่งข้อมูล คำตอบ และการตรวจสอบย้อนหลังอย่างชัดเจน

### User Journey

> Ask Question → Understand Intent → Retrieve TSI Knowledge → Generate Answer → Show Source → Collect Feedback

### ตัวอย่างคำถาม

- ยอดขายลดลงควรเริ่มแก้จากตรงไหน
- สินค้าคงคลังมากเกินไปต้องทำอย่างไร
- จะลดของเสียในกระบวนการผลิตได้อย่างไร
- ควรตั้ง KPI สำหรับพนักงานแบบไหน

### Core Capabilities

#### 1. Natural-language Q&A

ผู้ใช้ถามด้วยภาษาธรรมชาติ โดยไม่จำเป็นต้องรู้ชื่อหลักการหรือหัวข้อในระบบ

#### 2. TSI Knowledge Retrieval

ระบบค้นข้อมูลจากเอกสาร TSI Way, Playbook, Case Study และเนื้อหาที่ได้รับอนุมัติ

#### 3. Controlled Answer

ระบบตอบเฉพาะเมื่อพบหลักฐานที่เกี่ยวข้อง และใช้ Fallback เมื่อไม่มีข้อมูลเพียงพอ

#### 4. Source Reference

แสดงชื่อเอกสารหรือแหล่งความรู้ที่ใช้ประกอบคำตอบ เพื่อเพิ่มความน่าเชื่อถือ

#### 5. Quick Reply

ช่วยต่อบทสนทนา เช่น

- ขอขั้นตอนเพิ่มเติม
- มีตัวอย่างหรือไม่
- สรุปเป็น Checklist
- ปัญหานี้เกี่ยวกับหัวข้อใด

### AI Control Framework

คำตอบที่น่าเชื่อถือไม่ควรถูกควบคุมด้วย Prompt เพียงชั้นเดียว แต่ควรมีการควบคุมหลายระดับ

> Approved Source → Retrieval Threshold → Evidence Check → Answer Policy → Disclaimer → Audit Log

ระบบควรบันทึกข้อมูลสำคัญเพื่อให้ตรวจสอบย้อนหลังได้ ได้แก่

- Model Version
- Prompt Version
- Knowledge Base Version
- Document Reference
- Chunk Reference
- Request ID
- Timestamp

### Business Value

- เปิดให้เข้าถึงองค์ความรู้ TSI ได้ตลอด 24 ชั่วโมง
- ลดภาระเจ้าหน้าที่จากคำถามที่เกิดซ้ำ
- เพิ่มการเข้าถึงเนื้อหาที่เดิมกระจายอยู่หลายเอกสาร
- สร้างมาตรฐานการให้คำปรึกษาที่สม่ำเสมอ
- ทำให้ TSI เห็นคำถามที่ฐานความรู้ยังตอบไม่ได้
- สร้างข้อมูลสำหรับพัฒนา Knowledge Base ต่อไป

### Scope Positioning

#### Base Scope

- LINE OA Text Chat
- Secure Webhook
- Claude Haiku 4.5
- RAG และ Vector Database
- Source Reference
- Controlled Answer
- Fallback
- Disclaimer
- Monitoring
- Traceability
- Rate Limiting
- Cost Control

#### ไม่รวมใน Zone 1

- การจดจำผู้ใช้ระยะยาว
- Personalized Recommendation
- CRM Integration
- Appointment
- Human Advisor Workspace
- LINE MINI App

---

# Appendix B — Zone 2: Personal Business Assistant  
## From Answering Questions to Guiding Improvement

### บทบาทของ Zone นี้

ยกระดับ MiAi จากระบบที่รอให้ผู้ใช้ถาม ไปสู่ผู้ช่วยธุรกิจที่เข้าใจบริบท แนะนำสิ่งที่ควรทำ และติดตามผลอย่างต่อเนื่อง

หัวใจของ Zone นี้คือการเปลี่ยนจาก

> Generic Answer

ไปสู่

> Recommendation based on Business Context

### User Journey

> Build Profile → Diagnose Business → Recommend Priority → Create Action Plan → Remind → Review Progress

### Core Capabilities

#### 1. Business Profile

เก็บข้อมูลที่ผู้ใช้ยินยอมให้บันทึก เช่น

- ประเภทธุรกิจ
- สินค้าและบริการ
- จำนวนพนักงาน
- อายุธุรกิจ
- พื้นที่ดำเนินงาน
- ปัญหาหลัก
- เป้าหมายทางธุรกิจ

#### 2. Business Health Check

ประเมินสถานะเบื้องต้นในแต่ละด้าน เช่น

- การบริหารธุรกิจ
- การตลาดและยอดขาย
- การผลิตและการดำเนินงาน
- คุณภาพ
- สินค้าคงคลัง
- การเงิน
- บุคลากร
- การเติบโต

ผลลัพธ์ควรแสดงเป็นภาพรวมที่เข้าใจง่าย เพื่อช่วยให้ผู้ประกอบการเห็นประเด็นที่ควรให้ความสำคัญก่อน

#### 3. Personalized Recommendation

เลือกคำแนะนำตามบริบทของผู้ใช้ เช่น

> ร้านอาหารที่มียอดขายลดลงและยังไม่มีฐานลูกค้าประจำ  
> ควรเริ่มจากการวิเคราะห์กลุ่มลูกค้า ปรับเมนูเด่น และสร้างช่องทางติดตามลูกค้าผ่าน LINE OA

#### 4. Improvement Plan

แปลงคำแนะนำให้เป็น Action Plan ที่ลงมือทำได้ เช่น

- สิ่งที่ต้องทำ
- ผู้รับผิดชอบ
- กำหนดเวลา
- ตัวชี้วัด
- สถานะ
- สิ่งที่ควรทำต่อไป

#### 5. Reminder & Follow-up

แจ้งเตือนกิจกรรมและติดตามความคืบหน้า เช่น

- Checklist ที่ยังไม่เสร็จ
- กำหนดติดตามผล
- Workshop ที่เกี่ยวข้อง
- นัดหมายกับที่ปรึกษา
- การส่งข้อมูลเพิ่มเติม

#### 6. Progress Summary

สรุปการพัฒนาให้ผู้ใช้เห็น เช่น

- ภารกิจที่ทำสำเร็จ
- Business Health Score
- เป้าหมายที่คืบหน้า
- ปัญหาที่ยังต้องปรับปรุง
- Recommendation รอบถัดไป

### Example Experience

ผู้ประกอบการถามว่า

> “ยอดขายลดลงมา 3 เดือน ควรเริ่มแก้ตรงไหน”

#### Zone 1

ตอบด้วยองค์ความรู้และขั้นตอนเบื้องต้นจากฐานความรู้ TSI

#### Zone 2

ถามบริบทเพิ่มเติม เช่น

- ลูกค้าหลักคือใคร
- ยอดขายลดจากช่องทางใด
- มีข้อมูลลูกค้าเก่าหรือไม่
- มีสินค้าใดขายดีที่สุด
- เคยทำโปรโมชั่นแบบใด

จากนั้นระบบสร้าง

> Business Diagnosis → Priority Problem → 7-day Improvement Plan → Follow-up

### Business Value

- ทำให้คำแนะนำเกี่ยวข้องกับธุรกิจแต่ละราย
- เปลี่ยนความรู้เป็นการลงมือทำ
- สร้างเหตุผลให้ผู้ประกอบการกลับมาใช้งานต่อ
- เพิ่มโอกาสเข้าสู่กิจกรรมหรือโครงการของ TSI
- สร้างข้อมูลสำหรับวางแผนช่วยเหลือ SME
- เพิ่ม Engagement ระยะยาว

### Data & Privacy Principles

- เก็บข้อมูลเมื่อได้รับ Consent
- แยกข้อมูลส่วนบุคคลออกจาก Technical Log
- ให้ผู้ใช้ตรวจสอบและแก้ไขข้อมูลได้
- กำหนดระยะเวลาการเก็บข้อมูล
- ไม่ใช้ข้อมูลนอกวัตถุประสงค์ที่แจ้งไว้
- รองรับการถอนความยินยอม
- รองรับการลบข้อมูลตามนโยบายที่กำหนด

### Scope Positioning

Zone 2 อยู่นอก Base TOR ที่มุ่งเน้น Closed-domain AI Advisor จึงควรวางเป็น

> **Optional Module หรือ Phase 2**

เพื่อไม่ให้ราคา ระยะเวลา และความซับซ้อนของ Proposal หลักสูงเกินไป

---

# Appendix C — Zone 3: LINE Ecosystem  
## From Conversation to Action and Long-term Relationship

### บทบาทของ Zone นี้

ใช้ LINE เป็นมากกว่าช่องทางแชท โดยเชื่อม Messaging, MINI App, กิจกรรม, แบบฟอร์ม และบริการของ TSI เข้าเป็น Ecosystem เดียว

แนวคิดสำคัญคือ

> LINE OA = Communication Layer  
> LINE MINI App = Service & Transaction Layer  
> Messaging API = Automation & Relationship Layer

### Ecosystem Components

#### 1. LINE OA Messaging

เหมาะสำหรับการสื่อสารที่รวดเร็วและต่อเนื่อง เช่น

- AI Q&A
- Quick Reply
- Flex Message
- ข่าวสารและบทความ
- แจ้งเตือน
- Follow-up
- สถานะการสมัคร
- คำแนะนำเฉพาะบุคคล

#### 2. LINE MINI App

เหมาะสำหรับงานที่มีหลายขั้นตอนหรือจำเป็นต้องแสดงข้อมูลเป็นหน้าจอ เช่น

- Business Profile
- Business Health Check
- Improvement Plan
- Checklist และ Progress
- Event Registration
- Learning Center Booking
- Application Form
- Advisor Appointment
- My Activities
- Consent Management

#### 3. TSI Program Connection

เชื่อมคำแนะนำจาก AI ไปสู่บริการจริง เช่น

- สมัครเข้าร่วมโครงการ
- จองเยี่ยมชมศูนย์เรียนรู้
- สมัคร Workshop
- ขอรับคำปรึกษา
- นัดหมายเจ้าหน้าที่
- ดาวน์โหลดเครื่องมือหรือ Template
- เข้าร่วม Community

#### 4. Human Handoff

เมื่อ AI ไม่สามารถตอบได้ หรือพบว่าผู้ใช้ต้องการคำแนะนำเชิงลึก ระบบสามารถส่งต่อให้เจ้าหน้าที่พร้อม Context เช่น

- ข้อมูลธุรกิจ
- คำถามก่อนหน้า
- ปัญหาหลัก
- เอกสารที่ระบบแนะนำ
- สิ่งที่ผู้ใช้ทดลองทำแล้ว
- เหตุผลที่ส่งต่อ

สิ่งนี้ช่วยลดเวลาที่เจ้าหน้าที่ต้องถามข้อมูลซ้ำ และทำให้การให้คำปรึกษาต่อเนื่องมากขึ้น

#### 5. Dashboard & CRM Connection

ข้อมูลจาก LINE Ecosystem สามารถส่งต่อไปยัง Dashboard หรือ CRM เพื่อให้ TSI เห็น

- จำนวนผู้ใช้งาน
- หัวข้อที่ถูกถามบ่อย
- ประเภทปัญหาของ SME
- Conversion ไปสู่กิจกรรม
- ผู้ที่ต้องการการช่วยเหลือเพิ่มเติม
- Follow-up Status
- Knowledge Gap
- Engagement ต่อเนื่อง
- ประสิทธิภาพของแต่ละ Program

### End-to-end Journey

> LINE Entry  
> → Ask MiAi  
> → Diagnose Business  
> → Receive Recommendation  
> → Open MINI App  
> → Complete Improvement Plan  
> → Join Workshop or Apply  
> → Receive Reminder  
> → Follow-up with TSI

### Example Trigger-to-Action

| Trigger จากการสนทนา | Next Best Action |
|---|---|
| ผู้ใช้ถามเรื่องสต็อกหลายครั้ง | เปิด Inventory Health Check |
| ต้องการตัวอย่างธุรกิจจริง | แนะนำ Case Study หรือศูนย์เรียนรู้ |
| ปัญหาซับซ้อนเกินฐานความรู้ | ส่งต่อ Human Advisor |
| สนใจเข้าร่วมโครงการ | เปิด Application Form |
| มี Checklist ที่ยังไม่เสร็จ | ส่ง Reminder ผ่าน LINE |
| ทำภารกิจสำเร็จ | แนะนำขั้นตอนพัฒนาระดับถัดไป |
| สนใจเรียนรู้เพิ่มเติม | แนะนำ Workshop ที่เกี่ยวข้อง |
| ต้องการความช่วยเหลือเฉพาะด้าน | นัดหมายผู้เชี่ยวชาญ |

### Business Value

- ลดช่องว่างระหว่างการได้รับคำแนะนำกับการลงมือทำ
- เพิ่ม Conversion เข้าสู่กิจกรรมและโครงการ TSI
- ลดการกรอกข้อมูลซ้ำระหว่าง LINE และแบบฟอร์ม
- สร้างความสัมพันธ์กับผู้ประกอบการอย่างต่อเนื่อง
- ทำให้ TSI เห็น Journey ของผู้ใช้ตั้งแต่เริ่มถามจนได้รับความช่วยเหลือ
- รองรับการขยาย Community และ CRM
- สร้างฐานข้อมูลเพื่อพัฒนา Program ในอนาคต

### Scope Positioning

#### Phase 1

- LINE OA Integration
- Messaging API
- Rich Menu
- Quick Reply
- Flex Message
- Basic Notification

#### Phase 2

- LINE MINI App
- Business Profile
- Business Health Check
- Booking
- Application
- Personalized Follow-up

#### Phase 3

- CRM Integration
- Human Advisor Workspace
- Community
- Campaign Automation
- Advanced Business Intelligence
- Cross-program Recommendation

---

# Appendix D — How the Three Zones Work Together

| Zone | หน้าที่หลัก | User Value | TSI Value |
|---|---|---|---|
| Zone 1: AI Q&A | ตอบคำถามจากองค์ความรู้ TSI | ได้คำตอบรวดเร็วและเชื่อถือได้ | ลดคำถามซ้ำและเห็น Knowledge Gap |
| Zone 2: Personal Business Assistant | เข้าใจบริบทและแนะนำสิ่งที่ควรทำ | ได้แผนที่เหมาะกับธุรกิจตนเอง | เพิ่ม Engagement และข้อมูลเชิงลึก |
| Zone 3: LINE Ecosystem | เชื่อมคำแนะนำไปสู่บริการและกิจกรรม | ลงมือทำได้ใน Journey เดียว | เพิ่ม Conversion และสร้างความสัมพันธ์ |

## Strategic Role of Each Zone

### Zone 1 — Build Trust

ทำให้ผู้ประกอบการมั่นใจว่าคำตอบมาจากองค์ความรู้ที่ TSI รับรองและตรวจสอบได้

### Zone 2 — Build Relevance

เปลี่ยนคำตอบทั่วไปให้เป็นคำแนะนำที่เหมาะกับบริบท เป้าหมาย และความพร้อมของผู้ประกอบการแต่ละราย

### Zone 3 — Drive Action

เชื่อมคำแนะนำไปสู่การสมัคร การจอง การเข้าร่วมกิจกรรม การติดตามผล และการได้รับความช่วยเหลือจาก TSI

## Final Message

> **Zone 1 สร้างความเชื่อมั่น**  
> **Zone 2 สร้างความเกี่ยวข้องกับผู้ใช้แต่ละราย**  
> **Zone 3 เปลี่ยนคำแนะนำให้เกิดการลงมือทำ**

หรือสรุปเป็น Journey เดียว

> **Ask → Understand → Improve → Connect → Grow**

---

# Recommended Roadmap

## Phase 1 — Trusted AI Advisor

สร้างรากฐาน AI Q&A ที่ปลอดภัย เชื่อถือได้ และตรวจสอบย้อนหลังได้

## Phase 2 — Personalized Assistance

เพิ่ม Business Profile, Business Health Check, Personalized Recommendation และ Follow-up

## Phase 3 — Connected TSI Ecosystem

เชื่อม LINE MINI App, Program, Booking, CRM, Human Advisor และ Community

## Closing Positioning

> **MiAi 2.0 is not only a chatbot.**  
> It is a trusted business advisory ecosystem that turns TSI knowledge into personalized guidance, practical action, and continuous business improvement.