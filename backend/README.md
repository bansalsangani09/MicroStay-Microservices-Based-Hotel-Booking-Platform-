# ⚙️ MicroStay Backend Services

The MicroStay backend is built on a Spring Cloud microservices architecture, providing a scalable and resilient infrastructure for hotel booking operations.

---

## 🏗️ Services & Ports

| Service Name | Port | Description | Database |
| :--- | :--- | :--- | :--- |
| **Discovery Server** | `8761` | Netflix Eureka for service registration. | N/A |
| **API Gateway** | `8080` | Entry point with global CORS and Rate Limiting. | Redis |
| **User Service** | `8081` | Handles Auth, OAuth2, and User profiles. | MySQL (`microstay_users`) |
| **Hotel Service** | `8082` | Hotel/Room data and AI reviews (Gemini). | MongoDB (`hotel_db`) |
| **Booking Service** | `8083` | Reservation management and Feign client. | MySQL (`microstay_booking`) |
| **Payment Service** | `8084` | Secure payment transaction handling. | MySQL (`microstay_payment`) |

---

## 🛠️ Prerequisites

Ensure you have the following installed and running:

1. **Java 17+** (OpenJDK recommended)
2. **Maven 3.8+**
3. **MySQL 8.0+**
4. **MongoDB 6.0+**
5. **Redis** (for Rate Limiting)

---

## 🚀 Startup Sequence

To ensure services register correctly, follow this startup order:

1. **Discovery Server:** Start `discoveryServer` first. Wait until it's accessible at `http://localhost:8761`.
2. **Databases:** Ensure MySQL, MongoDB, and Redis are running.
3. **Core Services:** Start `userService`, `hotelService`, `bookingService`, and `paymentService` in any order.
4. **API Gateway:** Start `apiGateway` last to route traffic to the registered services.

### How to Run (Using Terminal)
```bash
# Navigate to the service folder
cd backend/[service-name]

# Run the project
mvn spring-boot:run
```

---

## 🔐 Security & Auth Flow

1. **Social Login:** Handled via Google OAuth2 in `userService`.
2. **Stateless Auth:** Upon login, a **JWT token** is issued.
3. **Gateway Enforcement:** API Gateway validates JWTs for protected routes (e.g., `/api/admin/**`).
4. **Rate Limiting:** Redis-based rate limiting is applied at the Gateway level to prevent abuse.

---

## 📋 Environment Configuration

Each service has an `application.yaml` for configuration. Key parameters:
- `spring.datasource.url`: MySQL connection string.
- `spring.data.mongodb.uri`: MongoDB connection string.
- `spring.data.redis.host`: Redis host.
- `gemini.api.key`: Google Gemini API key (Required for AI features in `hotelService`).
