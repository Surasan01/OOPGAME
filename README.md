# OOPGAME

### List การติดตั้ง (เพื่อจะเอาไป Run ในแบบต่างๆ)

1. [**การติดตั้งและใช้งานโปรเจคเว็บเกมการเงิน (Wepfinancegame.zip)**](#Listการติตตั้งที่1)
2. [**คู่มือการติดตั้งและใช้งานโปรเจค ExportFinanceGame ใน Unity (ExportFinanceGame.unitypackage)**](#Listการติตตั้งที่2)
3. [**วิธีการติดตั้งเพื่อเล่นเกม (Maingame.zip)**](#Listการติตตั้งที่3)
4. [**ดูโค้ดต่างๆ ในตัวโปรเจค (Assets.zip)**](#Listการติตตั้งที่4)


#### Listการติตตั้งที่1
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
2. หากยังไม่ได้ติดตั้ง ให้ดำเนินการติดตั้งตามลิงก์ที่ระบุในส่วน "ความต้องการเบื้องต้น".

### 3. การตั้งค่า PATH สำหรับ JDK และ Maven
1. **ตั้งค่า PATH สำหรับ JDK:**
   - เพิ่ม JAVA_HOME ลงในตัวแปรสิ่งแวดล้อม:
     - บน Windows:
       1. ไปที่ `Control Panel` > `System` > `Advanced system settings`.
       2. คลิกปุ่ม `Environment Variables`.
       3. ภายใต้ `System variables` คลิก `New` แล้วเพิ่ม:
         - ชื่อ: `JAVA_HOME`
         - ค่า: ตำแหน่งโฟลเดอร์ที่ติดตั้ง JDK (เช่น `C:\Program Files\Java\jdk-17`).
       4. แก้ไขตัวแปร `Path` แล้วเพิ่ม `%JAVA_HOME%\bin`.
     - บน Mac/Linux:
       - แก้ไขไฟล์ `~/.bashrc` หรือ `~/.zshrc` แล้วเพิ่ม:
         ```bash
         export JAVA_HOME=/path/to/jdk
         export PATH=$JAVA_HOME/bin:$PATH
         ```
       - ใช้คำสั่ง `source` เพื่อรีโหลด:
         ```bash
         source ~/.bashrc  # หรือ source ~/.zshrc
         ```

2. **ตั้งค่า PATH สำหรับ Maven:**
   - ดาวน์โหลด Apache Maven จาก [เว็บไซต์ทางการ](https://maven.apache.org/download.cgi).
   - แตกไฟล์ ZIP ไปยังโฟลเดอร์ที่ต้องการ.
   - เพิ่มตัวแปร `MAVEN_HOME` และเพิ่ม `bin` ลงใน `Path`:
     - บน Windows:
       - คล้ายกับขั้นตอน JDK ให้เพิ่มตัวแปรใหม่:
         - ชื่อ: `MAVEN_HOME`
         - ค่า: ตำแหน่งโฟลเดอร์ Maven (เช่น `C:\Program Files\Apache Maven`).
       - แก้ไข `Path` แล้วเพิ่ม `%MAVEN_HOME%\bin`.
     - บน Mac/Linux:
       - แก้ไขไฟล์ `~/.bashrc` หรือ `~/.zshrc` แล้วเพิ่ม:
         ```bash
         export MAVEN_HOME=/path/to/maven
         export PATH=$MAVEN_HOME/bin:$PATH
         ```
       - ใช้คำสั่ง `source` เพื่อรีโหลด:
         ```bash
         source ~/.bashrc  # หรือ source ~/.zshrc
         ```

3. ตรวจสอบว่าตั้งค่าถูกต้องแล้วด้วยคำสั่ง:
   ```bash
   java -version
   mvn -version

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
#### Listการติตตั้งที่2
# คู่มือการติดตั้งและใช้งานโปรเจกต์ ExportFinanceGame ใน Unity

## ความต้องการเบื้องต้น
1. **Unity Hub**
   - ดาวน์โหลด Unity Hub จาก [เว็บไซต์ Unity](https://unity.com/download) และติดตั้ง

2. **Unity Editor**
   - ใช้เวอร์ชันที่เข้ากันได้ (เช่น Unity 2021.3 LTS หรือสูงกว่า) ซึ่งสามารถติดตั้งผ่าน Unity Hub ได้

3. **ไฟล์ ExportFinanceGame.unitypackage**
   - ดาวน์โหลด ไฟล์ ExportFinanceGame.unitypackage จาก Github

---

## ขั้นตอนการติดตั้งและใช้งาน

### 1. ดาวน์โหลดและติดตั้ง Unity
1. ดาวน์โหลด [Unity Hub](https://unity.com/download) และติดตั้งบนเครื่องของคุณ
2. เปิด Unity Hub และเข้าสู่ระบบด้วยบัญชี Unity ของคุณ (สมัครใหม่หากยังไม่มีบัญชี)
3. ไปที่แท็บ **Installs** ใน Unity Hub
   - คลิกปุ่ม **Add** เพื่อเพิ่ม Unity Editor
   - เลือกเวอร์ชันที่แนะนำ (เช่น Unity 2021.3 LTS) และคลิก **Install**
   - ติดตั้งโมดูลเสริม เช่น **Windows Build Support** (ถ้าจำเป็น)

### 2. สร้างโปรเจกต์ Unity ใหม่
1. เปิด Unity Hub และไปที่แท็บ **Projects**
2. คลิกปุ่ม **New Project**
   - เลือกเทมเพลต 3D หรือ 2D ตามที่คุณต้องการ
   - ตั้งชื่อโปรเจกต์ (เช่น `FinanceGameProject`) และเลือกตำแหน่งที่บันทึก
   - คลิก **Create Project** เพื่อสร้างโปรเจกต์ใหม่

### 3. นำเข้าไฟล์ ExportFinanceGame.unitypackage
1. เปิดโปรเจกต์ Unity ที่สร้างขึ้นมา
2. ไปที่เมนู **Assets** > **Import Package** > **Custom Package...**
3. เลือกไฟล์ `ExportFinanceGame.unitypackage` ที่คุณมีอยู่
4. คลิก **Import** เพื่อเพิ่มไฟล์ทั้งหมดลงในโปรเจกต์ของคุณ

### 4. การตั้งค่าโปรเจกต์
1. ตรวจสอบว่าไฟล์ที่นำเข้าปรากฏใน **Project Window**
   - ไฟล์ควรมีโครงสร้างที่จัดการไว้ เช่นโฟลเดอร์ Scripts, Prefabs, และ Scenes
2. เปิด Scene หลักของเกม:
   - ไปที่โฟลเดอร์ **Scenes** และดับเบิลคลิกที่ไฟล์ Scene ที่ระบุ (เช่น `MainScene.unity`)

### 5. รันเกมใน Unity Editor
1. คลิกปุ่ม **Play** (สัญลักษณ์ ▶️) บนแถบเครื่องมือเพื่อทดลองเล่นเกม
2. ตรวจสอบว่าเกมทำงานถูกต้อง หากพบปัญหา ให้ตรวจสอบ Console (Window > General > Console) เพื่อดูข้อผิดพลาด

### 6. (ถ้าต้องการ) สร้างไฟล์ Build ของเกม
1. ไปที่เมนู **File** > **Build Settings...**
2. เลือกแพลตฟอร์มที่คุณต้องการ (เช่น PC, Mac & Linux Standalone)
   - คลิกปุ่ม **Switch Platform** (ถ้ายังไม่ได้เลือก)
3. คลิกปุ่ม **Add Open Scenes** เพื่อเพิ่ม Scene หลักของคุณลงใน Build
4. คลิก **Build** และเลือกตำแหน่งที่บันทึกไฟล์เกม

---

## หมายเหตุเพิ่มเติม
- หากมีปัญหาหรือคำถามเกี่ยวกับโปรเจกต์ โปรดติดต่อผู้ดูแลโครงการ
- Unity Documentation: [https://docs.unity3d.com/](https://docs.unity3d.com/)

---
#### Listการติตตั้งที่3
# วิธีการติดตั้งเพื่อเล่นเกม

1. ดาวน์โหลดไฟล์ `.zip` ที่ชื่อว่า Maingame.zip ของเกมจากลิงก์ที่ให้ไว้
2. แตกไฟล์ `.zip` ที่ดาวน์โหลดมาไปยังโฟลเดอร์ที่คุณต้องการ
   - คลิกขวาที่ไฟล์ `.zip` และเลือก `Extract Here` หรือใช้โปรแกรมสำหรับแตกไฟล์ เช่น WinRAR หรือ 7-Zip
3. เปิดโฟลเดอร์ที่คุณแตกไฟล์ไว้
4. ดับเบิลคลิกไฟล์ที่ชื่อ **`FINANCE GAME`** เพื่อเริ่มเล่นเกม

---
#### Listการติตตั้งที่4
# ดูโค้ดต่างๆ ในตัวโปรเจค (Assets.zip)

1. ดาวน์โหลดไฟล์ `.zip` ที่ชื่อว่า **Assets.zip** จาก Github
2. แตกไฟล์ `.zip` ที่ดาวน์โหลดมาไปยังโฟลเดอร์ที่คุณต้องการ
   - คลิกขวาที่ไฟล์ `.zip` และเลือก `Extract Here` หรือใช้โปรแกรมสำหรับแตกไฟล์ เช่น WinRAR หรือ 7-Zip
3. ไปที่เมนู  **Assets** > **Script**
4. จะมีไฟล์ภาษา **C Sharp** ที่เขียนไว้เป็นการทำงานหลักของตัวเกม