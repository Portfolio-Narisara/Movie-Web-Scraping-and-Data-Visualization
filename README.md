# Movie Web Scraping and Data Visualization
<br>

**Tool** : Google Colab notebooks <br>
**Programming Language** : Python <br>
**Libraries** : Pandas, BeautifulSoup <br>
**Visualization** : Matplotlib, Seaborn <br>
**Data** : https://www.themoviedb.org/ <br>
<br>
# Objectives
ทําการดึงข้อมูลเพื่อสร้าง dataset หรือ การ staging ข้อมูล จาก open web APIs ที่มีการ customize query ที่เป็น parameters จาก API ได้ และวิเคราะห์ข้อมูลที่รวบรวมมา 

**Table of Contents**
- [STAGE 1: Web Scraping](#stage-1-web-scraping)
    - [Web API](#web-api)
    - [Requests Data](#requests-data)
- [STAGE 2: Data Preprocessing](#stage-2-data-preprocessing)
    - [Data Overview](#data-overview)
    - [Data Assessment](#data-assessment)
- [STAGE 3: Data Visualization](#stage-3-data-visualization)
<br>
<br>

----

## STAGE 1: Web Scraping

### Web API
Web API API ที่เลือกคือ https://www.themoviedb.org/ เป็นที่รวบรวมข้อมูลเกี่ยวกับภาพยนตร์และรายการทีวี รวมถึงนักแสดงและการวิจารณ์

โดยเราจะเฉพาะเจาะจงไปที่ข้อมูลของภาพยนตร์ที่เป็นที่นิยมในขณะนี้ คือ https://www.themoviedb.org/movie โดยการใช้ Web API นี้ เราจะสามารถดึงข้อมูลในรูปแบบ JSON มาใช้ในการวิเคราะห์และการแสดงผลข้อมูลได้

### Requests Data
ข้อมูลที่เราต้องการดึงจาก TMDb API ประกอบด้วย:

    id = ไอดีของภาพยนตร์

    title = ชื่อภาพยนตร์

    release_date = วันที่เข้าฉาย

    rating = คะแนนความนิยมของภาพยนตร์

    country = ประเทศที่ผลิตภาพยนตร์

    runtime = ระยะเวลาความยางของภาพยนตร์

    genres = ประเภทของภาพยนตร์

    revenue = รายได้จากภาพยนตร์

เพื่อดึงข้อมูลจาก TMDb API เราจำเป็นต้อง:
<br>
<br>
1.สมัครบัญชีผู้ใช้บน TMDb และรับ API Key

2.ใช้ API Key เพื่อทำการเรียกข้อมูลจาก API

3.จัดเก็บข้อมูลที่ได้รับในรูปแบบ JSON เพื่อนำไปใช้งานต่อในการวิเคราะห์และการแสดงผลข้อมูลต่อไป
<br>
<br>

----

## STAGE 2: Data Preprocessing

### Data Overview
ชุดข้อมูลมีรายละเอียดดังนี้: 8 คอลัมน์ และ 1,200 แถว เป็นข้อมูลของภาพยนตร์ที่เป็นที่นิยมในขณะนี้ผ่านทาง TMDb Movie API

### Data Assessment
ทำการเตรียมข้อมูลที่ใช้สำหรับการวิเคราะห์ ให้พร้อมและเหมาะสมตามความต้องการของการวิเคราะห์:

- การตรวจสอบค่า null หรือ missing value ในข้อมูล
- การตรวจสอบและลบข้อมูลที่เป็นค่า null ที่มีการแทนค่า
- เปลี่ยนประเภทข้อมูลให้เหมาะสมกับลักษณะข้อมูล

----

## STAGE 3: Data Visualization
### 1. กราฟแสดงความถี่ของประเภทภาพยนตร์ ตั้งแต่ปี 2018-2022
ประเภทภาพยนตร์ที่เป็นที่นิยมใน 5 ปีที่ผ่านมา(2018-2022) ซึ่งสามารถช่วยในการสร้างภาพยนตร์ให้ได้ผลตอบรับที่ดีในอนาคต 
<p align="center">
    <kbd><img width="600" alt="tipe hotel rasio" src="https://github.com/Portfolio-Narisara/Movie-Web-Scraping-and-Data-Visualization/assets/171022446/050fbcac-4c66-47c1-8870-fcb4e2abd444"></kbd><br>
</p>
<br>
จากข้อมูลจะเห็นได้ว่าประเภทที่มีการผลิตมากที่สุดในทุกปี คือ Acion แต่หนังที่น่าสนใจคือหนังแนว Thriller ที่ในปี 2018 มีการผลิตหนังแนวนี้น้อยมากแต่ในปี 2022 กลับเป็นหนังแนวที่ผลิตเกือบมากที่สุด รวมถึงหนังแนว Mystery ที่ขยับขึ้นมาเยอะมากจากปี 2018
<br>

### 2. ความสัมพันธ์ของแต่ละประเภทภาพยนต์
ถ้าหากค่าที่ได้มีค่า

ใกล้ -1.0 นั้นหมายความว่าตัวแปรทั้งสองตัวมีความสัมพันธ์กันอย่างมากในเชิงตรงกันข้าม

หากมีค่าใกล้ +1.0 นั้นหมายความว่า ตัวแปรทั้งสองมีความสัมพันธ์กันอย่างมากในทิศทางเดียวกัน

และหากมีค่าเป็น 0 นั้นหมายความว่า ตัวแปรทั้งสองตัวไม่มีความสัมพันธ์ต่อกัน

<p align="center">
    <kbd> <img width="800" alt="pembatalan city" src="https://github.com/Portfolio-Narisara/Movie-Web-Scraping-and-Data-Visualization/assets/171022446/9ea05846-2229-4beb-870f-a4519e95c40dg"></kbd> <br>
</p>
<br>

### 3. Frequency genres

แสดงประเภทหนังที่มีการผลิตมากที่สุด ซึ่งจากข้อมูลแสดงถึงการผลิตภาพยนตร์ประเภท Adventure และ Action มีจำนวนมากที่สุด 

<p align="center">
    <kbd><img width="400" alt="tren lead" src="https://github.com/Portfolio-Narisara/Movie-Web-Scraping-and-Data-Visualization/assets/171022446/fafa1068-e8ad-4c7b-95b1-b3cedabe9356"></kbd> <br>
</p>
<br>

### 4. กราฟแสดงความสัมพันธ์ระหว่างระยะเวลาของหนัง(runtime) และ รายได้ของหนัง(revenue)
จากข้อมูลจะเห็นได้ว่าระยะเวลาของหนังประมาณ 150-200 จะมี revenue ที่สูงกว่าช่วงเวลาอื่น แสดงถึงช่วงระยะเวลาที่มีผลต่อรายได้ของภาพยนตร์
 
<p align="center">
    <kbd><img width="600" alt="tipe hotel rasio" src="https://github.com/Portfolio-Narisara/Movie-Web-Scraping-and-Data-Visualization/assets/171022446/59ceef03-981c-4372-9370-475cd3c916ec"></kbd><br>
</p>
