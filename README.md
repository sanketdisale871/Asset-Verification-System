# Asset Verification System

A full-stack web application for automated hardware and peripheral asset verification across squadrons. Built as a hackathon project, it enables role-based workflows for finance teams, asset managers, and employees to track, verify, and manage IT and physical assets.

---

## Project Structure

```
.
├── Backend/    # Quarkus (Java 21) REST API with MySQL
└── UI1/        # React + TypeScript frontend (Vite)
```

---

## Features

- **Role-based dashboards** for Finance, Asset Manager, Employee, Network Equipment, Audio/Video, and Furniture roles
- **Asset verification campaigns** — create, assign, and review verification tasks
- **Peripheral assignment workflow** — guided flow for assigning peripherals to employees
- **Employee verification page** — employees can confirm their assigned assets
- **KPI cards & status badges** — at-a-glance metrics across asset categories
- **Excel export** — export asset data to spreadsheets
- **Session-based authentication** with protected routes per role

---

## Tech Stack

| Layer     | Technology                                      |
|-----------|-------------------------------------------------|
| Frontend  | React 18, TypeScript, Vite, Tailwind CSS        |
| UI Components | MUI (Material UI), Radix UI, Lucide Icons   |
| Backend   | Quarkus 3.30, Java 21, Hibernate ORM + Panache  |
| Database  | MySQL 8                                         |
| Email     | Quarkus Mailer (Gmail SMTP)                     |

---

## Prerequisites

- **Node.js** 18+
- **Java** 21+
- **Maven** 3.9+
- **MySQL** 8 running locally on port `3306`

---

## Getting Started

### 1. Database Setup

Ensure MySQL is running and a database named `squadron_db` exists (Quarkus will create it automatically if the user has the right permissions).

Default credentials (configurable in `Backend/src/main/resources/application.properties`):

```
username: root
password: root
```

### 2. Backend

```bash
cd Backend
./mvnw quarkus:dev
```

The API will be available at `http://localhost:8080`.  
The Quarkus Dev UI is accessible at `http://localhost:8080/q/dev/` in dev mode.

### 3. Frontend

```bash
cd UI1
npm install
npm run dev
```

The UI will be available at `http://localhost:5173` (or the port Vite assigns).

---

## User Roles

| Role               | Dashboard / Access                        |
|--------------------|-------------------------------------------|
| `finance`          | Finance Dashboard                         |
| `assetManager`     | Asset Manager Dashboard, Campaigns, Create Campaign |
| `employee`         | Employee Verification Page                |
| `networkEquipment` | Network Equipment Dashboard               |
| `audioVideo`       | Audio/Video Dashboard                     |
| `furniture`        | Furniture Dashboard                       |

---

## Building for Production

**Backend:**

```bash
cd Backend
./mvnw package
java -jar target/quarkus-app/quarkus-run.jar
```

**Frontend:**

```bash
cd UI1
npm run build
```

The compiled frontend will be in `UI1/dist/`.

---

## Related Links

- [Quarkus](https://quarkus.io/)
- [Figma Design](https://www.figma.com/design/VMSv9BkDCk5lGhLU7Brhir/Automated-Hardware-Verification-System)
