# Lesson 2
> Date: 8/2/2021

## เริ่มงาน
`git clone <url>` -> `cd <path>` -> `git log --all --decorate --oneline --graph` เช็คทุกรอบก่อนทำอะไรก็ตาม

## create branch (แตกกิ่ง)
`git branch <name>`
จุดเริ่มต้น branch จะมีไฟล์กับ commit ที่เราสร้างไว้ (ได้มาจาก main) เหมือนตัวโปรแกรมเก่าที่ใช้ได้อยู่แล้ว เราก็เข้าไปเพิ่ม feature ให้กับโปรแกรมนั้น ๆ

`git checkout <branch>` ไปที่ branch นั้น ๆ

## merge branch (no conflict)

`git checkout <branch>`

*สร้างไฟล์

`git add <file>` -> `git commit -m "comment"`

### push branch ขึ้น github
`git checkout <branch>` -> `git push origin <branch>`

`git checkout <branch1>`
เปลี่ยนไปที่ branch ปลายทาง

`git merge <branch2>`
รวม branch2 เข้าไปอยู่ branch1

พอใส่คำสั่ง merge แล้วจะขึ้นหน้า editor ให้กด ESC แล้วพิมพ์ wq แล้วกด enter

`git push origin <branch>`
ส่งเข้าไปใน github ถือว่า merge สมบูรณ์

## pull (no conflict)
`cd ..`
ออกกลับมาข้างนอก

`git clone <git-url> <new folder>` -> `cd <new folder>`
clone ไปยัง folder นั้น ๆ (จำลองว่าเหมือนมีคนอื่นมาช่วยทำงาน)

`git add <file>` -> `git commit -m "comment"` -> `git push origin main` จำลองว่าอีกคนส่งไฟล์เข้าไป repository เรา

`cd ..` -> `cd <original folder>` -> `ls -la`
จะพบว่าไม่มีไฟล์ที่อีกคนเพิ่ม

`git pull origin <branch>`
ดึงการเปลี่ยนแปลงจาก branch

`ls -la`
จะพบว่ามีไฟล์เพิ่มมาแล้ว

## merge (with conflict)

`git checkout <branch1>`

*แก้ไฟล์

`git add <file>` ->
`git commit -m "comment"`

`git checkout -b <branch2>` สร้าง branch2 แล้วเข้าไปที่ branch2

*แก้ไฟล์

`git add <file>` ->
`git commit -m "comment"`

ต้องเป็นไฟล์เดียวกัน <ins>บรรทัดเดียวกัน</ins> แต่ข้อมูลต่างกันในคนละ branch

`git checkout <branch1>`
เปลี่ยนไปที่ branch ปลายทาง

`git merge <branch2>`
รวม branch2 เข้าไปอยู่ branch1 แต่จะ merge ไม่ได้ เพราะข้อมูลในไฟล์ต่างกัน เกิด conflict (ถ้าเป็นไฟล์ .txt ตัว git จะสร้างคำอธิบายไว้) ต้องแก้ไฟล์ก่อนถึงจะ merge ได้

วิธีแก้ conflict : ลบเส้นที่ไม่ต้องการออก

พอแก้ไฟล์แล้ว

`git add <file>` ->
`git commit -m "comment"`
แล้วส่งขึ้น github

`git push origin <branch>`
ไม่จำเป็นต้อง push อีกกิ่ง เพราะรวมกันไปแล้ว

## pull (with conflict)
ในเครื่องใหม่ (จำลองว่าอีกคนมาแก้)

`cd ..` ->
`cd <new folder>` ->
`git pull origin <branch>`
ดึงไฟล์จากใน github มาแก้

*แก้ไฟล์

`git add <file>` ->
`git commit -m "comment"` ->
`git push origin <branch>`

ในเครื่องเก่า (เราแก้)
`cd ..` ->
`cd <old folder>`

*แก้ไฟล์ (ต้องแก้ไฟล์เดียวกัน บรรทัดเดียวกัน แต่ข้อมูลในบรรทัดต่างกัน)

`git add <file>` ->
`git commit -m "comment"`

ก่อน push ให้ pull ข้อมูลมาก่อน

`git pull origin <branch>`
จะเกิด conflict ให้แก้ไข conflict แล้ว add/commit/push

`git add <file>` ->
`git commit -m "comment"` ->
`git push origin <branch>`

ในเครื่องใหม่ (จำลองว่าอีกคนมาแก้)
`cd ..` ->
`cd <new folder>` ->
`git pull origin <branch>`
pull ได้ ไม่เกิด conflict เพราะไม่มีการแก้ไขอะไรเพิมเติม