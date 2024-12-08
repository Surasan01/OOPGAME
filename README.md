# OOPGAME


# การติดตั้งและใช้งานโปรเจคเว็บเกมการเงิน (Finance Game)

## คำแนะนำเบื้องต้น
โปรเจคนี้เป็นเว็บแอปพลิเคชันที่พัฒนาด้วย **Java Spring Boot** สำหรับการเล่นเกมการเงิน คุณสามารถนำโปรเจคนี้ไปติดตั้งและรันบนเครื่องของคุณได้ตามขั้นตอนที่ระบุไว้ด้านล่าง

---

## ความต้องการเบื้องต้น
ก่อนเริ่มการติดตั้ง โปรดตรวจสอบให้แน่ใจว่าคุณมีเครื่องมือดังต่อไปนี้:

1. **Java Development Kit (JDK) เวอร์ชัน 17 หรือสูงกว่า**  
   [ดาวน์โหลด JDK](https://www.oracle.com/java/technologies/javase-downloads.html)

2. **Maven** (สำหรับจัดการ dependency ของโปรเจค)  
   [ดาวน์โหลด Maven](https://maven.apache.org/download.cgi)

3. **Visual Studio Code (VS Code)** พร้อมติดตั้งส่วนขยาย:
   - Extension: Spring Boot Tools (ติดตั้งจาก VS Code Marketplace)
   - Extension: Java Extension Pack (สำหรับสนับสนุนการพัฒนา Java)

4. **Web Browser** (สำหรับเปิดหน้าเว็บ เช่น Google Chrome หรือ Microsoft Edge)

---

## ขั้นตอนการติดตั้ง

### 1. ดาวน์โหลดโปรเจค
1. ดาวน์โหลดไฟล์ ZIP ของโปรเจคจาก GitHub ที่ชื่อว่า Wepfinancegame.zip
2. แตกไฟล์ ZIP ไปยังโฟลเดอร์ที่ต้องการ

### 2. ตั้งค่าความพร้อมของระบบ
1. ตรวจสอบว่าเครื่องของคุณติดตั้ง JDK และ Maven แล้ว:
   - ตรวจสอบ JDK ด้วยคำสั่ง:
     ```bash
     java -version
     ```
   - ตรวจสอบ Maven ด้วยคำสั่ง:
     ```bash
     mvn -version
     ```
2. หากยังไม่ได้ติดตั้ง ให้ดำเนินการติดตั้งตามลิงก์ที่ระบุในส่วน "ความต้องการเบื้องต้น"

### 3. เปิดโปรเจคใน VS Code
1. เปิด VS Code
2. เลือก **File** > **Open Folder** แล้วเลือกโฟลเดอร์ที่มีโปรเจคนี้
3. ติดตั้งส่วนขยายที่แนะนำ (Spring Boot Tools และ Java Extension Pack) หากยังไม่ได้ติดตั้ง

### 4. สร้างและรันโปรเจค
1. เปิด Terminal ใน VS Code (ใช้คำสั่ง `Ctrl+``)
2. รันคำสั่งด้านล่างเพื่อดาวน์โหลด dependency และคอมไพล์โปรเจค:
   ```bash
   mvn clean install
   ```
3. เมื่อการติดตั้งสำเร็จแล้ว ให้รันโปรเจคด้วยคำสั่ง:
   ```bash
   mvn spring-boot:run
   ```
4. หากรันสำเร็จ คุณจะเห็นข้อความ "Started FinanceGameApplication" ใน Terminal

### 5. เปิดเว็บแอปพลิเคชัน
1. เปิดเว็บเบราว์เซอร์
2. เข้า URL: `http://localhost:8080`
3. คุณจะเห็นหน้าเว็บของโปรเจคที่พร้อมใช้งาน

---

## โครงสร้างของโปรเจค
- `src/main/java` - โค้ดหลักของโปรเจค
- `src/main/resources/templates` - ไฟล์ HTML สำหรับการแสดงผล
- `pom.xml` - ไฟล์จัดการ dependency ด้วย Maven

---

## คำสั่งที่สำคัญ
- **Clean และติดตั้ง dependency ใหม่**:
  ```bash
  mvn clean install
  ```
- **รันโปรเจค**:
  ```bash
  mvn spring-boot:run
  ```
- **หยุดการทำงานของโปรเจค**:
  กด `Ctrl+C` ใน Terminal ที่กำลังรันโปรเจค

---

## ปัญหาและการแก้ไข
1. **Java หรือ Maven ไม่ถูกติดตั้ง**:
   - ติดตั้งตามลิงก์ที่ให้ไว้ในส่วน "ความต้องการเบื้องต้น"

2. **พอร์ต 8080 ถูกใช้งานอยู่แล้ว**:
   - แก้ไขไฟล์ `application.properties` ในโฟลเดอร์ `src/main/resources` และเพิ่มบรรทัดนี้:
     ```properties
     server.port=8081
     ```
   - จากนั้นรันโปรเจคใหม่

---

หากพบปัญหาเพิ่มเติม สามารถติดต่อผู้พัฒนาโปรเจคได้ผ่านช่องทางที่ระบุใน GitHub Repository!
