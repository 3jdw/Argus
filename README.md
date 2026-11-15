# Argus

เว็บสแกนไฟล์ ลิงก์ IP และแฮช เพื่อหาสัญญาณมัลแวร์ ทำงานทั้งหมดในเบราว์เซอร์ของผู้ใช้ ไฟล์ไม่ถูกอัปโหลดไปไหน
Static malware / link / IP / hash scanner that runs entirely in the browser. Nothing is uploaded.

- เว็บเป็นไฟล์เดียว: `index.html` (ไม่มีสคริปต์หรือฟอนต์จากภายนอก)
- `_headers` คือ header ความปลอดภัยสำหรับ Cloudflare Pages / Netlify (GitHub Pages ไม่อ่านไฟล์นี้ จึงใช้ CSP ที่ฝังในหน้าเว็บแทน)
- ถ้าแก้ `index.html` ค่าแฮชของสคริปต์ใน CSP จะไม่ตรงและหน้าเว็บจะถูกบล็อก

## ข้อจำกัด / Limits
การวิเคราะห์เป็นแบบสถิต ไม่ได้รันไฟล์ในแซนด์บ็อกซ์ และฐานลายเซ็นมีขนาดเล็กกว่าบริการคลาวด์มาก ผล "ไม่พบ" ไม่ได้แปลว่าปลอดภัย
Analysis is static; the signature set is small. "Nothing found" does not mean "safe". Not a replacement for antivirus.
