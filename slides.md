---

marp: true
theme: mahidol
size: 16:9
paginate: true
title: 'ความก้าวหน้าระบบ VARD'
author: 'คณะวิศวกรรมศาสตร์ มหาวิทยาลัยมหิดล'
footer: 'VARD · ความก้าวหน้าระบบต้นแบบ'


---

<style>
@import url('themes/local-fonts.css');
section { --font-default:'Noto Sans Thai','Leelawadee UI',sans-serif; }
section:not(.lead):not(.divider) { padding-bottom:72px; }
section.divider h2:last-of-type { font-size:44px; line-height:1.5; max-width:1100px; }
h2 { font-size:34px; }
h3 { margin-top:20px; }
.caption { color:#526681; font-size:18px; line-height:1.5; margin-top:18px; border-left:4px solid #0891b2; padding-left:14px; }
.workflow { display:flex; align-items:center; gap:15px; margin:28px 0 32px; }
.workflow>div { flex:1; border-top:4px solid #2563eb; padding:20px 8px; background:#f0f6ff; text-align:center; }
.workflow span { display:block; font-size:19px; margin-top:12px; }
.workflow i { font-style:normal; font-size:30px; color:#0891b2; }
.evidence-split { display:grid; grid-template-columns:38% 1fr; gap:50px; align-items:center; }
.evidence-split>img { width:100%; height:420px; object-fit:contain; }
.evidence-split h3 { margin-top:6px; }
.evidence-split p,.evidence-split li { font-size:23px; }
.screen-grid { display:grid; grid-template-columns:30% 1fr; gap:24px; align-items:start; }
.screen-grid b { display:block; font-size:19px; margin-bottom:8px; }
.screen-grid img { display:block; width:100%; object-fit:contain; }
.screen-grid>div:first-child img { height:162px; margin-bottom:8px; }
.screen-grid>div:last-child img { height:374px; }
.definition { color:#1e3a8a; font-size:24px; line-height:1.5; border-left:4px solid #0891b2; padding-left:16px; }
.principles { display:grid; grid-template-columns:1fr 1fr; gap:42px; margin-top:12px; }
.principles h3 { font-size:23px; margin:12px 0 4px; }
.principles p { font-size:21px; line-height:1.45; margin:0 0 10px; }
.big-number { font-size:62px; color:#0891b2; font-weight:700; line-height:1.2; margin:5px 0 12px; }
.results { display:grid; grid-template-columns:60% 1fr; gap:28px; }
.results h3 { margin-top:0; font-size:24px; }
.bar-row { display:grid; grid-template-columns:160px 1fr 62px; gap:10px; align-items:center; height:42px; font-size:18px; }
.bar-row>b { font-size:19px; color:#1e3a8a; }
.bar-track { height:21px; background:#e5eaf2; }
.bar-track>div { height:100%; background:#0891b2; }
.results table { font-size:18px; margin-top:12px; }
.results td,.results th { padding:5px 9px; }
.results-slide .caption { margin-top:15px; }
.detail-table table {font-size:20px;}
.detail-table td,.detail-table th {padding:7px 10px;}
.detail-table h2 {font-size:32px;}
.example {font-size:21px;color:#526681;border-left:4px solid #d59b31;padding-left:14px;margin:16px 0;}
.comparison {display:grid;grid-template-columns:1fr 1fr;gap:36px;}
.comparison h3 {margin-top:0;}
.comparison li {font-size:23px;}
.gold-ui {display:grid;grid-template-columns:53% 1fr;gap:28px;align-items:start;}
.gold-ui img {width:100%;height:425px;object-fit:contain;}
.gold-ui h3 {font-size:24px;margin-top:8px;}
.gold-ui p {font-size:22px;}
.trace {display:grid;grid-template-columns:1fr 1fr 1fr;gap:24px;margin:20px 0;}
.trace div {border-top:4px solid #2563eb;padding-top:12px;}
.trace h3 {margin:0 0 12px;}
.trace p {font-size:22px;}

section.large-workflow:not(.lead):not(.divider) {padding-top:116px;padding-bottom:68px;}
section.large-workflow .evidence-split {grid-template-columns:55% 1fr;gap:28px;align-items:center;}
section.large-workflow .evidence-split>img {width:100%;height:510px;object-fit:contain;}
section.large-workflow .evidence-split p,section.large-workflow .evidence-split li {font-size:22px;}
section.large-workflow .evidence-split h3 {font-size:25px;}
section.large-workflow .caption {margin-top:5px;font-size:17px;line-height:1.4;}

section.concept-overview:not(.lead):not(.divider) {padding-top:126px;padding-bottom:68px;}
section.concept-overview .concept-figure {display:block;width:100%;height:474px;object-fit:contain;}
section.concept-overview .caption {font-size:17px;line-height:1.45;margin-top:9px;}

section header {position:absolute;top:13px;right:64px;left:auto;z-index:5;margin:0;padding:1px 9px;border:1px solid #b45309;color:#92400e;background:#fff7ed;font-size:13px;font-weight:700;line-height:1.4;letter-spacing:.08em;}
section.lead header {top:22px;right:210px;background:#fff7ed;}
section.divider header {background:#fff7ed;}
.jev-context {font-size:19px;line-height:1.45;color:#526681;margin:0 0 14px;padding-left:12px;border-left:4px solid #d59b31;}
section.d3-model-summary .results {grid-template-columns:54% 1fr;gap:24px;}
section.d3-model-summary .results table {font-size:17px;}
section.d3-model-summary .results td,section.d3-model-summary .results th {padding:5px 7px;}
section.d3-model-summary .caption {font-size:17px;line-height:1.4;}
section.d3-full-models table {font-size:19px;}
section.d3-full-models td,section.d3-full-models th {padding:6px 9px;}
section.d3-full-models td:first-child {white-space:nowrap;}
section.d3-full-models .caption {font-size:17px;line-height:1.4;}
section.d3-field-models table {font-size:20px;}
section.d3-field-models td,section.d3-field-models th {padding:6px 9px;}
section.d3-field-models .caption {font-size:17px;line-height:1.4;}

/* D3 report-aligned identifiers and Set1 results */
.model-id {white-space:nowrap;font-family:'Noto Sans Thai','Leelawadee UI',sans-serif;font-weight:400;}
.metric-scope {font-size:22px;color:#526681;margin:0 0 15px;}
.model-bar-row {display:grid;grid-template-columns:390px 1fr 64px;gap:14px;align-items:center;height:39px;}
.model-bar-row .model-id {font-size:19px;}
.model-bar-row>b {font-size:21px;color:#1e3a8a;text-align:right;}
.model-bar-row .bar-track {height:23px;}
.bar-axis {display:flex;justify-content:space-between;margin:8px 78px 0 404px;font-size:16px;color:#64748b;}
section.d3-exact-full .caption {font-size:18px;line-height:1.5;margin-top:24px;}
section.d3-timing-full .model-bar-row {height:33px;}
section.d3-timing-full .bar-track>div {background:#1e3a8a;}
.time-explanation {font-size:20px;line-height:1.55;margin-top:20px;border-left:4px solid #0891b2;padding-left:15px;}
section.d3-table35 table {font-size:19px;table-layout:fixed;margin-top:0;margin-bottom:14px;}
section.d3-table35 th:first-child {width:47%;}
section.d3-table35 td,section.d3-table35 th {padding:6px 10px;}
section.d3-table35 td:not(:first-child) {text-align:right;}
.agreement-warning {font-size:18px;line-height:1.5;color:#526681;border-left:4px solid #d59b31;padding-left:14px;}
.timing-comparison {font-size:19px;line-height:1.55;margin-top:14px;color:#1e3a8a;}
section.d3-jev-mechanism .definition {font-size:23px;line-height:1.6;}
section.d3-jev-mechanism table {font-size:21px;margin:16px 0;}
.jev-pilot {font-size:20px;line-height:1.6;color:#1e3a8a;}
section.d3-jev-mechanism .caption {font-size:17px;margin-top:15px;}
section.d3-full-models .caption {font-size:17px;line-height:1.5;}
section.d3-full-models table {font-size:19px;}
section.d3-full-models td,section.d3-full-models th {padding:7px 9px;}
section.d3-full-models td:first-child {white-space:nowrap;}
section.d3-fields-complete table {table-layout:fixed;font-size:18px;margin-top:0;}
section.d3-fields-complete th:first-child {width:37%;}
section.d3-fields-complete th {font-size:16px;}
section.d3-fields-complete td,section.d3-fields-complete th {padding:8px 7px;}
section.d3-fields-complete td:not(:first-child) {text-align:center;}
section.d3-fields-complete .model-id {font-size:17px;}
section.d3-fields-complete .caption {font-size:17px;line-height:1.5;}

/* D6 executive review and progress summary */
section.d6-method .big-number {font-size:56px;margin:5px 0 8px;}
section.d6-method li {font-size:25px;line-height:1.55;}
section.d6-status li {font-size:25px;line-height:1.5;}
section.d6-status blockquote {font-size:23px;}
section.d6-plan table {font-size:21px;}
section.d6-plan td,section.d6-plan th {padding:9px 10px;}
section.d6-sequence table {font-size:20px;}
section.d6-sequence td,section.d6-sequence th {padding:9px 10px;}
section.d6-progress table {table-layout:fixed;font-size:22px;line-height:1.45;}
section.d6-progress th:first-child {width:21%;}
section.d6-progress th:nth-child(2) {width:36%;}
section.d6-progress td,section.d6-progress th {padding:12px 13px;}
.d6-progress-status {font-size:25px;color:#0891b2;font-weight:600;margin:0 0 18px;}
.d6-decision {font-size:22px;line-height:1.5;color:#1e3a8a;border-left:4px solid #2563eb;padding-left:16px;margin-top:18px;}
</style>

<!-- _class: lead -->
<!-- _paginate: false -->

<img class="university-logo" src="fig/logos/mahidol.svg" alt="Mahidol University">

# ความก้าวหน้าระบบ VARD

<div class="subtitle">ฉบับละเอียด: ระบบต้นแบบและผลประเมินเบื้องต้น</div>

ระบบอัตโนมัติเพื่อทบทวนและรวบรวมข้อมูลการวิจัยพัฒนาวัคซีน<br>และผลิตภัณฑ์วัคซีนด้วยปัญญาประดิษฐ์

**ผศ.ดร. ทวีศักดิ์ สมานชื่น** หัวหน้าโครงการ<br>
คณะวิศวกรรมศาสตร์ มหาวิทยาลัยมหิดล

อ้างอิงรายงานเชิงเทคนิควันที่ 29 ตุลาคม 2569

<!-- ข้อมูลชื่อผู้วิจัยและหน่วยงาน: main(3).pdf วันที่ 29 ตุลาคม 2569 หน้าปก; แหล่งทุนตามข้อเสนอ: สถาบันวัคซีนแห่งชาติ; NRIIS 4863782 -->





---

## เนื้อหาการนำเสนอ

1. ที่มา วัตถุประสงค์ และขอบเขตโครงการ
2. ภาพรวมและสถาปัตยกรรมระบบ VARD
3. กระบวนการรวบรวม สกัด และตรวจทานข้อมูล
4. ตัวอย่างหน้าจอและการใช้งานระบบต้นแบบ
5. การสร้าง Gold Standard และผลประเมิน AI เบื้องต้น
6. สถานะปัจจุบัน ข้อจำกัด และแผนพัฒนาระยะถัดไป

<!-- แหล่งข้อมูล: agenda.md -->





---

<!-- _class: divider -->

## 01
## ที่มา วัตถุประสงค์ และขอบเขตโครงการ

Project rationale and scope





---

## ที่มาและปัญหาที่โครงการต้องการแก้

### ข้อมูลวิจัยวัคซีนกระจายในหลายแหล่ง

- รูปแบบข้อมูลต่างกัน ทำให้รวบรวมและเปรียบเทียบได้ยาก
- ต้องจัดโครงสร้างและใช้คำศัพท์ให้สอดคล้องกัน
- ทุกค่าควรตรวจย้อนกลับถึงเอกสารและหลักฐานต้นฉบับได้

> โครงการเตรียมข้อมูลเพื่อสนับสนุนระบบข้อมูลและบริหารจัดการวัคซีน (VIMS) ของสถาบันวัคซีนแห่งชาติ

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 1.1 -->





---

## วัตถุประสงค์และบทบาทของ VARD

<div class="workflow">
<div><b>รวบรวม</b><span>ข้อมูลและต้นฉบับ</span></div><i>→</i>
<div><b>สกัด</b><span>กฎร่วมกับ AI</span></div><i>→</i>
<div><b>ตรวจทาน</b><span>ผู้เชี่ยวชาญและหลักฐาน</span></div><i>→</i>
<div><b>เตรียมใช้</b><span>ข้อมูลสำหรับ VIMS</span></div>
</div>

- จัดข้อมูลตามโครงสร้าง พร้อมหลักฐานและประวัติการแก้ไข
- ใช้ AI ช่วยงาน โดยผู้เชี่ยวชาญตรวจรับข้อมูลก่อนนำไปใช้

<div class="caption">การส่งออกไฟล์ยังไม่เท่ากับการเชื่อมต่อ VIMS ที่เสร็จสมบูรณ์</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 1.1–1.3 และ 2.5 -->





---

## ขอบเขตข้อมูลและกลุ่มวัคซีนนำร่อง

| หมวดข้อมูล | พจนานุกรมฉบับร่าง | สถานะตามรายงาน |
|---|---:|---|
| พรีคลินิก | 17 ฟิลด์ | งานขยายระยะถัดไป |
| การทดลองทางคลินิก | 22 ฟิลด์ | ต้นแบบและผลประเมินนำร่อง |
| การขึ้นทะเบียน | 19 ฟิลด์ | งานขยายระยะถัดไป |
| ผลิตภัณฑ์วัคซีนทั่วโลก | 36 ฟิลด์ | งานขยายระยะถัดไป |

**กลุ่มนำร่อง:** MMR, VZ และ FLU<br>
ต้นแบบที่รายงานเน้นข้อมูลทางคลินิกจาก ClinicalTrials.gov

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 1.2, 2.4.2 และ 4.3 -->





---

<!-- _class: detail-table -->

## มาตรฐานข้อมูลที่ต้องยืนยันกับ VIMS

| ประเด็น | สิ่งที่ต้องตกลงให้ตรงกัน |
|---|---|
| นิยามฟิลด์ | ความหมาย ขอบเขต และแหล่งหลักฐานที่ยอมรับ |
| ชนิดและรูปแบบข้อมูล | วันที่ ปี ตัวเลข ข้อความ และรูปแบบค่าว่าง |
| คำศัพท์ควบคุม | สถานะการศึกษา ระยะ แพลตฟอร์ม และวิธีให้วัคซีน |
| ตัวระบุและความสัมพันธ์ | รหัสงานวิจัย วัคซีน และ vaccine candidate |
| การส่งออก | ฟิลด์บังคับ/ไม่บังคับ และตารางเทียบกับ VIMS |

<div class="caption">พจนานุกรมฉบับร่างมีชื่อและชนิดข้อมูลต่างรูปแบบ เช่น MainPhase/Mainphase จึงต้องยืนยันชื่อมาตรฐานและ mapping ก่อนเชื่อมต่อจริง</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.4.2 และ 4.4 -->




---

<!-- _class: divider -->

## 02
## ภาพรวมและสถาปัตยกรรมระบบ VARD

System overview and architecture





---

<!-- _class: concept-overview -->

## กรอบแนวคิดภาพรวมของระบบ

<img class="concept-figure" src="fig/evidence/system-concept.png" alt="ภาพที่ 2.1 กระบวนการหลักตั้งแต่แหล่งข้อมูลจนเตรียมผลลัพธ์สำหรับ VIMS และเส้นทางประเมิน Gold Standard แบบออฟไลน์ที่แยกออกมา">

<div class="caption">เส้นทึบ: กระบวนการจัดเตรียมข้อมูลหลัก · เส้นประ: สร้างชุดอ้างอิงและเปรียบเทียบผลโมเดลแบบออฟไลน์</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.3 ภาพที่ 2.1 -->





---

<!-- _class: large-workflow -->


## สถาปัตยกรรมระบบต้นแบบ

<div class="evidence-split">
<img src="fig/evidence/architecture.png" alt="สถาปัตยกรรมและกระบวนการทำงานของระบบต้นแบบ">
<div>
<h3>ส่วนติดต่อและประมวลผล</h3>
<p>React สำหรับผู้ใช้<br>FastAPI รับคำขอ<br>worker จัดคิวและประมวลผลเบื้องหลัง</p>
<h3>ข้อมูลและบริการภายนอก</h3>
<p>PostgreSQL และระบบไฟล์<br>ClinicalTrials.gov และบริการ LLM<br>เลือกประมวลผลในเครื่องหรือคลาวด์</p>
</div></div>
<div class="caption">สถาปัตยกรรมตามเอกสารต้นแบบ ยังต้องทดสอบสิทธิ์และกระบวนการครบวงจร</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.5 ภาพที่ 2.2 -->





---

<!-- _class: detail-table -->

## บทบาทผู้ใช้ในงานตรวจทานและชุดอ้างอิง

| บทบาท | หน้าที่ตามเอกสาร | ผลลัพธ์หลัก |
|---|---|---|
| admin | จัดบัญชี/บทบาท และจัดการชุดอ้างอิง | สิทธิ์ผู้ใช้และชุดงาน |
| reviewer | ตรวจ แก้ไข ปฏิเสธ หรืออนุมัติระเบียน | ข้อมูลที่เตรียมนำไปใช้งาน |
| expert | อ่านต้นฉบับและให้คำตอบอ้างอิงอย่างอิสระ | คำตอบและหลักฐานรายฟิลด์ |
| head adjudicator | ตัดสินกรณีผู้เชี่ยวชาญเห็นต่าง | คำตอบสุดท้ายและเหตุผล |

> การตรวจแก้ข้อมูลใช้งานและการสร้างเกณฑ์ประเมินโมเดลเป็นคนละกระบวนการ

<div class="caption">ตารางนี้อธิบายการออกแบบบทบาท ยังต้องมีผลทดสอบการบังคับใช้สิทธิ์จริง</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.4 ตาราง 2.5 และ 2.6 -->




---

<!-- _class: divider -->

## 03
## กระบวนการรวบรวม สกัด และตรวจทานข้อมูล

Data collection, extraction and review





---

## การนำเข้าและจัดโครงสร้างข้อมูล

1. ค้นหาและดึงระเบียนจาก ClinicalTrials.gov ผ่าน API
2. เก็บ JSON ต้นฉบับ ข้อมูลแหล่งที่มา และ content hash
3. จับคู่ฟิลด์กับพจนานุกรมฉบับร่างและตรวจสอบตามกฎ
4. เชื่อมระเบียนกับวัคซีนหรือ vaccine candidate

<div class="caption">content hash ช่วยตรวจสอบเนื้อหาต้นฉบับ ส่วนจำนวนที่ดึง อนุมัติ และส่งออกจริงยังไม่มีตัวเลขยืนยันในรายงาน</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.4–2.5 -->





---

## การเก็บที่มาและประวัติของข้อมูล

<div class="trace">
<div><h3>ต้นฉบับ</h3><p>JSON จากแหล่งข้อมูล<br>ตำแหน่งไฟล์และ content hash</p></div>
<div><h3>ระเบียน</h3><p>ค่าที่จับคู่หรือสกัด<br>ประเด็น validation และรุ่นข้อมูล</p></div>
<div><h3>การตัดสินใจ</h3><p>ค่าก่อน–หลัง เหตุผล<br>ประวัติการอนุมัติและชุดส่งออก</p></div>
</div>

- PostgreSQL เก็บข้อมูลที่จัดโครงสร้างและข้อมูลกำกับ
- ระบบไฟล์เก็บเอกสารต้นฉบับและไฟล์ส่งออกของต้นแบบ

<div class="caption">content hash ช่วยตรวจสอบเนื้อหา ส่วนแผนสำรอง กู้คืน และติดตามระบบจริงยังต้องกำหนดเพิ่มเติม</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.4–2.5 และภาคผนวก A -->




---

## ขอบเขตงานของกฎและ LLM

<div class="comparison">
<div><h3>JSON parser และกฎ</h3><ul><li>อ่านฟิลด์ที่มีโครงสร้างจากต้นทาง</li><li>จับคู่ชื่อและรูปแบบข้อมูล</li><li>ตรวจเงื่อนไขตาม pilot schema</li></ul></div>
<div><h3>LLM ที่เรียกตามคำขอ</h3><ul><li>ช่วยตีความข้อความเพื่อเติมช่องว่าง</li><li>เสนอค่าพร้อมข้อความหลักฐาน</li><li>ให้ผู้ตรวจทานพิจารณาก่อนรับค่า</li></ul></div>
</div>

> ข้อมูลที่อ่านจากต้นทางได้โดยตรงและข้อมูลที่ AI เสนอควรมีที่มาให้ตรวจสอบได้

<div class="caption">LLM เป็นบริการเสริมในต้นแบบ ไม่ได้แทนการจับคู่ฟิลด์และการตรวจทานทั้งหมด</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.4–2.5 -->




---

## การใช้ AI ช่วยสกัดและเติมข้อมูล

### เติมเฉพาะช่องว่างตามคำขอของผู้ตรวจทาน

- โมเดลภาษาขนาดใหญ่ (LLM) เสนอค่าพร้อมข้อความอ้างอิง
- ระบบตรวจว่าข้อความอ้างอิงปรากฏในเอกสารต้นฉบับ
- ผู้เชี่ยวชาญตรวจว่าหลักฐานสนับสนุนความหมายของค่านั้นจริง
- กระบวนการเติมข้อมูลไม่เขียนทับค่าที่มีอยู่

> การพบข้อความตรงต้นฉบับยังไม่เพียงพอที่จะยืนยันว่าค่าที่ AI เสนอถูกต้อง

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.5 -->





---

<!-- _class: detail-table -->

## การพบข้อความกับการมีหลักฐานสนับสนุน

<div class="example">ตัวอย่างสมมติเพื่ออธิบายหลักการ ไม่ใช่ผลทดลองรายกรณีของโครงการ</div>

**ข้อความต้นฉบับสมมติ:** “Participants received Vaccine A; Vaccine B was used as a comparator.”

| สิ่งที่ AI เสนอ | สิ่งที่ต้องตรวจ |
|---|---|
| วัคซีนที่ศึกษา = Vaccine B | คำว่า Vaccine B มีอยู่จริง แต่กล่าวถึงตัวเปรียบเทียบ |
| หลักฐานผ่านการค้นข้อความ | ยังต้องพิจารณาบริบทและนิยามของฟิลด์ |

> พบคำในต้นฉบับแล้ว ยังต้องตรวจว่าข้อความนั้นรองรับค่าของฟิลด์ที่กำลังสกัดจริง

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.5; ตัวอย่างสมมติเพื่ออธิบาย -->




---

## การตรวจทานโดยผู้เชี่ยวชาญและการส่งออก

<div class="columns">
<div><h3>Human-in-the-Loop</h3>
<p>ตรวจหลักฐาน แก้ไข ปฏิเสธ หรืออนุมัติ<br>เก็บค่าก่อน–หลัง เหตุผล และรุ่นของระเบียน</p></div>
<div><h3>ข้อมูลที่เตรียมส่งออก</h3>
<p>รับเฉพาะระเบียนที่อนุมัติและผ่าน validation<br>ส่งออกเป็น JSON, CSV และ manifest</p></div>
</div>

> ประวัติการตัดสินใจช่วยให้ตรวจสอบย้อนกลับได้

<div class="caption">ยังต้องยืนยัน export mapping และทดสอบการเชื่อมต่อกับเจ้าของข้อมูล VIMS</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.5 -->





---

<!-- _class: divider -->

## 04
## ตัวอย่างหน้าจอและการใช้งานระบบต้นแบบ

Prototype screens and review journey





---

## ตัวอย่างหน้าจอและเส้นทางการใช้งาน

<div class="screen-grid">
<div><b>ภาพรวมและลงชื่อเข้าใช้</b><img src="fig/evidence/overview.png" alt="หน้าภาพรวมและลงชื่อเข้าใช้ต้นแบบ"><b>แดชบอร์ดผู้ดูแล</b><img src="fig/evidence/dashboard.png" alt="แดชบอร์ดผู้ดูแลต้นแบบ"></div>
<div><b>ตรวจหลักฐาน แก้ไขหรืออนุมัติ แล้วส่งออก</b><img src="fig/evidence/review.png" alt="หน้าตรวจทานระเบียน NCT05952505"></div>
</div>
<div class="caption">ตัวอย่าง NCT05952505 อยู่ในสถานะ Review Pending ตัวเลขบนหน้าจอไม่ใช่ยอดการใช้งานจริงที่ยืนยันแล้ว</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.7 -->





---

## ตัวอย่างการตรวจหนึ่งระเบียนก่อนอนุมัติ

### จุดตรวจจากภาพ NCT05952505

1. ตรวจวัคซีนที่ศึกษาให้ต่างจากวัคซีนที่ให้ร่วม/ตัวเปรียบเทียบ
2. พิจารณาคำเตือนเรื่องความสอดคล้องของกลุ่มวัคซีนและ candidate
3. ตรวจความละเอียดของวันที่เริ่มศึกษาเมื่อแหล่งข้อมูลมีเพียงปี/เดือน
4. เปิดต้นฉบับ แก้ไขหรือคงค่า พร้อมบันทึกเหตุผลก่อนตัดสินใจ

> เมื่อข้อมูลผ่านการอนุมัติและ validation แล้ว จึงเตรียมส่งออก

<div class="caption">เป็นเส้นทางตรวจทานที่อธิบายจากภาพต้นแบบ ไม่ใช่บันทึกว่าระเบียนนี้ได้รับการแก้ไขหรืออนุมัติจริง</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.7 -->




---

<!-- _class: divider -->

## 05
## การสร้าง Gold Standard และผลประเมิน AI เบื้องต้น

Reference data and preliminary AI evaluation





---

## หลักการของ Gold Standard

<div class="definition">ชุดคำตอบอ้างอิงที่ผู้เชี่ยวชาญตรวจสอบ เพื่อใช้ประเมินความถูกต้องของข้อมูลที่ AI สกัด</div>
<div class="principles">
<div><h3>1. กำหนดเกณฑ์ให้ตรงกัน</h3><p>นิยามฟิลด์ รูปแบบคำตอบ และกรณีที่เอกสารไม่ระบุข้อมูล</p>
<h3>2. ยึดหลักฐานต้นฉบับ</h3><p>ทุกค่าต้องมีข้อความสนับสนุนและตรวจสอบย้อนกลับได้</p>
<h3>3. ให้คำตอบอย่างอิสระ</h3><p>ผู้เชี่ยวชาญไม่เห็นคำตอบของ AI หรือผู้เชี่ยวชาญคนอื่น</p></div>
<div><h3>4. ชี้ขาดเมื่อเห็นต่าง</h3><p>ผู้ชี้ขาดตรวจหลักฐานและบันทึกคำตอบพร้อมเหตุผล</p>
<h3>5. ตรึงชุดก่อนประเมิน</h3><p>ควบคุมรุ่น และแยกชุดประเมินจากข้อมูลที่ใช้ปรับ prompt</p>
<h3>6. วิเคราะห์ข้อผิดพลาด</h3><p>แยกค่าผิด เติมเกิน ตกหล่น และกรณีค่าว่างรายฟิลด์</p></div>
</div>
<div class="caption">ชุดอ้างอิงยังอาจมีข้อผิดพลาด จึงต้องเก็บหลักฐาน ตรวจทาน และควบคุมรุ่น</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6, 3.2 และ 4.4 -->





---

<!-- _class: detail-table -->

## การออกแบบชุด Gold Standard ให้ประเมินได้

| ก่อนเริ่มให้คำตอบ | รายละเอียดที่ควรกำหนด |
|---|---|
| ขอบเขตตัวอย่าง | กลุ่มวัคซีน แหล่งเอกสาร ฟิลด์ และเกณฑ์คัดเลือก |
| คู่มือการให้คำตอบ | นิยามฟิลด์ คำศัพท์ที่ยอมรับ และกรณีไม่ระบุข้อมูล |
| ความเป็นอิสระ | ผู้เชี่ยวชาญไม่เห็นผล AI หรือคำตอบของกันและกัน |
| การจัดการข้อขัดแย้ง | กติกาส่งชี้ขาดและการบันทึกเหตุผล |
| การประเมินรอบใหม่ | ตรึงรุ่นและแยกชุดพัฒนาออกจากชุดประเมิน |

<div class="caption">รายงานมี pilot 15 งานวิจัย 5 ฟิลด์ แต่ยังต้องแนบรายชื่อ เกณฑ์คัดเลือก และการกระจาย MMR/VZ/FLU เพื่อยืนยัน coverage</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6 และ 4.4; แนวทางเตรียมประเมินรอบถัดไป -->




---

<!-- _class: large-workflow -->


## กระบวนการสร้าง Gold Standard

<div class="evidence-split">
<img src="fig/evidence/gold-workflow.png" alt="กระบวนการจัดทำคำตอบอ้างอิงและประเมินโมเดลแบบออฟไลน์">
<div><h3>จากต้นฉบับสู่คำตอบอ้างอิง</h3>
<ol><li>ผู้ดูแลเลือกงานวิจัยและฟิลด์</li><li>ผู้เชี่ยวชาญให้คำตอบอย่างอิสระ</li><li>ผู้ชี้ขาดพิจารณากรณีเห็นต่าง</li><li>ผู้ดูแลตรึงชุดก่อนประเมินโมเดล</li></ol>
<p><strong>Set1 ตามรายงาน</strong><br>74 กรณีเห็นตรงกัน<br>1 กรณีชี้ขาด</p></div></div>
<div class="caption">ยังไม่มี annotations และบันทึกการชี้ขาดรายกรณีให้ตรวจยืนยันซ้ำ</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6 -->





---

<!-- _class: detail-table -->

## คำตอบอ้างอิงหนึ่งกรณีควรมีอะไรบ้าง

<div class="example">ตัวอย่างสมมติของรายการ annotation เพื่ออธิบายโครงสร้างการบันทึก</div>

| รายการ | ตัวอย่าง |
|---|---|
| ชุด / งานวิจัย / ฟิลด์ | Gold-v1 / STUDY-EXAMPLE / Platform |
| คำตอบผู้เชี่ยวชาญ | Inactivated Vaccine |
| หลักฐานต้นฉบับ | “The investigational product is an inactivated vaccine.” |
| สถานะ | มีข้อมูลในต้นฉบับ หรือ “ไม่ระบุข้อมูล” |
| ผู้ให้คำตอบและเหตุผล | ระบุผู้เชี่ยวชาญ พร้อมคำอธิบายที่ตรวจย้อนกลับได้ |

<div class="caption">ตัวอย่างนี้ไม่ใช่คำตอบจริงจาก Set1 ส่วนผลและหลักฐานรายกรณีของ Set1 ยังต้องแนบเพื่อตรวจยืนยัน</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6 และภาคผนวก A; ตัวอย่างสมมติเพื่ออธิบาย -->




---

<!-- _class: detail-table -->

## ตัวอย่างการเห็นต่างและการชี้ขาด

<div class="example">ตัวอย่างสมมติเพื่ออธิบายขั้นตอน ไม่ใช่กรณีชี้ขาด 1 กรณีที่รายงานใน Set1</div>

| ขั้นตอน | การพิจารณา |
|---|---|
| ผู้เชี่ยวชาญให้คำตอบ | คำตอบหนึ่งเป็นค่าแพลตฟอร์ม อีกคำตอบเป็น “ไม่ระบุข้อมูล” |
| ตรวจรูปแบบ | ปรับตัวพิมพ์ ขีดเชื่อม และช่องว่างตามกติกา |
| ส่งชี้ขาดหากยังต่าง | อ่านหลักฐาน นิยามฟิลด์ และขอบเขตของวัคซีนที่ศึกษา |
| บันทึกข้อยุติ | คำตอบสุดท้าย พร้อมหลักฐานและเหตุผล |

> ผู้ชี้ขาดตรวจความหมายจากหลักฐาน ไม่ควรเลือกตามคำตอบของ AI

<div class="caption">เมื่อจัดการข้อขัดแย้งครบแล้วจึงตรึงชุดและนำไปประเมินแบบออฟไลน์</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6; ตัวอย่างเพื่ออธิบายกระบวนการ -->




---

## หน้าจัดการชุดอ้างอิงและผลการชี้ขาด

<div class="gold-ui">
<img src="fig/evidence/gold-admin.png" alt="หน้าจัดการชุดอ้างอิงและผลการชี้ขาดจากรูป B.1">
<div><h3>สิ่งที่เห็นในภาพต้นแบบ</h3><p>เลือกชุดอ้างอิงและดูสถานะ<br>กำหนดชื่อชุดและรหัสงานวิจัย<br>ตรึงชุดและส่งออก CSV</p>
<h3>ตารางคำตอบรายกรณี</h3><p>แสดงคำตอบผู้เชี่ยวชาญ<br>คำตอบสุดท้าย และกรณีที่ชี้ขาด</p></div>
</div>
<div class="caption">ภาพจากภาคผนวก B ใช้อธิบาย UI เท่านั้น ยังไม่ยืนยันรุ่นระบบ การบังคับใช้สิทธิ์ หรือการทำงานครบวงจร</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 2.6 และภาคผนวก B -->




---

<!-- _class: d6-method -->

## กรอบการประเมินผลนำร่อง

<div class="big-number">15 งานวิจัย × 5 ช่องข้อมูล</div>

รวม **75 กรณีต่อโมเดล** จากข้อมูลการทดลองทางคลินิก

- เปรียบเทียบคำตอบของ 7 โมเดลข้อความกับคำตอบอ้างอิงของผู้เชี่ยวชาญ
- นับคำตอบที่ตรงกัน (exact match) พร้อมแยกค่าผิด ตอบเกิน และข้อมูลตกหล่น
- Jev เลือกจากรายการคำตอบที่กำหนดไว้ จึงรายงานแยกจากโมเดลข้อความ

<div class="caption">คะแนนรวมกรณีที่ต้นฉบับไม่มีข้อมูล จึงต้องแยกกรณีมีข้อมูลจริงก่อนสรุปความสามารถในการสกัด<br>ผลยังเป็นการประเมินนำร่อง ต้องขยายชุดข้อมูลและตรวจซ้ำก่อนยืนยันความพร้อมใช้งาน</div>

<!-- แหล่งข้อมูล: main(3).pdf วันที่ 29 ตุลาคม 2569 หัวข้อ 3.2 ตาราง 3.2–3.3; รวมเนื้อหาจาก D5 หน้า 29–31 -->

---

<!-- _class: d3-exact-full -->

## ผล exact match ของโมเดลข้อความบน Set1

<div class="metric-scope">กรณีงานวิจัย–ฟิลด์ 75 กรณีต่อการตั้งค่า · exact match (%)</div>
<div class="full-model-bars"><div class="model-bar-row"><span class="model-id">groq:openai/gpt-oss-120b</span><div class="bar-track"><div style="width:94.66666666666667%"></div></div><b>94.67</b></div><div class="model-bar-row"><span class="model-id">groq:openai/gpt-oss-20b</span><div class="bar-track"><div style="width:89.33333333333333%"></div></div><b>89.33</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:kimi-k3</span><div class="bar-track"><div style="width:88%"></div></div><b>88.00</b></div><div class="model-bar-row"><span class="model-id">groq:qwen/qwen3.8-27b</span><div class="bar-track"><div style="width:88%"></div></div><b>88.00</b></div><div class="model-bar-row"><span class="model-id">gemini:gemini-3.8-flash</span><div class="bar-track"><div style="width:86.66666666666667%"></div></div><b>86.67</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:gemma4:31b</span><div class="bar-track"><div style="width:85.33333333333334%"></div></div><b>85.33</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:deepseek-v4.1-flash</span><div class="bar-track"><div style="width:80%"></div></div><b>80.00</b></div></div>
<div class="bar-axis"><span>0%</span><span>100%</span></div>
<div class="caption"><span class="model-id">groq:openai/gpt-oss-120b</span> ตรง 71/75 (94.67%) สูงสุดในชุดนี้<br>คะแนนรวมกรณีต้นฉบับไม่มีข้อมูล ยังสรุปความสามารถสกัดเมื่อมีข้อมูลจริงไม่ได้<br>ต้องแยกกรณีมีค่า/ค่าว่าง และตรวจผลรายกรณีก่อนสรุปความพร้อมใช้งาน</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 ตาราง 3.3 และแผนภูมิ 3.1; หน้าเลขพิมพ์ 32–33; ชื่อการตั้งค่าถอดตามรายงาน ยังไม่ได้ยืนยันกับผู้ให้บริการ -->




---

<!-- _class: d3-timing-full -->

## เวลาเฉลี่ยตอบของโมเดลข้อความต่อรายการ

<div class="time-bars"><div class="model-bar-row"><span class="model-id">groq:qwen/qwen3.8-27b</span><div class="bar-track"><div style="width:6.3%"></div></div><b>0.63</b></div><div class="model-bar-row"><span class="model-id">groq:openai/gpt-oss-20b</span><div class="bar-track"><div style="width:10.3%"></div></div><b>1.03</b></div><div class="model-bar-row"><span class="model-id">groq:openai/gpt-oss-120b</span><div class="bar-track"><div style="width:15.7%"></div></div><b>1.57</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:gemma4:31b</span><div class="bar-track"><div style="width:18%"></div></div><b>1.80</b></div><div class="model-bar-row"><span class="model-id">gemini:gemini-3.8-flash</span><div class="bar-track"><div style="width:35.8%"></div></div><b>3.58</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:deepseek-v4.1-flash</span><div class="bar-track"><div style="width:54.800000000000004%"></div></div><b>5.48</b></div><div class="model-bar-row"><span class="model-id">ollama-cloud:kimi-k3</span><div class="bar-track"><div style="width:86.8%"></div></div><b>8.68</b></div></div>
<div class="bar-axis"><span>0</span><span>10 วินาที</span></div>
<div class="time-explanation">Qwen ตอบเฉลี่ย 0.63 วินาที และ Kimi 8.68 วินาทีต่อรายการในรอบทดลองนี้<br>วัดเฉพาะเวลาตอบของโมเดล ยังไม่รวมการดึงข้อมูลและการตรวจอนุมัติ<br>ยังขาดการกระจายเวลา จำนวนครั้งเรียกซ้ำ สภาพแวดล้อม และต้นทุน จึงยังใช้กำหนด SLA หรือสรุปประสิทธิภาพใช้งานจริงไม่ได้</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 หัวข้อ 3.4 ตาราง 3.6 และแผนภูมิ 3.3; หน้าเลขพิมพ์ 35–36 -->




---

<!-- _class: d3-table35 -->

## Set1: เวลา จำนวนค่าที่เติม และความเห็นพ้อง

<table class="table35"><thead><tr><th>การตั้งค่าโมเดลตามรายงาน</th><th>เวลาเฉลี่ย/รายการ<br>(วินาที)</th><th>จำนวนค่าที่เติม<br>/75</th><th>เฉลี่ยเห็นพ้อง<br>กับโมเดลอื่น*</th></tr></thead><tbody><tr><td><span class="model-id">groq:qwen/qwen3.8-27b</span></td><td>0.63</td><td>26</td><td>64.0</td></tr><tr><td><span class="model-id">groq:openai/gpt-oss-20b</span></td><td>1.03</td><td>27</td><td>65.9</td></tr><tr><td><span class="model-id">groq:openai/gpt-oss-120b</span></td><td>1.57</td><td>22</td><td>65.7</td></tr><tr><td><span class="model-id">ollama-cloud:gemma4:31b</span></td><td>1.80</td><td>26</td><td>66.0</td></tr><tr><td><span class="model-id">gemini:gemini-3.8-flash</span></td><td>3.58</td><td>23</td><td>65.9</td></tr><tr><td><span class="model-id">ollama-cloud:deepseek-v4.1-flash</span></td><td>5.48</td><td>27</td><td>64.6</td></tr><tr><td><span class="model-id">ollama-cloud:kimi-k3</span></td><td>8.68</td><td>26</td><td>66.3</td></tr></tbody></table>
<div class="agreement-warning">* ฐาน 75 กรณีตามรายงาน ไม่ใช่ร้อยละ ยังไม่มีสูตรและวิธีจัดการค่าว่างให้ตรวจซ้ำ จึงไม่ใช้จัดอันดับความถูกต้อง<br>จำนวนค่าที่เติมไม่ใช่จำนวนค่าที่ถูกต้อง อนุมัติ หรือส่งออก</div>
<div class="timing-comparison"><span class="model-id">groq:qwen/qwen3.8-27b</span> และ <span class="model-id">ollama-cloud:kimi-k3</span> ได้ exact match เท่ากันที่ 66/75 (88.00%) แต่เวลาเฉลี่ยในรอบทดลองต่างกันที่ 0.63 และ 8.68 วินาที</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 ตาราง 3.6; หน้าเลขพิมพ์ 35; ฉบับย่อนี้ไม่รวมแถว Jev ในตารางเปรียบเทียบ -->




---

<!-- _class: d3-full-models -->

## ผลรายโมเดลและจำนวนกรณีที่ไม่ตรง

| Provider และชื่อรุ่นตามรายงาน | ตรง /75 | ค่าผิด | เติมเกิน | ตกหล่น | ผิดรวม |
|---|---:|---:|---:|---:|---:|
| groq:openai/gpt-oss-120b | 71 | 1 | 2 | 1 | 4 |
| groq:openai/gpt-oss-20b | 67 | 2 | 6 | 0 | 8 |
| ollama-cloud:kimi-k3 | 66 | 2 | 6 | 1 | 9 |
| groq:qwen/qwen3.8-27b | 66 | 2 | 6 | 1 | 9 |
| gemini:gemini-3.8-flash | 65 | 2 | 5 | 3 | 10 |
| ollama-cloud:gemma4:31b | 64 | 4 | 6 | 1 | 11 |
| ollama-cloud:deepseek-v4.1-flash | 60 | 5 | 8 | 2 | 15 |

<div class="caption">ชื่อรุ่นตามรายงานยังต้องมี prompt ฉบับเต็มและ log ทดลองเพื่อทำซ้ำ<br>จำนวนตรง + ค่าผิด + เติมเกิน + ตกหล่น = 75 กรณีงานวิจัย–ฟิลด์</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 ตาราง 3.3; หน้าเลขพิมพ์ 32; ชื่อการตั้งค่าถอดตามรายงาน ยังไม่ได้ยืนยันกับผู้ให้บริการ -->




---

## ผลรายฟิลด์และประเด็นที่ต้องปรับปรุง

| ข้อสังเกตในกลุ่มโมเดลข้อความ | แนวทางปรับปรุง |
|---|---|
| Platform ตรง 10–12/15 | ทบทวนนิยาม คำศัพท์ควบคุม และ mapping |
| Vaccine-Sub ตรง 10–15/15 | ตรวจความแตกต่างของชื่อและความหมาย |
| เติมเกิน 2–8 กรณีต่อโมเดล | ตรวจหลักฐานก่อนรับค่าที่เสนอ |
| CellbasedType ตรง 15/15 ทุกโมเดล | แยกกรณีมีข้อมูลกับค่าว่างก่อนตีความ |

> ปรับนิยามฟิลด์ กฎ mapping และ prompt จากประเภทข้อผิดพลาด

<div class="caption">คะแนนเต็มในบางฟิลด์ยังไม่ยืนยันว่าการสกัดสมบูรณ์ เพราะไม่มีการแจกแจงค่าว่างรายฟิลด์</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 ตาราง 3.4 และ 3.7; หน้าเลขพิมพ์ 34 และ 36–37 -->





---

<!-- _class: d3-fields-complete -->

## ผลตรงชุดอ้างอิงรายฟิลด์ของโมเดลข้อความ

<table class="full-field-table"><thead><tr><th>การตั้งค่าโมเดลตามรายงาน</th><th>Vaccine-Sub</th><th>Platform</th><th>RouteType</th><th>Technology<br>Production</th><th>CellbasedType</th></tr></thead><tbody><tr><td><span class="model-id">groq:openai/gpt-oss-120b</span></td><td>15</td><td>12</td><td>14</td><td>15</td><td>15</td></tr><tr><td><span class="model-id">groq:openai/gpt-oss-20b</span></td><td>12</td><td>12</td><td>14</td><td>14</td><td>15</td></tr><tr><td><span class="model-id">ollama-cloud:kimi-k3</span></td><td>11</td><td>12</td><td>14</td><td>14</td><td>15</td></tr><tr><td><span class="model-id">groq:qwen/qwen3.8-27b</span></td><td>14</td><td>10</td><td>14</td><td>13</td><td>15</td></tr><tr><td><span class="model-id">gemini:gemini-3.8-flash</span></td><td>13</td><td>11</td><td>12</td><td>14</td><td>15</td></tr><tr><td><span class="model-id">ollama-cloud:gemma4:31b</span></td><td>11</td><td>12</td><td>12</td><td>14</td><td>15</td></tr><tr><td><span class="model-id">ollama-cloud:deepseek-v4.1-flash</span></td><td>10</td><td>10</td><td>11</td><td>14</td><td>15</td></tr></tbody></table>
<div class="caption">แต่ละฟิลด์มีฐาน 15 งานวิจัย คะแนนรวมกรณีค่าว่าง จึงยังไม่ใช้แทนความสามารถสกัดเฉพาะกรณีมีข้อมูล<br>Jev ใช้ป้ายกำกับปิดและไม่มี quote จึงไม่รวมในตารางเปรียบเทียบโมเดลข้อความนี้</div>

<!-- แหล่งข้อมูล: main(3).pdf รายงานความก้าวหน้าเชิงเทคนิค วันที่ 29 ตุลาคม 2569 ตาราง 3.4; หน้าเลขพิมพ์ 34 -->




---

<!-- _class: divider -->

## 06
## สถานะปัจจุบัน ข้อจำกัด และแผนพัฒนาระยะถัดไป

Current status, limitations and next steps





---

<!-- _class: d6-status -->

## สถานะปัจจุบันและงานที่ต้องยืนยัน

### มีต้นแบบข้อมูลทางคลินิกและผลประเมินนำร่อง

- ประเมินแล้ว 15 งานวิจัย ยังต้องเพิ่มผลรายกรณีและแยกกรณีไม่มีข้อมูล
- ต้องทดสอบครบวงจร ตรวจสิทธิ์เข้าถึง และทดสอบโดยผู้ใช้จริง
- ต้องรับรองโครงสร้างข้อมูลและการเทียบช่องข้อมูลร่วมกับผู้ดูแล VIMS
- ต้องวัดผลของวงจรตรวจสอบโดยผู้เชี่ยวชาญก่อนและหลังปรับปรุง
- งานระยะถัดไปยังรวมพรีคลินิก การขึ้นทะเบียน และผลิตภัณฑ์วัคซีน

> เป้าหมายถัดไปคือยืนยันคุณภาพข้อมูลและความพร้อมใช้งานจริง

<!-- แหล่งข้อมูล: main(3).pdf วันที่ 29 ตุลาคม 2569 หัวข้อ 4.1–4.4 หน้าเลขพิมพ์ 39–41; D5 หน้า 39 -->

---

<!-- _class: d6-plan -->

## แผนพัฒนาระยะถัดไปและผลที่คาดหวัง

| งานระยะถัดไป | ผลลัพธ์ที่ต้องได้ |
|---|---|
| ยืนยันโครงสร้างและการเทียบช่องข้อมูลกับ VIMS | มาตรฐานข้อมูลและกติกาหลักฐานที่รับรองร่วมกัน |
| ขยายชุดคำตอบอ้างอิงให้ครอบคลุม MMR/VZ/FLU | ชุดพัฒนาและชุดประเมินที่แยกกัน พร้อมตรึงคำตอบอ้างอิง |
| ประเมินรายช่องข้อมูล แยกกรณีมีข้อมูลและไม่มีข้อมูล | ผลความถูกต้อง เวลา ต้นทุน และภาระตรวจทาน |
| ทดสอบครบวงจรและวงจรตรวจสอบโดยผู้เชี่ยวชาญ | ผลก่อนและหลังปรับปรุงระบบจากการตรวจของผู้เชี่ยวชาญ |
| ขยายหมวดข้อมูล เชื่อมต่อ และทดสอบโดยผู้ใช้จริง | ผลทดสอบและการยอมรับก่อนติดตั้งและส่งมอบ |

<div class="caption">ทบทวนแผนและงวดส่งมอบกับผู้กำกับดูแลสัญญา<br>กำหนดผู้รับผิดชอบ วันครบกำหนด และเกณฑ์ผ่านร่วมกัน</div>

<!-- แหล่งข้อมูล: main(3).pdf วันที่ 29 ตุลาคม 2569 บทสรุปผู้บริหารและหัวข้อ 4.4 หน้าเลขพิมพ์ 4 และ 40–41; D5 หน้า 40 -->

---

<!-- _class: d6-sequence -->

## ลำดับงานและหลักฐานก่อนขยายการใช้งาน

| ลำดับ | งาน | หลักฐานสำหรับพิจารณาความพร้อม |
|---|---|---|
| 1 | จัดระบบทดสอบภายในและทดสอบครบวงจร | ผลทดสอบสิทธิ์ การนำเข้า ตรวจทาน และส่งออกข้อมูล |
| 2 | รับรองมาตรฐานข้อมูลร่วมกับ VIMS | นิยามช่องข้อมูล ตารางเทียบข้อมูล และเกณฑ์ผ่าน |
| 3 | ขยายชุดคำตอบอ้างอิงและประเมินโมเดล | ผลรายกรณี เวลา และต้นทุนการประมวลผล |
| 4 | ประเมินวงจรตรวจสอบโดยผู้เชี่ยวชาญ | อัตรารับและแก้ไขข้อมูล เวลาตรวจ และผลก่อน–หลัง |
| 5 | ขยายหมวดข้อมูล เชื่อมต่อ และทดสอบโดยผู้ใช้จริง | ผลทดสอบ การยอมรับของผู้ใช้ คู่มือ และแผนกู้คืน |

<div class="caption">กำหนดวันส่งมอบ ผู้รับผิดชอบ และเกณฑ์ผ่านร่วมกับเจ้าของข้อมูลและผู้กำกับดูแลสัญญา</div>

<!-- แหล่งข้อมูล: main(3).pdf วันที่ 29 ตุลาคม 2569 หัวข้อ 4.4; แนวทางระบบทดสอบภายใน คู่มือ และแผนกู้คืนจาก OperationalReport 13 ตุลาคม 2569 หน้า PDF 9–10; D5 หน้า 41 -->

---

<!-- _class: d6-progress -->

## สรุปความก้าวหน้าและงานก่อนส่งมอบ

<div class="d6-progress-status">สถานะปัจจุบัน: มีต้นแบบทางคลินิกและผลประเมินนำร่อง</div>

| งานหลัก | หลักฐานความก้าวหน้าที่มีแล้ว | งานที่เหลือก่อนใช้งานจริง |
|---|---|---|
| มาตรฐานข้อมูล | พจนานุกรมข้อมูล 4 หมวด | รับรองนิยามและเทียบช่องข้อมูลกับ VIMS |
| ระบบต้นแบบ | องค์ประกอบนำเข้า ตรวจทาน และส่งออกข้อมูลคลินิก | ทดสอบครบวงจร ตรวจสิทธิ์ และให้ผู้ใช้จริงทดสอบ |
| ประเมิน AI | ผลนำร่อง 15 งานวิจัย รวม 75 กรณีต่อโมเดล | ขยายชุดคำตอบอ้างอิง ตรวจซ้ำ และวัดภาระตรวจทาน |
| ครอบคลุมขอบเขตงาน | ผลนำร่องเฉพาะข้อมูลทางคลินิก | เพิ่มพรีคลินิก การขึ้นทะเบียน ผลิตภัณฑ์ และเชื่อมต่อ VIMS |

<div class="d6-decision"><b>ประเด็นหารือ:</b> ผู้รับรองมาตรฐานข้อมูล เกณฑ์ผ่าน และกำหนดส่งมอบรอบถัดไป</div>

<!-- แหล่งข้อมูล: main(3).pdf วันที่ 29 ตุลาคม 2569 บทสรุปผู้บริหาร หัวข้อ 2.4–2.7 และ 4.1–4.4; แสดงสถานะตามหลักฐาน มิใช่ผลตรวจรับงวดสัญญา; ไม่กำหนดเปอร์เซ็นต์ความก้าวหน้าเพราะยังไม่มีน้ำหนักงานและผลตรวจรับที่รับรอง; D5 หน้า 42 -->
