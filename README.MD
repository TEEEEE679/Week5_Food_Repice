# 🍽️ Food & Recipe Management System

ระบบจัดการข้อมูลเมนูอาหารและสูตรวัตถุดิบ พัฒนาด้วยภาษา PHP (OOP) เชื่อมต่อฐานข้อมูลผ่าน PDO และตกแต่งหน้าตาเว็บด้วย Bootstrap 5

## ✨ ฟีเจอร์หลัก (Features)
*   **CRUD Operations:** เพิ่ม, อ่าน, แก้ไข, ลบ ข้อมูลเมนูอาหารได้
*   **1-to-Many Relationship:** จัดการสูตรวัตถุดิบย่อยในแต่ละเมนูอาหาร (เพิ่มได้หลายรายการ)
*   **Image Upload:** รองรับการอัปโหลดรูปภาพเมนูอาหารเข้าสู่เซิร์ฟเวอร์
*   **Responsive UI:** แสดงผลสวยงามและใช้งานง่ายด้วย Bootstrap 5

## 💻 สิ่งที่ต้องเตรียม (Prerequisites)
*   XAMPP หรือเว็บเซิร์ฟเวอร์จำลองอื่นๆ
*   PHP 8.0 ขึ้นไป
*   MySQL / MariaDB

## 🚀 วิธีติดตั้งและใช้งาน (Installation)

1. นำโฟลเดอร์โปรเจกต์ไปวางไว้ใน `htdocs` (สำหรับ XAMPP)
2. สร้างโฟลเดอร์ชื่อ `uploads` ไว้ในโฟลเดอร์หลักของโปรเจกต์ (สำหรับเก็บรูปภาพ)
3. เข้าไปที่ phpMyAdmin สร้าง Database ชื่อ `foods_repice_db`
4. นำโค้ด SQL ด้านล่างไปรันในเมนู SQL ของ phpMyAdmin เพื่อสร้างตาราง

### 🗄️ โครงสร้างฐานข้อมูล (Database SQL)

```sql
-- สร้างตาราง foods (เก็บข้อมูลเมนูอาหารหลัก)
CREATE TABLE `foods` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name_th` varchar(255) NOT NULL,
  `category` varchar(100) NOT NULL,
  `image` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- สร้างตาราง recipes (เก็บสูตรวัตถุดิบ)
CREATE TABLE `recipes` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `food_id` int(11) NOT NULL,
  `recipe_name` varchar(255) NOT NULL,
  `quantity` decimal(10,2) NOT NULL,
  `unit_name` varchar(50) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;