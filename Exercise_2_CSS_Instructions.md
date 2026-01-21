# แบบฝึกหัดที่ 2: CSS (Exercise 2: CSS)

## ภาพรวม (Overview)
สร้างเว็บเพจแสดงข้อมูล "เกี่ยวกับคณะ" โดยใช้ HTML และ CSS

---

## ส่วนที่ 1: Structuring HTML

### โครงสร้างโฟลเดอร์
```
CS369_Lab2_Part1/
├── index.html
└── about.html
```

### ข้อกำหนด index.html

#### 1. Page Title
- ตั้งชื่อ: `CS369-Lab2-CSS`

#### 2. Headings และ Sub-headings (เรียงตามลำดับ)
เนื้อหาคัดลอกจาก: https://cs.sci.tu.ac.th/about-faculty-th-2/

| ลำดับ | Heading | Tag | Class/ID |
|-------|---------|-----|----------|
| a | เกี่ยวกับ คณะวิทยาศาสตร์และเทคโนโลยี มหาวิทยาลัยธรรมศาสตร์ | `<h1>` | `class="heading"`, `id="organization"` |
| b | 2529-2538 | `<h2>` | `class="year-range"` |
| b.i | ก่อตั้งสร้างฐาน | `<h3>` | - |
| c | 2539-2548 | `<h2>` | `class="year-range"` |
| c.i | ขยายสู่ระดับบัณฑิตศึกษา | `<h3>` | - |
| d | 2549-2558 | `<h2>` | `class="year-range"` |
| d.i | พัฒนาเป็นมหาวิทยาลัยวิจัย | `<h3>` | - |
| e | 2559-ปัจจุบัน | `<h2>` | `class="year-range"` |
| e.i | ผลิตผู้นำรุ่นใหม่ให้สังคมไทย | `<h3>` | - |
| f | เว็บไซต์ที่เกี่ยวข้อง | `<h2>` | - |

#### 3. ส่วน "เว็บไซต์ที่เกี่ยวข้อง" (ใช้ List tag `<ul>` หรือ `<ol>`)
```html
<ul>
  <li><a href="https://cs.sci.tu.ac.th/about-faculty-th-2/">ที่มา https://cs.sci.tu.ac.th/about-faculty-th-2/</a></li>
  <li><a href="https://cs.sci.tu.ac.th/">คลิกเพื่อไปสู่เว็บไซต์สาขาวิชาวิทยาการคอมพิวเตอร์ คณะวิทยาศาสตร์และเทคโนโลยี มหาวิทยาลัยธรรมศาสตร์</a></li>
  <li><a href="https://sci.tu.ac.th/">คลิกเพื่อไปสู่เว็บไซต์คณะวิทยาศาสตร์และเทคโนโลยี มหาวิทยาลัยธรรมศาสตร์</a></li>
  <li><a href="https://tu.ac.th/">คลิกเพื่อไปสู่เว็บไซต์มหาวิทยาลัยธรรมศาสตร์</a></li>
</ul>
```

#### 4. ส่วนท้าย index.html
- ใช้ `<hr>` คั่น
- สร้างลิงก์ "สมาชิกภายในกลุ่ม" ไปยัง `about.html`

#### 5. เนื้อหาอื่นๆ
- ใส่ใน tag `<p>`

### ข้อกำหนด about.html
- Heading: "สมาชิกภายในกลุ่ม"
- ตาราง `<table>` แสดง 3 คอลัมน์:
  1. เลขทะเบียน
  2. ชื่อ-นามสกุล
  3. ชื่อเล่น
- ตารางต้องมีขอบ (border)

---

## ส่วนที่ 2: Basic CSS (Internal CSS)

### โครงสร้างโฟลเดอร์
```
CS369_Lab2_Part2/
├── index.html (copy จาก Part1 + เพิ่ม CSS)
└── about.html (copy จาก Part1)
```

### CSS Styling (ใส่ใน `<head>` เท่านั้น)

```css
/* 1. id="organization" */
#organization {
  background-color: bisque;
  text-align: center;
  color: green;
}

/* 2. class="year-range" */
.year-range {
  border-left-width: 6px;
  border-left-color: red;
  border-left-style: solid;
}

/* 3. ตัวอักษรตัวแรกใน <p> */
p::first-letter {
  font-size: 35px;
  color: blue;
}

/* 4. hover บน <p> */
p:hover {
  font-size: 26px;
  color: red;
}

/* 5. class="heading" - ใช้ !important เพื่อ override */
.heading {
  color: #0D3D56 !important;
}

/* 6. link ที่ยังไม่เคยถูกเยี่ยม */
a:link {
  color: blueviolet;
  text-decoration-style: dotted;
  text-decoration-color: red;
}

/* 7. link ที่ถูก visited แล้ว */
a:visited {
  color: gray;
  text-decoration-style: dotted;
  text-decoration-color: blue;
}

/* 8. link ภายใต้ <li> */
li a {
  background-color: aquamarine;
}

/* 9. indent สำหรับ <p> */
p {
  text-indent: 40px;
}
```

### ข้อ 10: Inline Style สำหรับลิงก์ "สมาชิกภายในกลุ่ม"
```html
<a href="about.html" style="text-align: center; display: block;">สมาชิกภายในกลุ่ม</a>
```

---

## ส่วนที่ 3: Basic CSS -2 (External CSS)

### โครงสร้างโฟลเดอร์
```
CS369_Lab2_Part3/
├── index.html (ไม่มี <style> tag)
├── about.html
└── app.css (CSS ทั้งหมดย้ายมาที่นี่)
```

### การลิงก์ CSS ใน index.html
```html
<head>
  <link rel="stylesheet" href="app.css">
</head>
```

**หมายเหตุ:** ลบ `<style>` tag ออกจาก `<head>` ทั้งหมด

---

## ส่วนที่ 4: Basic CSS – 3 (Optional - Extra Marks)

### งาน
1. วิเคราะห์ข้อด้อยของหน้าเว็บเพจอย่างน้อย 2 ข้อ
2. เสนอแนวทางปรับปรุง
3. ปรับปรุงเฉพาะไฟล์ `app.css`
4. อธิบายการปรับปรุงที่ทำ

### ตัวอย่างข้อด้อยที่อาจพบ
- ไม่มี responsive design
- ขาด spacing/margin ที่เหมาะสม
- font ไม่สวยงาม
- ขาด visual hierarchy
- สีไม่ harmonize กัน

---

## โครงสร้างไฟล์ส่งงานทั้งหมด
```
LabXX_GroupYY/
├── CS369_Lab2_Part1/
│   ├── index.html
│   └── about.html
├── CS369_Lab2_Part2/
│   ├── index.html
│   └── about.html
├── CS369_Lab2_Part3/
│   ├── index.html
│   ├── about.html
│   └── app.css
└── answers.pdf
```

---

## แหล่งข้อมูลเนื้อหา
- URL หลัก: https://cs.sci.tu.ac.th/about-faculty-th-2/
- ให้ดึงเนื้อหาจากเว็บไซต์นี้สำหรับแต่ละ heading/sub-heading
