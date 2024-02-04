# Data Wareouse and Business Intelligence

## Project Week 1

### Step_01 Create Codespaces
1. กดเลือกที่ Code
2. ตรงหัวข้อ Codespaces กดไปที่เครื่องหมายบวก (create a codespace on main)
<img width="1304" alt="Screenshot 2567-02-04 at 10 40 48" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/96752d3f-490a-46dc-8524-39df750570b1"> 

3. จะมีการสร้างพื้นที่เพื่อใช้สำหรับเขียน code โดยมีชื่อของ Codesspaces ต่างกัน
<img width="1432" alt="Screenshot 2567-02-04 at 10 55 26" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/db424272-e46b-4c79-a097-7c9d0e554beb">

### Step_02 Create Folder
1. กดไปที่ New Folder สร้าง folder ใหม่ขึ้นมา 2 folder
<img width="421" alt="Screenshot 2567-02-04 at 11 05 42" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/8f0654da-516f-410a-987d-5b26cb6e75e2">

2. Download Data source : https://github.com/zkan/swu-ds525/tree/main
3. folder ที่ 1 ชื่อ "01-data-modeling-i"
    - download files :
      - /docker-compose.yml 
      - /create_tables.py
      - /etl.py 
4. folder ที่ 1 ชื่อ "data"
    - download files :
        -  /github_events_01.json

### Step_03 Install Enviroment on Terminal
<img width="719" alt="Screenshot 2567-02-04 at 11 19 35" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/754083a0-e413-47f0-b0ef-cd5aee733685">

1. เตรียม Web server **nginx** โดยใช้งานผ่าน Docker

        docker run -p 8080:80 nginx
  
2. เปลี่ยน path ให้อยู่ใน 01-data-molling-1
  
        cd 01-data-modeling-i

3. เพื่อให้ Python สามารถเขียนด้วย  Postgres ต้อง ทำการ install ที่เกี่ยวข้อง
  
       pip install psycopg2-binary
  
4. Run docker-compose.yml เพื่อสร้าง Database Postgres และ Adminer ด้วย docker

        docker-compose up

### Step_04 Database
1. ไปที่แถบ PORTS (1) 
2. กดเลือกที่ Port 8080 เพื่อเปิด browser adminer ขึ้นมา
<img width="1065" alt="Screenshot 2567-02-04 at 11 27 32" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/35e3d91c-e190-4684-9235-12214551b2dc">

3. Log in เลือก system : PostgreSQL 
<img width="583" alt="Screenshot 2567-02-04 at 11 33 19" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/9c2c7e68-4a4e-44c7-9991-d1e188ca7557">

### Step_05
1. รันด้วย create_tables.py และเขียน code ของ PostgresSQL

        python create_tables.py
<img width="791" alt="Screenshot 2567-02-04 at 11 45 37" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/52605656-25a4-496d-81db-9e197c83f57c">

2. สร้างไฟล์สำหรับ etl เพื่อนำข้อมูลจาก json เข้าไปยัง postgres  ใช้ไฟล์  etl.py

        python etl.py 
<img width="594" alt="Screenshot 2567-02-04 at 11 48 19" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/3bbecf37-c043-40fb-9316-4d5ab93017a4">

### Remark
- การเพิ่ม-ลด tables
<img width="634" alt="Screenshot 2567-02-04 at 11 50 40" src="https://github.com/nisitrabun/dw-and-bi/assets/139243286/962f3006-b73d-49cd-86cd-1cc6c3c73bbf">
