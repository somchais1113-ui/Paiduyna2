PAI.DUY.NA LOCAL ADMIN
======================

เครื่องมือสร้างและเผยแพร่ข่าวสถานะการเดินรถ ใช้ได้ 2 โหมด

โหมดที่ 1  เผยแพร่ทันที (แนะนำ)
--------------------------------
กรอกข่าว แล้วกดปุ่มเดียว ระบบจะเขียนไฟล์ status.json ขึ้น GitHub ให้เอง
ไม่ต้อง Export ไม่ต้อง Commit เอง

ตั้งค่าครั้งแรกครั้งเดียว

1. สร้าง Fine-grained Personal Access Token ที่
   GitHub > Settings > Developer settings > Personal access tokens
   > Fine-grained tokens > Generate new token

   Repository access : Only select repositories > เลือกเฉพาะ Repo ที่ใช้เผยแพร่เว็บ
   Permissions       : Repository permissions > Contents > Read and write
   Expiration        : 90 วัน แล้วต่ออายุใหม่เมื่อครบ

2. เปิด PAI_DUY_NA_Admin.html แล้วเลื่อนลงมาที่หัวข้อ "เผยแพร่ขึ้น GitHub ทันที"
   กรอกเจ้าของ Repository, ชื่อ Repository, Branch, ตำแหน่งไฟล์ และวาง Token

3. กด "ทดสอบการเชื่อมต่อ" ให้ขึ้นข้อความสีเขียวก่อน

การใช้งานประจำวัน

1. เปิดไฟล์นี้
2. กรอกข่าว กด "แสดงตัวอย่าง" เพื่อดูผล
3. กด "เผยแพร่ทันที"
4. รอ GitHub Pages Build ประมาณ 1 ถึง 2 นาที

โหมดที่ 2  Export แล้วอัปเองด้วยมือ
------------------------------------
ใช้เมื่อไม่มี Token หรือ Token หมดอายุ

1. กด "Export status.json"
2. นำไฟล์ไปแทน data/status.json ใน Repository
3. Commit และ Push

ข้อควรระวัง
-----------
- Token เก็บอยู่ในเบราว์เซอร์เครื่องนี้เท่านั้น และเก็บต่อเมื่อติ๊ก "จำ Token" เท่านั้น
- ห้ามใส่ Token ลงในไฟล์ใดก็ตามที่ Commit ขึ้น GitHub
- หากเปิดไฟล์แล้วขึ้นข้อความ Failed to fetch ให้เปิดผ่าน Local Server แทน
  cd ไปที่โฟลเดอร์นี้ แล้วสั่ง  python3 -m http.server 8000
  จากนั้นเปิด  http://localhost:8000/PAI_DUY_NA_Admin.html
- ถ้าเก็บโฟลเดอร์นี้ไว้ใน Repository ให้ตั้งเป็น Private
  และห้ามอยู่ใน Branch ที่ GitHub Pages เผยแพร่
- โฟลเดอร์นี้มีโลโก้อยู่ในตัวแล้ว ย้ายไปไว้ที่ไหนก็ทำงานได้ครบ
