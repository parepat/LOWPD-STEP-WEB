# LOW PD / STEP Q4/2569 — GitHub Pages Bridge V3

ชุดนี้ใช้เมื่อต้องการให้หน้าเว็บเปิดจาก GitHub Pages แต่ข้อมูลยังมาจาก Google Sheet / Apps Script

## 1. Apps Script Backend
เปิดโฟลเดอร์ `apps-script-backend`

นำไฟล์:
- `Code.gs`
- `index.html`
- `appsscript.json`

ไปแทนใน Apps Script แล้ว Deploy Web App ใหม่

## 2. ตั้งค่า GitHub index.html
เปิด `index.html` ที่ root แล้วหา:

```js
const APPS_SCRIPT_API_URL =
  'PASTE_YOUR_APPS_SCRIPT_EXEC_URL_HERE';
```

เปลี่ยนเป็น URL Apps Script ที่ลงท้าย `/exec`

ตัวอย่าง:

```js
const APPS_SCRIPT_API_URL =
  'https://script.google.com/macros/s/AKfycbXXXXXXXX/exec';
```

## 3. GitHub Pages
- Push ไฟล์ root ไป GitHub
- Settings > Pages
- Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`

## หมายเหตุเรื่องความปลอดภัย
ถ้า Rate / เงื่อนไขเป็นข้อมูลใช้ภายในธนาคาร:
- แนะนำ Private Repository
- ไม่แนะนำเปิด GitHub Pages แบบ Public
- ทางที่ปลอดภัยกว่า คือใช้ Apps Script `/exec` เป็นหน้าใช้งานจริง แล้วใช้ GitHub เป็น Source Control / Backup

## Data source
- MLR: `ตารางผ่อนชำระ!C2`
- Config: `WEB_CONFIG`
- Rate / Spread / Tier: `WEB_RATE_TABLE`
GitHub Pages deployment
