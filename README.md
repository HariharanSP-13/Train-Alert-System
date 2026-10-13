# 🚆 Train Pulse - Train Alert & Management System

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-22.x-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.19-000000?logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)

A modern, full-stack railway companion web application designed to keep passengers informed in real-time. Features automated arrival notifications, destination proximity alarms, live train tracking, seat booking, and station platform navigation.

---

## 🌟 Key Features

- 🔔 **Multi-Channel Alert System**:
  - **Browser Desktop Notifications**: Receive timely alerts before approaching stations.
  - **Audio & Haptic Alerts**: Audible alert chimes and device vibration patterns.
  - **SMS Alerts via Twilio**: Automatic text notifications dispatched directly to user phones.
- 🚆 **Live Train Tracking**:
  - Real-time station progression and route map.
  - Estimated time of arrival (ETA), delay monitoring, and intermediate station timings.
- 🎫 **Ticket Booking**:
  - Search routes between stations, select coach classes, specify passengers, and view ticket confirmations.
- 📍 **Platform Locator & Station Guide**:
  - Look up assigned platforms and station facilities (waiting rooms, cloak rooms, food courts).
- 👤 **User Authentication & Dashboard**:
  - Register, log in, manage profile details, notification preferences, and saved journeys.
- 🛠️ **Admin Management Panel**:
  - Manage train routes, station master lists, and broadcast alerts.

---

## 📁 Project Architecture

The repository is organized into distinct **frontend** and **backend** applications:

```text
Train-Alert-System/
├── backend/                  # Express.js REST API & Database Services
│   ├── index.js              # Server entry point & API endpoints
│   ├── package.json          # Backend dependencies & scripts
│   └── package-lock.json
│
├── frontend/                 # React + TypeScript + Vite Single Page Application
│   ├── src/
│   │   ├── components/       # UI components & Shadcn/Radix UI widgets
│   │   ├── context/          # Auth and application state providers
│   │   ├── pages/            # View pages (Dashboard, Tracking, Booking, etc.)
│   │   ├── services/         # API clients (notification, train, database)
│   │   ├── App.tsx           # Application router & protected routes
│   │   └── main.tsx          # React application root
│   ├── index.html            # HTML entry point
│   ├── package.json          # Frontend dependencies & scripts
│   ├── tailwind.config.ts    # Tailwind styling tokens & theme
│   └── vite.config.ts        # Vite build config & backend API proxy
│
└── README.md                 # Project documentation
```

---

## 🛠️ Technology Stack

### Frontend
- **Framework:** React 18 with TypeScript
- **Bundler & Dev Server:** Vite
- **Styling:** Tailwind CSS, `tailwindcss-animate`
- **UI Components:** Radix UI primitives / Shadcn UI components
- **Icons:** Lucide React
- **Routing:** React Router DOM (v6)
- **Data Fetching:** TanStack React Query

### Backend
- **Runtime:** Node.js
- **Web Framework:** Express.js
- **Database:** MongoDB via Mongoose (with automatic fallback to mock database if offline)
- **SMS Gateway:** Twilio Node SDK
- **Cross-Origin Handling:** CORS

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [npm](https://www.npmjs.com/) (v9 or higher)
- [MongoDB](https://www.mongodb.com/) (Optional: runs in mock mode if MongoDB is not active)

---

### 1. Backend Setup

1. Open a terminal and navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. (Optional) Create a `.env` file in `backend/.env`:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/train_pulse
   TWILIO_ACCOUNT_SID=your_twilio_account_sid
   TWILIO_AUTH_TOKEN=your_twilio_auth_token
   TWILIO_PHONE_NUMBER=your_twilio_phone_number
   ```

4. Start the backend server:
   ```bash
   npm start
   ```
   > Server will run on: **http://localhost:5000**
   > Health check: **http://localhost:5000/api/health**

---

### 2. Frontend Setup

1. Open a second terminal and navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the Vite development server:
   ```bash
   npm run dev
   ```
   > The web app will launch at: **http://localhost:8080**
   > API requests (`/api/*`) are automatically proxied to the backend at `http://localhost:5000`.

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/health` | Health check returning server timestamp & MongoDB connection state |
| `POST` | `/api/send-sms` | Sends an SMS notification via Twilio (or logs to console in Demo Mode) |

#### Example: `/api/send-sms` Request Payload
```json
{
  "phoneNumber": "+1234567890",
  "message": "Train 12301 approaching New Delhi in 10 minutes!"
}
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to open an issue or submit a Pull Request.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
