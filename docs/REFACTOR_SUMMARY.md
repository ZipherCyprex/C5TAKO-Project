# 📋 Docs Refactoring Summary

## 🎯 วัตถุประสงค์
ปรับปรุง UX/UI ของเอกสารให้อ่านง่าย หาข้อมูลเร็ว และใช้สมองน้อยที่สุด

---

## ✅ การเปลี่ยนแปลงที่ทำ

### **1. เปลี่ยนตารางเป็น Card Components**

#### ❌ ก่อน (ใช้ตาราง)
```markdown
| เมนูบนเครื่อง | ใช้ทำอะไร | คู่มือ |
| --- | --- | --- |
| `WIFI` | สแกน ตรวจสอบ และทดสอบ Wi‑Fi | [เปิดคู่มือ](/features/wifi-overview) |
```

**ปัญหา:**
- ต้องอ่าน 3 คอลัมน์ก่อนตัดสินใจ
- ลิงก์เล็ก ยากต่อการคลิก
- ดูเรียบไม่โดดเด่น

#### ✅ หลัง (ใช้ CardGroup)
```markdown
<CardGroup cols={2}>
  <Card title="📶 WIFI" icon="wifi" href="/features/wifi-overview">
    ค้นหา ตรวจสอบ และทดสอบเครือข่าย Wi‑Fi
  </Card>
</CardGroup>
```

**ข้อดี:**
- 👁️ มองเห็นชัดเจนทันที
- 🖱️ คลิกได้ทั้งการ์ด
- 🎨 ใช้ emoji/icon ช่วยจำ

---

### **2. ย้าย Settings ที่ใช้บ่อยออกจาก Accordion**

#### ❌ ก่อน
```markdown
<Accordion title="Brightness — ความสว่าง" icon="sun">
  เปิด SETTINGS → Display UI → Brightness แล้วเลือก 10%, 25%, 50%, 75% หรือ 100%
</Accordion>
```

**ปัญหา:** ต้องคลิกเปิด Accordion ถึงจะเห็น

#### ✅ หลัง
```markdown
### ⭐ ตั้งค่ายอดนิยม

#### ความสว่าง (Brightness)
เส้นทาง: `SETTINGS → Display UI → Brightness`

เลือกได้ 5 ระดับ: **10%** | **25%** | **50%** | **75%** | **100%**

💡 **แนะนำ:** เริ่มที่ 25–50% เพื่อประหยัดแบตเตอรี่
```

**ข้อดี:** เห็นข้อมูลทันทีไม่ต้องคลิก

---

### **3. Troubleshooting ใช้ Visual Cards แทนตาราง**

#### ❌ ก่อน
```markdown
| อาการ | ไปที่ |
| --- | --- |
| เครื่องเปิดไม่ติด | [เครื่องเปิดไม่ติด...](#...) |
```

#### ✅ หลัง
```markdown
## 🆘 เลือกปัญหาของคุณ

<CardGroup cols={2}>
  <Card title="⚠️ เครื่องเปิดไม่ติด" icon="power-off" href="#...">
    หน้าจอดำ กดปุ่มไม่มีอะไรเกิดขึ้น
  </Card>
</CardGroup>
```

**ข้อดี:** ค้นหาปัญหาได้เร็วด้วย icon และคำอธิบาย

---

## 📁 ไฟล์ที่แก้ไข

### **ภาษาไทย:**
- ✅ `docs/index.mdx`
- ✅ `docs/features/menu-overview.mdx`
- ✅ `docs/features/wifi-overview.mdx`
- ✅ `docs/features/wifi-attack.mdx`
- ✅ `docs/features/wifi-sniffer.mdx`
- ✅ `docs/features/bluetooth-overview.mdx`
- ✅ `docs/features/settings.mdx`
- ✅ `docs/help/troubleshooting.mdx`

