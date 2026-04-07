# 📱 MicroStay Frontend

MicroStay Frontend is a high-performance, modern web application built with **React 19** and **Vite**. It provides a seamless user experience with real-time maps, fluid animations, and a responsive design.

---

## 🚀 Modern Tech Stack

- **Framework:** [React 19](https://react.dev/)
- **Build Tool:** [Vite (with Rolldown)](https://vite.dev/)
- **Styling:** [Tailwind CSS 4](https://tailwindcss.com/)
- **Animations:** [Framer Motion](https://www.framer.com/motion/)
- **Icons:** [Lucide React](https://lucide.dev/)
- **Maps:** [Leaflet](https://leafletjs.com/) & [React-Leaflet](https://react-leaflet.js.org/)
- **State Management:** React Hooks & Context API
- **Charts:** [Chart.js](https://www.chartjs.org/)

---

## ✨ Key Features

- **Interactive Stay Discovery:** Search hotels on an interactive map.
- **Dynamic Dashboards:** Visual revenue and booking analytics for hotel managers.
- **Smart Filtering:** Multi-criteria filtering (price range, amenities, city, etc.).
- **Photo Galleries:** Responsive image carousels for hotel rooms.
- **Seamless Auth:** Clean login/registration flow with Google OAuth integration.
- **Real-time Feedback:** Toast notifications and optimistic UI updates.

---

## 🛠️ Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

### Installation
```bash
# Install dependencies
npm install
```

### Development
```bash
# Start the development server
npm run dev
```
The app will be available at `http://localhost:5173`.

---

## 📂 Folder Structure

- `src/components/`: Reusable UI components (Modals, Cards, Navbars).
- `src/pages/`: Main application pages (Home, HotelDetails, Search).
- `src/assets/`: Static assets (Logos, SVGs).
- `src/context/`: Global state management.
- `src/services/`: API integration services using Axios.

---

## ⚙️ Configuration

The frontend connects to the Microservices via the **API Gateway** (`http://localhost:8080`). Ensure the backend services are running and accessible.
