# Argus

เว็บสแกนไฟล์ ลิงก์ IP และแฮช เพื่อหาสัญญาณมัลแวร์ ทำงานทั้งหมดในเบราว์เซอร์ของผู้ใช้ ไฟล์ไม่ถูกอัปโหลดไปไหน
Static malware / link / IP / hash scanner that runs entirely in the browser. Nothing is uploaded.

- เว็บเป็นไฟล์เดียว: `index.html` (ไม่มีสคริปต์หรือฟอนต์จากภายนอก)
- `_headers` คือ header ความปลอดภัยสำหรับ Cloudflare Pages / Netlify (GitHub Pages ไม่อ่านไฟล์นี้ จึงใช้ CSP ที่ฝังในหน้าเว็บแทน)
- ถ้าแก้ `index.html` ค่าแฮชของสคริปต์ใน CSP จะไม่ตรงและหน้าเว็บจะถูกบล็อก

## ฟีเจอร์ล่าสุด / Latest
- รองรับไฟล์เพิ่ม: .jar .class .bat .cmd .ps1 .vbs .js .py .pyc .sh .php .au3 .reg .url .svg .lnk .eml .one .dex ฯลฯ / More file types: Java, Python, shell, batch, VBS, registry, shortcut, e-mail, OneNote, Android DEX and more.
- แท็บ "โค้ด" แกะไฟล์เป็นโค้ด บอกภาษา แบ่งเป็นส่วน ดูโค้ดเต็มพร้อมไฮไลต์บรรทัดน่าสงสัย / "Code" tab: unpacked code, language, sections, full viewer with suspicious lines marked.
- แท็บ "หลายเอนจิน" ถาม VirusTotal (ไม่บังคับ ต้องใช้ API key ของคุณเอง ส่งเฉพาะแฮช ไม่ส่งไฟล์) / "Multi-engine" tab: optional VirusTotal lookup with your own API key; only the hash is sent, never the file. Argus does not run third-party antivirus engines itself.
- CSP `connect-src` จึงอนุญาต `https://www.virustotal.com` เพิ่มจาก DoH สองโดเมน / the CSP `connect-src` therefore also allows `https://www.virustotal.com`.

## ข้อจำกัด / Limits
การวิเคราะห์เป็นแบบสถิต ไม่ได้รันไฟล์ในแซนด์บ็อกซ์ และฐานลายเซ็นมีขนาดเล็กกว่าบริการคลาวด์มาก ผล "ไม่พบ" ไม่ได้แปลว่าปลอดภัย
Analysis is static; the signature set is small. "Nothing found" does not mean "safe". Not a replacement for antivirus.
