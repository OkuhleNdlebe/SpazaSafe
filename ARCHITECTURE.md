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