### **English:**
- ✅ `docs/en/index.mdx`
- ✅ `docs/en/features/menu-overview.mdx`
- ✅ `docs/en/features/wifi-overview.mdx`
- ✅ `docs/en/features/wifi-attack.mdx`
- ✅ `docs/en/features/bluetooth-overview.mdx`
- ✅ `docs/en/features/settings.mdx`
- ✅ `docs/en/help/troubleshooting.mdx`

---

## 📊 ผลลัพธ์ที่คาดหวัง

### ก่อน
```
😕 อ่านตาราง → หาลิงก์ → เล็งคลิก → ไปหน้าถัดไป
⏱️ เวลา: 5-7 วินาที
```

### หลัง
```
😊 เห็น Card → คลิกเลย → ไปหน้าถัดไป
⏱️ เวลา: 1-2 วินาที
```

---

## 🎨 หลักการที่ใช้

1. **Visual Hierarchy** - ใช้ Card, Icon, Emoji ให้ข้อมูลโดดเด่น
2. **Click Target Size** - Card ใหญ่กว่าลิงก์ คลิกง่าย
3. **Cognitive Load** - ลดการอ่านและคิด แสดงแค่ที่จำเป็น
4. **Progressive Disclosure** - ข้อมูลสำคัญเห็นก่อน ข้อมูลเพิ่มเติมซ่อนใน Accordion
5. **Scan-ability** - ใช้ icon/emoji ช่วยให้สแกนหาข้อมูลเร็ว

---

## 💡 Next Steps (ถ้าต้องการปรับเพิ่ม)

### Priority 2 (ควรทำต่อ)
- [ ] **Task-based Navigation**: เพิ่มหน้า "ฉันต้องการ..." สำหรับแต่ละฟีเจอร์
  ```markdown
  ## 🚀 ฉันต้องการ...
  
  <CardGroup cols={2}>
    <Card title="ค้นหา Router ใกล้ ๆ" href="#ap">
      ไปที่: WIFI → SCAN → AP → Scan
    </Card>
  </CardGroup>
  ```

- [ ] **ลบหรือปรับ Menu Tree**: ASCII tree ในหน้า menu-overview อาจยังดูซับซ้อนเกินไป
  - พิจารณาเปลี่ยนเป็น Task-based cards แทน
  - หรือใส่ใน Accordion แล้วเปลี่ยนเป็น HTML list ที่อ่านง่ายกว่า

### Priority 3 (Nice to have)
- [ ] เพิ่ม Tags/Categories ใน frontmatter สำหรับ Search
- [ ] ทดสอบ responsive บนหน้าจอมือถือ
- [ ] เพิ่ม Quick Start Guide แบบ Step-by-step interactive

---

## 🔍 ทดสอบ

### วิธีทดสอบ:
1. รัน Mintlify dev server:
   ```bash
   cd docs
   mint dev
   ```

2. เปิดเว็บบราวเซอร์แล้วทดสอบ:
   - คลิก Card ใช้งานได้หรือไม่
   - Card แสดงผลถูกต้องบนหน้าจอขนาดต่าง ๆ
   - Emoji และ Icon แสดงผลครบ

### Checklist:
- [ ] หน้าแรก (index.mdx) แสดง Card แทนตาราง
- [ ] Menu Overview แสดง Card
- [ ] Troubleshooting แสดง Card พร้อม icon ปัญหา
- [ ] Settings แสดง Brightness/Theme ออกจาก Accordion
- [ ] ทุกหน้าใช้งานได้ทั้งไทยและอังกฤษ

---

## 📝 หมายเหตุ

- ไม่ได้แก้เนื้อหา (content) เลย แก้เฉพาะ UI/UX
- Mintlify Components ที่ใช้: `<CardGroup>`, `<Card>`, `<Note>`, `<Tip>`
- ทุกการเปลี่ยนแปลงเป็น backward compatible กับ Mintlify

---

**สร้างเมื่อ:** 2026-08-20  
**ผู้สร้าง:** Kiro AI Assistant  
**วัตถุประสงค์:** ปรับปรุง C5TAKO Docs ให้อ่านง่ายและใช้งานสะดวกขึ้น
