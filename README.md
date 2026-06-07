# ระบบบ้านลมสวนสัตว์สไลเดอร์ - GitHub Pages Package

ชุดไฟล์นี้เตรียมไว้สำหรับนำขึ้น GitHub Pages / Static Hosting

## ไฟล์ที่ต้องอัปโหลดขึ้น GitHub

1. `index.html`  
   ไฟล์หน้าเว็บหลักของระบบ ใช้งานได้กับ GitHub Pages โดยเชื่อมต่อฐานข้อมูลผ่าน Google Apps Script Web App URL ที่กำหนดไว้ในตัวแปร `CONFIG_WEB_APP_URL`

2. `.nojekyll`  
   ไฟล์เปล่าสำหรับป้องกัน GitHub Pages ประมวลผลแบบ Jekyll ช่วยให้ไฟล์ static ทำงานตรงตามโครงสร้าง

3. `README.md`  
   คู่มือสั้นสำหรับผู้ดูแล repository ไม่จำเป็นต่อการทำงานของระบบ แต่แนะนำให้อัปโหลดไว้

## ไฟล์ที่ไม่ต้องอัปโหลดขึ้น GitHub Pages

- `Code.gs`  
  ใช้ใน Google Apps Script เท่านั้น ไม่ต้องนำขึ้น GitHub Pages เว้นแต่ต้องการเก็บเป็น source code สำรองใน repository

## วิธีอัปโหลดขึ้น GitHub Pages

1. สร้าง repository ใหม่ใน GitHub
2. อัปโหลด `index.html`, `.nojekyll`, `README.md`
3. ไปที่ Settings > Pages
4. เลือก Branch: `main` และ Folder: `/root`
5. กด Save
6. รอ GitHub สร้าง URL สำหรับเข้าใช้งาน

## จุดที่ต้องตรวจสอบก่อนใช้งานจริง

เปิดไฟล์ `index.html` แล้วตรวจสอบบรรทัดนี้:

```js
const CONFIG_WEB_APP_URL = 'https://script.google.com/macros/s/AKfycbz32DG_GLJ_3ywfXmENlUpa--Pp0mJcnnk7cFGc5uMSITdS62KwZYfqmNWqIe_Vs1Gh/exec';
```

ต้องเป็น URL Web App ของ Google Apps Script ที่ deploy แล้ว และต้องลงท้ายด้วย `/exec`

## การตั้งค่า Google Apps Script

Deploy Web App โดยใช้ค่า:

- Execute as: `Me`
- Who has access: `Anyone`

หากเชื่อมต่อไม่ได้ ให้ตรวจสอบว่า URL เป็น `/exec` ไม่ใช่ `/dev` และสิทธิ์ Deploy เป็น `Anyone`
