# Data Wareouse and Business Intelligence

## Project Week 1

### Step_01 Create Codespaces
1. กดเลือกที่ Code
2. ตรงหัวข้อ Codespaces กดไปที่เครื่องหมายบวก (create a codespace on main)
![Alt text](<Screenshot 2567-02-04 at 10.40.48.png>)

3. จะมีการสร้างพื้นที่เพื่อใช้สำหรับเขียน code โดยมีชื่อของ Codesspaces ต่างกัน
![Alt text](<Screenshot 2567-02-04 at 10.55.26.png>)

### Step_02 Create Folder
1. กดไปที่ New Folder สร้าง folder ใหม่ขึ้นมา 2 folder
![Alt text](<Screenshot 2567-02-04 at 11.05.42.png>)

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

![Alt text](<Screenshot 2567-02-04 at 11.19.35.png>)

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
![Alt text](<Screenshot 2567-02-04 at 11.27.32.png>) 

3. Log in เลือก system : PostgreSQL 
![Alt text](<Screenshot 2567-02-04 at 11.33.19.png>)

### Step_05
1. รันด้วย create_tables.py และเขียน code ของ PostgresSQL

        python create_tables.py
![Alt text](<Screenshot 2567-02-04 at 11.45.37.png>)

2. สร้างไฟล์สำหรับ etl เพื่อนำข้อมูลจาก json เข้าไปยัง postgres  ใช้ไฟล์  etl.py

        python etl.py 
![Alt text](<Screenshot 2567-02-04 at 11.48.19.png>)

### Remark
- การเพิ่ม-ลด tables
![Alt text](<Screenshot 2567-02-04 at 11.50.40.png>) 
