# git101-632-200

> Pound Ratchathorn Songsrivisuth

room temperature iq man

## Lesson 1 (ย่อ)
[Lesson 1 Full](https://github.com/Ratchathorn/git101-632-200/blob/main/lesson1.md)
- `git init` กำหนด directory ให้เป็น git directory โดยจะมีโฟลเดอร์ .git เพิ่มขึ้นมา ห้ามแก้เด็ดขาด
- `git status` บอกสถานะ
- `git add <file1> <file2>` เพิ่มไฟล์เข้า stage โดยถ้าใช้ `git add .` จะเพิ่มทุกไฟล์
- `git rm <file1> <file2>` เอาไฟล์ออกจาก stage
- `git commit -m "comment"` เพิ่ม commit / checkpoint โดยต้องตั้งค่าผู้ commit ก่อน
- `git config` ตั้งค่าต่าง ๆ แต่เรียนแค่ตั้งค่าชื่อ / อีเมลผู้ใช้
- `git restore <file>` แก้ไฟล์กลับไปยัง commit ล่าสุด
- `git log` ดู commit โดยบนสุดคือล่าสุด ถ้าใช้ `git log --all --decorate --oneline --graph` (git log adog) จะทำให้ดูง่ายขึ้น
- `git remote` เชื่อมกับ github
- `git branch -M <name>` เปลี่ยนชื่อ branch
- `git push` ส่งไฟล์เข้า github ถ้าใช้ครั้งแรกให้ใช้ `git push -u origin main`
- `git checkout <commit-id>` ย้อนกลับมาที่ commit id นั้น ๆ
- `git clone <url>` โหลดใน github ลงเครื่อง ได้ทั้ง folder

## Lesson 2 (ย่อ)
[Lesson 2 Full](https://github.com/Ratchathorn/git101-632-200/blob/main/lesson2.md)
- `git branch` ดู branch ทั้งหมด
- `git branch <name>` สร้าง branch
- `git branch -b <name>` สร้าง branch แล้วเข้าไปใน branch นั้น ๆ
- `git branch -d <name>` ลบ branch (ต้องไม่อยู่ใน branch ที่จะลบ)
- `git checkout <branch>` เข้าไปใน branch นั้น ๆ
- `git merge <branch>` รวม branch ที่ระบุเข้ากับ branch ที่อยู่ปัจจุบัน
- `git push origin <branch>` ส่ง branch เข้าไปใน github repository
- `git pull origin <branch>` ดึง branch จากใน github repository
- Merge Conflict - เวลาที่รวม branch แล้วมีไฟล์ที่ในบรรทัดเดียวกัน มีค่าข้อมูลต่างกันในแต่ละ branch
- - เกิดตอนที่ใช้คำสั่ง `git merge`
- - ติดอยู่ระหว่างการรวม (merging)
- - ต้องแก้ไฟล์ก่อนถึงจะ merge ได้
- Pull Conflict - เวลาที่แก้ไฟล์ของตนเองแล้วดึงข้อมูล (`git pull`) ที่มีไฟล์เดียวกัน แต่ข้อมูลในบรรทัดเดียวกันนั้นต่างกัน
- - เกิดตอนใช้ตำสั่ง `git pull` จากการแก้ไฟล์แล้ว commit แต่ใช้ `git pull` ดึงไฟล์นั้นมา ทำให้ข้อมูลในบรรทัดเดียวกันนั้นต่างกัน
- - ติดอยู่ระหว่างการรวม (merging)
- - ต้องแก้ไฟล์ก่อนถึงจะ merge ได้