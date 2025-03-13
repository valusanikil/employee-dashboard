# 🏆 Spring Boot Backend – Employee Management System

This is a Spring Boot backend project for managing employee records. It provides a RESTful API for CRUD operations using Spring Data JPA, Hibernate, and MySQL.

---

## 📌 **Table of Contents**
1. [Project Overview](#project-overview)  
2. [Technologies Used](#technologies-used)  
3. [Setup Instructions](#setup-instructions)  
4. [API Endpoints](#api-endpoints)  
5. [Code Overview](#code-overview)  
6. [Testing](#testing)  

---

## 📖 **1. Project Overview**
This project is a backend service for an Employee Management System with CRUD operations, database persistence, and exception handling.

# home page
<img src="assets/Screenshot 2025-03-13 014433.png" alt="">

# update employee
<img src="assets/Screenshot 2025-03-13 014451.png" alt="">

# employee details
<img src="assets/Screenshot 2025-03-13 014505.png" alt="">


---

## 🚀 **2. Technologies Used**
| Technology | Description |
|-----------|-------------|
| **Java** | Programming language (v17+) |
| **Spring Boot** | Backend framework |
| **Spring Data JPA** | ORM framework for database interactions |
| **Hibernate** | ORM for mapping Java objects to tables |
| **MySQL** | Relational database |
| **Maven** | Build and dependency management |

---

## 🛠️ **3. Setup Instructions**
### **Clone the repository**:
```bash
git clone <repo-url>
```

### **Configure the database**:
Update `application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
spring.datasource.username=root
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
```

### **Run the project**:
```bash
./mvnw spring-boot:run
```

---

## 🌐 **4. API Endpoints**
| Method | Endpoint | Description |
|--------|----------|-------------|
| **GET** | `/api/employees` | Get all employees |
| **POST** | `/api/employees` | Create a new employee |
| **GET** | `/api/employees/{id}` | Get employee by ID |
| **PUT** | `/api/employees/{id}` | Update employee by ID |
| **DELETE** | `/api/employees/{id}` | Delete employee by ID |

---

## 🏗️ **5. Code Overview**
### **Employee.java** – Entity class  
```java
@Entity
@Table(name = "employees")
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String firstName;
    private String lastName;
    private String email;
}
```

### **EmployeeRepository.java** – Data access layer  
```java
@Repository
public interface EmployeeRepository extends JpaRepository<Employee, Long> {
}
```

### **EmployeeController.java** – REST controller  
```java
@RestController
@RequestMapping("/api/employees")
public class EmployeeController {
    @Autowired
    private EmployeeRepository employeeRepository;

    @GetMapping
    public List<Employee> getAllEmployees() {
        return employeeRepository.findAll();
    }
}
```

---

## ✅ **6. Testing**
- **Unit Testing:** Use `SpringbootBackendApplicationTests.java`  
- **API Testing:** Use Postman  

---
