🍺 Beer Store Project Checklist & Setup
ไฟล์นี้คือ Roadmap สำหรับการเริ่มสร้างจาก Scratch ด้วยตัวเอง

1. 📂 Folder Structure (The "SoC" Map)
สร้างโครงสร้างนี้ใน VS Code ของคุณ (ห้ามรวมไฟล์กันเด็ดขาด เพื่อฝึกความเป็นมืออาชีพ)

Plaintext

beer-store-system/
├── backend/
│   ├── src/
│   │   ├── config/          # การตั้งค่าต่างๆ (Database, Cloudinary)
│   │   ├── models/          # โครงสร้าง MongoDB (Mongoose Schema)
│   │   ├── controllers/     # Logic การทำงานของ API
│   │   ├── routes/          # เส้นทางของ API (Endpoints)
│   │   ├── middleware/      # ตัวกรองก่อนเข้า Controller (Auth, Error Handler)
│   │   └── server.js        # จุดเริ่มต้นรันระบบ
│   ├── .env                 # เก็บค่าความลับ (API Keys)
│   └── package.json
└── frontend/                # (เดี๋ยวค่อยสร้างตอนทำ Dashboard)

2. 📦 Installation Commands
รันคำสั่งเหล่านี้ใน Terminal ของโฟลเดอร์ backend

A. ตัวหลัก (Production)
Bash

npm install express mongoose dotenv cors helmet morgan
express: ทำ Web Server

mongoose: คุยกับ MongoDB

dotenv: อ่านไฟล์ .env

cors: ยอมให้ Frontend คุยกับ Backend

helmet: ป้องกันช่องโหว่ HTTP เบื้องต้น (Security)

morgan: แสดง Log ใน Terminal ว่ามีใครเรียก API อะไรบ้าง

B. สำหรับ AI Agent (ติดตั้งรอไว้เลย)
Bash

npm install langchain @langchain/openai
C. สำหรับจัดการไฟล์ & ข้อมูล
Bash

npm install multer cloudinary papaparse
multer: รับไฟล์รูปภาพ/CSV จาก Frontend

cloudinary: อัปโหลดรูปขึ้น Cloud

papaparse: แปลง CSV จาก Ocha เป็น JSON

D. สำหรับการพัฒนา (Dev Dependencies)
Bash

npm install -D nodemon

🎯 3. Your Challenges (To-Do List)
ลองทำให้ผ่านทีละข้อโดยเปิด Google ควบคู่ไปได้ครับ:

DB Connect: เขียน src/config/db.js ให้เชื่อมต่อ MongoDB Atlas ให้สำเร็จ

Schema Design: สร้าง src/models/Beer.js ให้มีฟิลด์ name, price, stock และลองเพิ่ม abv (แอลกอฮอล์) เอง

The API: สร้าง Routes และ Controllers ให้รองรับ:

GET /api/beers (แสดงเบียร์ทั้งหมด)

POST /api/beers (เพิ่มเบียร์ใหม่)

PATCH /api/beers/:id (อัปเดตสต็อก - ต้องลองเขียนเอง)

DELETE /api/beers/:id (ลบเบียร์ - ต้องลองเขียนเอง)