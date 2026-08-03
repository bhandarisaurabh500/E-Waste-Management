# 🌿 EcoCycle: Intelligent E-Waste Management & Circular Economy Portal

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3.5-brightgreen.svg)
![Java](https://img.shields.io/badge/Java-JDK%2021-orange.svg)
![MySQL](https://img.shields.io/badge/Database-MySQL%208.0-blue.svg)
![Thymeleaf](https://img.shields.io/badge/Frontend-Thymeleaf%20%2B%20Bootstrap%205-green.svg)
![Status](https://img.shields.io/badge/Build-Passing-success.svg)

**EcoCycle Hub** is a full-stack, enterprise-grade E-Waste Management and Recycling web application built using **Spring Boot 3**, **Thymeleaf**, **Spring Data JPA**, and **MySQL**. It solves the critical environmental challenge of toxic electronic waste disposal through digital logistics, OTP verification, corporate EPR compliance, and a certified refurbished electronics marketplace.

---

## 📌 Problem Statement & Solution

Improper disposal of obsolete electronic goods releases hazardous heavy metals (*lead, mercury, cadmium, barium*) into soil and water tables. 
**EcoCycle Hub** connects individual citizens, corporations, and authorized e-waste refurbishers on a unified platform to:
- Enable certified doorstep e-waste pickup for citizens.
- Streamline enterprise IT asset disposition (ITAD) and Extended Producer Responsibility (EPR) reporting.
- Provide a secondary marketplace for certified Grade-A refurbished tech to extend hardware lifespan.

---

## ✨ Key Features & Multi-Role Architecture

### 1. 👤 Citizen / Individual User Portal
- **Secure Authentication:** OTP-based 2-step email verification via Spring Boot `JavaMailSender`.
- **Doorstep Pickup Scheduling:** Submit device specs, category, condition percentage, date slot, and device photo upload.
- **Instant Digital Confirmation:** Real-time request tracking and pickup receipt.

### 2. 🏢 Corporate & Enterprise Portal (ITAD / EPR)
- **Bulk Asset Logistics:** Batch disposal requests for enterprise servers, workstations, and office IT assets.
- **EPR & Compliance Auditing:** Regulatory compliance tracking adhering to Central Pollution Control Board (CPCB) and ISO 14001 guidelines.
- **Data Sanitization Certificate:** Certified verification for physical degaussing & NIST 800-88 digital data wiping.

### 3. 🏪 Refurbisher & Seller Marketplace
- **Authorized Vendor Portal:** Dedicated registration & authentication for certified e-waste dismantlers.
- **Circular Economy Store:** Listing certified second-life laptops, smartphones, and energy-efficient appliances.
- **Secure COD Checkout:** Doorstep verification and Cash on Delivery order processing.

---

## 🛠️ Technology Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Backend Framework** | Spring Boot 3.3.5, Spring MVC, Spring Data JPA, Hibernate ORM |
| **Language** | Java 21 (LTS) |
| **Database** | MySQL 8.0 with HikariCP connection pooling |
| **Frontend & Templating**| Thymeleaf 3.x, HTML5, Vanilla Modern CSS3, JavaScript (ES6) |
| **Styling & Icons** | Custom Glassmorphism Design System, Bootstrap 5.3, FontAwesome 6.7 |
| **Email Verification** | Spring Mail (`JavaMailSender`), SMTP OTP Generation & Verification |
| **Build & Dependency Tool** | Apache Maven 3.9.x |

---

## 🏗️ Project Architecture & Workflow

```
       [ Client Browser (HTML5 / Bootstrap 5 / Thymeleaf) ]
                               │
                       HTTP / REST Mappings
                               │
                               ▼
            [ Spring MVC Controllers (Presentation Layer) ]
        ┌──────────────────────┼──────────────────────┐
        ▼                      ▼                      ▼
  [UserController]   [CorprativeController]   [SellingController]
        │                      │                      │
        ▼                      ▼                      ▼
            [ Spring Service Layer (Business Logic) ]
         ├── UserService / CorprativeService / SellingService
         └── MailService (SMTP OTP Generation & Verification)
                               │
                               ▼
            [ Spring Data JPA Repositories (DAO Layer) ]
                               │
                               ▼
           [ MySQL Relational Database (Persistence Layer) ]
```

---

## 🚀 How to Run the Project Locally

### 1. Prerequisites
- **JDK 21** or higher installed.
- **MySQL Server (8.0+)** running on `localhost:3306`.
- **Apache Maven 3.9+** (or use the included Maven wrapper).

### 2. Database Configuration
Create a database in MySQL:
```sql
CREATE DATABASE e_wastemanagement;
```

Update credentials in `src/main/resources/application.properties` if needed:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/e_wastemanagement?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=update
```

### 3. Run Application
Run the following command from the project root directory:

**Windows PowerShell:**
```powershell
$env:JAVA_HOME = "C:\Program Files\Java\jdk-21"
& "C:\Users\ASUS\Downloads\apache-maven-3.9.11-bin\apache-maven-3.9.11\bin\mvn.cmd" spring-boot:run
```

**Standard Maven Command:**
```bash
mvn spring-boot:run
```

### 4. Access Application
Open your browser and navigate to:
👉 **[http://localhost:8080/](http://localhost:8080/)**

---

## 🌐 Complete Route Directory

| Page | URL Route | Description |
| :--- | :--- | :--- |
| **Home Page** | `GET /` | Hero section, live recycling metrics, process workflow, reviews |
| **User Login** | `GET /loginpage` | Individual user login |
| **User Signup** | `GET /register` | Individual user registration with OTP validation |
| **Corporate Login** | `GET /e` | Corporate partner authentication |
| **Corporate Signup** | `GET /corprative` | Enterprise ITAD onboarding with OTP validation |
| **Seller Login** | `GET /loginpagesell`| Refurbisher & scrap vendor login |
| **Seller Signup** | `GET /r` | Vendor registration |
| **Citizen Pickup** | `GET /p` | Doorstep device pickup booking form |
| **Corporate Pickup**| `GET /po` | Bulk enterprise IT asset disposal form |
| **Marketplace Store**| `GET /loginsell` | Refurbished electronics store |
| **Checkout** | `GET /q` | Order address & Cash on Delivery confirmation |
| **About Us** | `GET /about` | Mission, environmental standards, and certifications |
| **Contact Us** | `GET /contact` | Dedicated helpline, support inquiry form, team credits |

---

## 👨‍💻 Project Team & Contributors
- **Saurabh Bhandari** (Project Lead & Full Stack Developer)
- **S. Belhekar**
- **S. Andhar**
- **M. Bawadkar**

---

## 📄 License
This project is developed for academic, educational, and sustainable technology advancement.
