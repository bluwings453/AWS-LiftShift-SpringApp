# 🚀 AWS-LiftShift-SpringApp

## 🌟 Introduction
Welcome to **AWS-LiftShift-SpringApp**, a **Lift & Shift** migration project in **AWS**. This project is designed to seamlessly migrate and deploy a high-performance web application using the **Spring Framework** while leveraging AWS cloud services for scalability, security, and efficiency. The application integrates **RabbitMQ, Memcached, and Elasticsearch** to enhance performance and ensure reliability.

---

## 📌 Prerequisites
- ☕ **JDK 11**
- 🛠 **Maven 3**
- 🗄 **MySQL 8**

---

## 🛠 Technologies Used
- 🌐 **Spring MVC**
- 🔐 **Spring Security**
- 🗃 **Spring Data JPA**
- ⚙️ **Maven**
- 🖥 **JSP**
- 🏗 **Tomcat**
- 🛢 **MySQL**
- 🏃 **Memcached**
- 📩 **RabbitMQ**
- 🔍 **Elasticsearch**

---

## 📂 Database Setup
The MySQL dump file is located at:
```
/src/main/resources/db_backup.sql
```
To import the dump into MySQL, run:
```bash
mysql -u <user_name> -p accounts < db_backup.sql
```

---

## ☁️ AWS Services Used
- 🖥 **EC2 Instances**
- ⚖ **Elastic Load Balancer (ELB)**
- 📈 **Auto Scaling**
- 📦 **EFS/S3 for Shared Storage**
- 🔐 **Amazon Certificate Manager**
- 🌍 **Route 53**

---

## 🏗 Infrastructure Configuration
- **VM for Tomcat, RabbitMQ, Memcached, MySQL**
- **Nginx as Load Balancer Replacement**
- **Automation for VM Scaling**
- **Shared Storage**
- **Private DNS Service**

---

## 🎯 Objectives
- ✅ **Seamless Lift & Shift Migration**
- ✅ **Flexible Infrastructure**
- ✅ **No Upfront Cost**
- ✅ **Effective Modernization**
- ✅ **Infrastructure as Code (IaaC)**

---

## 🚀 Flow of Execution
1. 🔑 **Login to AWS Account**
2. 🔐 **Create Key Pairs**
3. 🛡 **Create Security Groups**
4. 📜 **Launch Instances with User Data [Bash Scripts]**
5. 🌍 **Update IP to Name Mapping in Route 53**
6. 🏗 **Build Application from Source Code**
7. ☁️ **Upload to S3 Bucket**
8. 📥 **Download Artifact to Tomcat EC2 Instance**
9. 🔐 **Setup ELB with HTTPS [Certificate from Amazon Certificate Manager]**
10. 🔄 **Map ELB Endpoint to Website Name in GoDaddy DNS**
11. ✅ **Verify Deployment**

---

## 🚀 Setup Instructions
### 1️⃣ Clone Repository
```bash
git clone https://github.com/your-username/AWS-LiftShift-SpringApp.git
cd AWS-LiftShift-SpringApp
```

### 2️⃣ Build and Run with Maven
```bash
mvn clean package
java -jar target/aws-liftshift-springapp.jar
```

### 3️⃣ Deploy on Tomcat
1. Move the WAR file to Tomcat:
   ```bash
   cp target/aws-liftshift-springapp.war /opt/tomcat/webapps/
   ```
2. Restart Tomcat:
   ```bash
   sudo systemctl restart tomcat
   ```

### 4️⃣ Database Configuration
Edit `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/accounts
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
```

---

## 🌐 AWS Deployment
1. 🚀 **Launch EC2 instances** for Tomcat, MySQL, RabbitMQ, and Memcached.
2. ⚖ **Set up ELB** to distribute traffic.
3. 📈 **Configure Auto Scaling** for high availability.
4. 📦 **Use EFS/S3** for shared storage.
5. 🌍 **Set up Route 53** for DNS management.

---

## 🤖 DevOps Automation
- **Terraform**: Automate AWS resource provisioning.
- **Jenkins/GitHub Actions**: CI/CD pipeline for automated deployments.

---

## 📜 License
This project is licensed under the **MIT License**.

