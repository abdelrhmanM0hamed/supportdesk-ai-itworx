# SupportDesk AI

An AI-powered customer support desk built with **Spring Boot** and **Spring AI** — enabling agents and admins to manage tickets, orders, and refunds, with a RAG-based chatbot that answers customer queries using a dynamic knowledge base.

---

## Features

- **AI Chatbot** — Powered by Spring AI with OpenAI and Ollama integration; uses Retrieval-Augmented Generation (RAG) over a knowledge base to deliver context-aware responses
- **Ticket Management** — Full lifecycle support: create, assign, escalate, and resolve tickets with priority levels
- **Order & Product Management** — Browse a product catalog, place orders, and track order status
- **Refund Workflow** — Submit and process refund requests with approval/rejection logic
- **Knowledge Base** — Admins can create and manage KB articles that feed the AI chatbot
- **Role-Based Access Control** — Separate dashboards and permissions for Customers, Agents, and Admins
- **JWT Authentication** — Secure login and registration with stateless JWT tokens
- **Audit Logging** — All key actions are logged for traceability
- **Metrics Dashboard** — Summary view of system activity for admins

---

## Tech Stack

### Backend
| Layer | Technology |
|---|---|
| Framework | Spring Boot 4.1 |
| AI Integration | Spring AI (OpenAI + Ollama + Vector Store) |
| Security | Spring Security + JWT (jjwt) |
| Persistence | Spring Data JPA + MySQL |
| API | REST (Spring MVC) |
| Testing | JUnit 5 + Integration Tests |
| Build | Maven |

### Frontend
| Layer | Technology |
|---|---|
| Framework | React (Vite) |
| State | React Context API |
| Styling | CSS + Styled Components |

---

## Project Structure

```
supportdesk-ai/
├── backend/
│   └── src/
│       ├── main/java/com/itworx/supportdesk/
│       │   ├── config/          # AI config, data seeding, KB loader
│       │   ├── controller/      # REST endpoints
│       │   ├── service/         # Business logic + AI tools
│       │   ├── repository/      # JPA repositories
│       │   ├── model/           # Entities (User, Ticket, Order, ...)
│       │   ├── dto/             # Request/response DTOs
│       │   ├── security/        # JWT filter, auth service, config
│       │   └── exception/       # Global exception handling
│       └── test/                # Integration tests
└── frontend/
    └── src/
        ├── pages/               # Admin, Agent, Auth, Orders, Tickets
        ├── components/          # Shared UI components
        └── context/             # Auth, Orders, Products context
```

---

## Getting Started

### Prerequisites
- Java 17+
- Maven
- MySQL
- Node.js 18+ (for frontend)
- An OpenAI API key **or** a running Ollama instance

### Backend Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/supportdesk-ai-itworx.git
   cd supportdesk-ai-itworx/backend
   ```

2. Configure `src/main/resources/application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/supportdesk
   spring.datasource.username=YOUR_DB_USER
   spring.datasource.password=YOUR_DB_PASSWORD

   # OpenAI
   spring.ai.openai.api-key=YOUR_OPENAI_KEY

   # JWT
   app.jwt.secret=YOUR_JWT_SECRET
   ```

3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```

### Frontend Setup

```bash
cd frontend
cp .env.example .env      # set VITE_API_URL to your backend URL
npm install
npm run dev
```

---

## API Overview

| Module | Base Path |
|---|---|
| Auth | `/api/auth` |
| Tickets | `/api/tickets` |
| Orders | `/api/orders` |
| Products | `/api/products` |
| Refunds | `/api/refunds` |
| Knowledge Base | `/api/kb` |
| Chatbot | `/api/chat` |
| Metrics | `/api/metrics` |
| Audit Logs | `/api/audit` |

---

## Developed During

ITworx Internship Program — Java Backend Track, Jul 2026 – Aug 2026
