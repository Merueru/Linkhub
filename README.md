# My Web App

เว็บไซต์ minimal พร้อม Admin Panel สำหรับจัดการปุ่มและลิงก์

## โครงสร้างไฟล์

```
my-web-app/
├── index.html      ← หน้าสาธารณะ (อ่านอย่างเดียว)
├── admin.html      ← หลังบ้าน (จัดการปุ่ม/ลิงก์)
├── config.json     ← ข้อมูลปุ่มทั้งหมด (แก้ผ่าน admin)
└── README.md
```

## วิธีใช้งาน

### 1. Fork / Clone repo นี้
```bash
git clone https://github.com/YOUR_USERNAME/my-web-app.git
cd my-web-app
```

### 2. Enable GitHub Pages
- ไปที่ `Settings → Pages`
- Source: `Deploy from branch` → branch `main` → folder `/` (root)
- Save → รอสักครู่ จะได้ URL เช่น `https://YOUR_USERNAME.github.io/my-web-app/`

### 3. แก้ค่าใน index.html
เปิด `index.html` แล้วแก้ 3 บรรทัดนี้:
```js
const GITHUB_USER   = 'YOUR_USERNAME';   // GitHub username ของคุณ
const GITHUB_REPO   = 'YOUR_REPO';       // ชื่อ repo
const GITHUB_BRANCH = 'main';            // branch (ปกติคือ main)
```

### 4. สร้าง GitHub Personal Access Token
- ไปที่ https://github.com/settings/tokens
- `Generate new token (classic)`
- เลือก scope: **`repo`** (ทั้งหมด)
- Copy token ไว้

### 5. เข้าใช้งาน Admin Panel
เปิด `https://YOUR_USERNAME.github.io/my-web-app/admin.html`
- กรอก Username, Repo, Branch, Token
- แก้ไขปุ่มและลิงก์ได้เลย
- กด **"บันทึกและ Push ขึ้น GitHub"**
- GitHub Pages จะ deploy อัตโนมัติ (ใช้เวลา 1-2 นาที)

## ฟีเจอร์ Admin Panel

- ✅ เพิ่ม / ลบ / เรียงลำดับปุ่มด้วยการลาก (drag & drop)
- ✅ เลือกประเภท: ลิงก์เว็บ / เว็บไซต์ / ดาวน์โหลด
- ✅ เลือกสีปุ่ม: ดำ / น้ำเงิน / เขียว / แดง / ขอบ
- ✅ เปิด/ปิดแสดงปุ่ม
- ✅ พรีวิวแบบ real-time
- ✅ บันทึก Token ใน localStorage (ไม่ส่งไปไหน)
- ✅ Push ขึ้น GitHub ผ่าน GitHub API โดยตรง

## ความปลอดภัย

- Token ถูกเก็บใน `localStorage` ของเบราว์เซอร์เครื่องคุณเท่านั้น
- ไม่มี server ไม่มีการส่งข้อมูลไปที่ไหนนอกจาก GitHub API
- แนะนำใช้ Token ที่มีสิทธิ์เฉพาะ `repo` เท่านั้น
