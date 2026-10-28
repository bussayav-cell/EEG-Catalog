# EV Station PluZ Catalog — Entech Energy

เว็บ Catalog สถานีชาร์จ EV (เปิดได้ทั้งมือถือและ iPad) เป็นไฟล์ static ล้วน ขึ้น GitHub Pages ได้ทันที

## 1) ขึ้น GitHub Pages

1. สร้าง repository ใหม่บน GitHub เช่น `ev-catalog` (เลือก Public)
2. อัปโหลดไฟล์ทั้งหมดในโฟลเดอร์นี้ คือ `index.html`, `README.md` และโฟลเดอร์ `img/` ทั้งโฟลเดอร์
   - วิธีอัปโหลด: กด **Add file → Upload files** แล้วลากไฟล์ทั้งหมดใส่ จากนั้นกด **Commit changes**
3. ไปที่ **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main**, โฟลเดอร์ **/ (root)** แล้วกด **Save**
4. รอ 1–2 นาที เว็บจะขึ้นที่ `https://<ชื่อบัญชี>.github.io/ev-catalog/`

## 2) ให้ฟอร์ม "ฝากข้อมูล" ส่งเข้าอีเมล

ตั้งไว้ให้ส่งเข้า **bussaya.v@gmail.com** ผ่าน FormSubmit.co ซึ่งใช้ฟรีและไม่ต้องสมัคร

**ต้องยืนยัน 1 ครั้งก่อนใช้งาน**

1. เปิดเว็บที่ขึ้น GitHub แล้ว ไปที่เมนู **ฝากข้อมูล** กรอกข้อมูลทดสอบแล้วกดส่ง
2. เข้า Gmail จะเจออีเมลจาก FormSubmit หัวข้อ "Action Required: Activate FormSubmit" (ถ้าไม่เจอให้ดูในโฟลเดอร์ Spam)
3. กดปุ่ม **Activate Form**
4. หลังจากนั้น ทุกครั้งที่ลูกค้ากดส่ง จะมีอีเมลเข้ามาเป็นตาราง มีชื่อ ช่องทางติดต่อกลับ ทำเล แพ็กเกจที่สนใจ และรายละเอียด

> ข้อความทดสอบครั้งแรก (ก่อนกดยืนยัน) จะไม่เข้าอีเมล เป็นเรื่องปกติ

### (แนะนำ) ซ่อนอีเมลจากโค้ด

ตอนนี้อีเมลอยู่ในโค้ดของหน้าเว็บ ใครเปิดดู source ก็เห็น วิธีซ่อน:

- หลังกดยืนยันแล้ว FormSubmit จะส่งอีเมลอีกฉบับที่มี **รหัสสุ่ม** (เช่น `a1b2c3d4e5...`) มาให้
- เปิด `index.html` ค้นหาคำว่า `const FORM=` แล้วใส่รหัสนั้นในช่อง `formsubmitId`

```js
const FORM={email:"bussaya.v@gmail.com",formsubmitId:"ใส่รหัสสุ่มตรงนี้",web3formsKey:""};
```

### ทางเลือก: ใช้ Web3Forms แทน

1. เข้า https://web3forms.com ใส่อีเมล bussaya.v@gmail.com เพื่อรับ **Access Key**
2. ใส่ key ในช่อง `web3formsKey` ระบบจะเปลี่ยนไปส่งผ่าน Web3Forms ให้เอง

```js
const FORM={email:"bussaya.v@gmail.com",formsubmitId:"",web3formsKey:"ใส่ Access Key ตรงนี้"};
```

### ถ้าส่งไม่สำเร็จ

ถ้าเน็ตลูกค้าหลุดหรือบริการฟอร์มล่ม หน้าเว็บจะคัดลอกข้อความที่ลูกค้ากรอกให้ แล้วขึ้นปุ่มให้ส่งต่อทาง LINE (https://line.me/ti/p/DlLWG-6fpl) ข้อมูลจึงไม่หาย

## 3) แก้ข้อมูลอื่น ๆ

ทุกอย่างอยู่ใน `index.html` ส่วน `<script>`

| ต้องการแก้ | ค้นหาคำว่า |
|---|---|
| ข้อมูลบริษัท ที่อยู่ เบอร์ | `company:{` |
| ราคาต่อหน่วยและสเปก | `const M={` |
| รายการแพ็กเกจ | `// packages from pttor_28_oct.xlsx` |
| ข้อความหมายเหตุราคา | `priceNote` |
| ลิงก์ LINE | `LINE_URL` |
| พิกัดสถานีจริง | `SITE_LOC` |
