# ARCHITECTURE.md

## 1. Project Title
**SpazaSafe: Counterfeit & Expired Product Detection System**

## 2. Domain
**Informal Retail & Consumer Safety**  
SpazaSafe operates within the informal retail sector, aiming to enhance product authenticity and safety in Spaza shops across South Africa. The system integrates QR codes, suppliers, shop owners, and regulatory bodies to ensure safe and legitimate products are sold.

## 3. Problem Statement
Spaza shops often sell expired or counterfeit products due to weak supply chain transparency. Consumers face health risks, and legitimate suppliers lose revenue. SpazaSafe addresses this issue by providing QR-based product authentication, supplier verification, and regulatory tracking.

## 4. C4 Architectural Diagrams

### 4.1 Context Diagram
Illustrates how SpazaSafe interacts with different users and external systems.

```mermaid
C4Context
  Person(shopOwner, "Spaza Shop Owner", "Scans QR Codes to verify products")
  Person(consumer, "Consumer", "Checks product authenticity before purchase")
  System(spazaSafe, "SpazaSafe System", "Ensures product authenticity and tracks supply chain")
  Person(supplier, "Supplier", "Registers products and ensures authenticity")
  Person(regulator, "Regulator", "Audits and verifies product compliance")

  shopOwner --> spazaSafe : Scans QR Codes
  consumer --> spazaSafe : Scans QR Codes
  supplier --> spazaSafe : Registers Products
  regulator --> spazaSafe : Audits Compliance
```

### 4.2 Container Diagram
Breaks the system into major components (backend, frontend, database, integrations).

```mermaid
C4Container
  System(spazaSafe, "SpazaSafe System", "Product verification and tracking")
  Container(webApp, "Frontend (React/Vue)", "User Interface for shops and consumers")
  Container(backend, "Backend (Laravel API)", "Handles business logic and verification")
  ContainerDb(database, "MySQL Database", "Stores product and shop data")
  Container(qrAPI, "QR Code API", "Handles QR code generation and verification")

  webApp --> backend : API Requests
  backend --> database : Reads/Writes Data
  backend --> qrAPI : QR Code Validation
```

### 4.3 Component Diagram
Details key components within the system.

```mermaid
C4Component
  Container(backend, "Backend (Laravel API)", "Handles business logic and verification")
  Component(authService, "Authentication Service", "Manages user authentication")
  Component(productService, "Product Verification", "Ensures products are authentic")
  Component(deliveryService, "Delivery Tracking", "Tracks product movements")
  Component(qrService, "QR Code Service", "Generates and verifies QR codes")

  backend --> authService : User Authentication
  backend --> productService : Product Verification
  backend --> deliveryService : Tracks Deliveries
  backend --> qrService : QR Code Processing
```

### 4.4 Code Diagram (Level 4 - Code Structure)
Defines high-level structure for Laravel application.

```mermaid
C4Component
  Component(laravelApp, "Laravel Application", "Handles business logic")
  Component(authController, "Auth Controller", "Handles user authentication")
  Component(productController, "Product Controller", "Manages product-related logic")
  Component(qrCodeController, "QR Code Controller", "Processes QR codes")
  Component(database, "MySQL Database", "Stores application data")

  laravelApp --> authController
  laravelApp --> productController
  laravelApp --> qrCodeController
  authController --> database
  productController --> database
  qrCodeController --> database
```

---
This document provides a clear architectural overview of SpazaSafe using the **C4 model** with **Mermaid syntax**. Let me know if you need modifications! 🚀
