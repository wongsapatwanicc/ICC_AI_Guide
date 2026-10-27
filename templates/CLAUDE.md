# CLAUDE.md

<!-- คัดลอกไฟล์นี้ไปไว้ที่ root ของโปรเจกต์ แล้วแก้ส่วนที่อยู่ใน <...> ให้ตรงงาน -->

## Project

- ชื่อโปรเจกต์: <ชื่อโปรเจกต์>
- Tech stack: <เช่น Go 1.23, React 18 + TypeScript, PostgreSQL 16>
- คำสั่งที่ต้องผ่านก่อน commit: <เช่น go test ./..., pnpm typecheck, pnpm test>

## Documentation rules

ก่อนเริ่มงาน:
- อ่าน docs/STATUS.md, docs/GLOSSARY.md และไฟล์ล่าสุดใน docs/sessions/
- ถ้างานเกี่ยวกับฟีเจอร์ไหน อ่าน docs/specs/ และ docs/adr/ ที่เกี่ยวข้องก่อน

ระหว่างทำ:
- ตัดสินใจเรื่องที่ย้อนกลับยาก → เขียน ADR ใน docs/adr/
- เจอศัพท์ใหม่ → เพิ่มใน docs/GLOSSARY.md
- เอกสารไม่ตรงกับโค้ด → แก้เอกสารให้ตรง และบอกผม

จบงานทุกครั้ง (ก่อน commit):
- สร้าง docs/sessions/YYYY-MM-DD-<หัวข้อ>.md ตาม docs/templates/session.md
- อัปเดต docs/STATUS.md
- ใช้ [[wikilink]] ลิงก์ไป ADR, spec และศัพท์ใน GLOSSARY

รูปแบบ:
- เนื้อหาภาษาไทย ชื่อไฟล์ภาษาอังกฤษตัวเล็กคั่นด้วย -
- ห้ามลบบันทึกเก่า ถ้าข้อมูลเปลี่ยนให้แก้พร้อมระบุวันที่
- ห้ามใส่ secret หรือข้อมูลลูกค้าจริงในเอกสาร

## Working rules

- ทำงานบน branch เสมอ ห้าม commit หรือ push เข้า main ตรง ๆ
- แก้เฉพาะไฟล์ที่เกี่ยวกับ ticket ปัจจุบัน ห้ามเพิ่ม dependency ใหม่โดยไม่ถามก่อน
- เขียน test ที่ fail ก่อนเขียนโค้ด ห้ามปิดหรือแก้ test เพื่อให้ผ่าน
- ห้ามรันคำสั่งที่ย้อนไม่ได้ (push --force, rm -rf, DROP TABLE) โดยไม่อธิบายและรอผมยืนยัน
- หยุดก่อน commit แล้วสรุป diff, สิ่งที่ยังไม่ได้ทำ และความเสี่ยง
