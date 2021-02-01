# Lesson 1
> Date: 1/2/2021

## Bash 

**drwx**r-xr-x (ของ bash)

d|rwx|r-x|r-x

- **d** = directory (dir / folder)
- **r** = read
- **w** = write
- **x** = execute

สามตัวแรกคือผู้ใช้
สามตัวต่อมาคือกลุ่ม
สามตัวหลังสุดคือผู้ใช้อื่น ๆ

## คำสั่ง cmd (Command Prompt)
- `d:` ไป drive d:
- `cd \` ไป root directory
- `cd .` ไป current directory
- `cd ..` ไป upper directory (ย้อนกลับไป)
- `cd <dir>` ไป directory นั้น ๆ

## คำสั่ง bash
- ดู directory
- - `ls`
- - `ls -l`
- - `ls -la`
- `cd \` ไป root directory
- `cd .` ไป current directory
- `cd ..` ไป upper directory (ย้อนกลับไป)
- `cd <dir>` ไป directory นั้น ๆ

## คำสั่ง git ต่าง

### init
`git init`
กำหนด dir ให้เป็น git dir

จะมี dir ".git" เพิ่มมา **ห้ามแก้เด็ดขาด**

### status
`git status`
บอกสถานะ

branch (ชื่อ default คือ master)

commit (การเปลี่ยนแปลง)

### add
`git add`
เพิ่มไฟล์เข้ามา staging area (เหมือนนักแสดงขึ้นเวที)

- `git add <file>`
- `git add <file1> <file2>`
- `git add .` (เพิ่มทุกไฟล์)

### remove
`git rm`
ลบไฟล์ออกจาก staging area

- `git rm <file>`
- `git rm <file1> <file2>`

### commit
`git commit -m "comment"`
สร้าง commit (checkpoint)

-m คือ ระบุ message

ก่อน commit ต้องตั้งค่าคน commit

### config

- `git config user.name`
- `git config user.email`

ตรวจสอบว่ามี name/email หรือไม่

- `git config user.name "Your Name"`
- `git config user.email "yourmail@ku.th"`

ตั้งค่า name/email

- `git config --global user.name "Your Name"`
- `git config --global user.email "yourmail@ku.th"`

*ถ้าใช้คอมคนเดียวให้เพิ่ม --global

### restore

`git restore <file>`
ไว้แก้ไฟล์กลับไปที่เซฟไว้ใน commit (checkpoint)

### log
`git log`
ไว้ดูคำสั่ง

commit แรกจะอยู่ล่างสุด

commit id เลขฐาน 16 จำนวน 32-48 ตัว ระบุใครสร้าง ระบุวันเวลา ระบุ message

`git log --all --decorate --oneline --graph`
ไว้ดูคำสั่งง่าย ๆ **(git log adog)**
- --**a**ll คือทั้งหมด
- --**d**ecorate คือทำให้สวย
- --**o**neline คือย่อให้เหลือเส้นเดียว
- --**g**raph เป็นกราฟ

`<id> <HEAD -> master> <comment>`
- id ~7 ตัว
- HEAD -> master เป็น branch

`<id> (HEAD -> main, origin/main) <comment>`
- origin/main คือเชื่อมกับ github

## github
- origin คือ ชื่อ remote repository ที่เราตั้งขึ้นเอง ต้องตรงกับชื่อ remote ที่เราใช้คำสั่ง git remote add
- master คือ branch หลักที่ได้มาตั้งแต่ต้นจากการสร้าง git repository (ตอนสั่ง git init)
- main คือ default branch ใหม่ของ github.com

### remote
`git remote add origin <url>`
เชื่อม local repository (git repo ในเครื่องเรา) กับ github

`git remote get-url origin`
พิมพ์ url ของ origin

`git remote remove origin`
ลบ origin url

`git branch -M <name>`
เปลี่ยนชื่อ branch

`git push -u origin main`
ส่งไฟล์และประวัติไปเก็บที่ github
ถ้าทำ -u แล้ว ใช้ `git push` ได้เลย

`control panel > credential manager > windows credential > github > แก้ชื่อ`
check credential (ว่าเราทำ)

*อย่าลืม remove ถ้าใช้หลายคน

- `git checkout <commit-id>`
- `git checkout <commit-id> <file>`

ย้อนกลับมาจากที่เซฟไว้ใน commit (ใน github)

`git clone <git-url>`
เอาที่ทำไว้จาก github กลับมาลงคอม

*ได้ทั้ง folder

user directory: user/dir

### README
README.md ไว้ขึ้นหน้าแรก

md = ภาษา markdown (เหมือนใน colab)