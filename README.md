# 💍 Naandi - Wedding & Event Management Platform

<div align="center">
  <img src="https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-5.8.3-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Vite-5.2.0-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
  <img src="https://img.shields.io/badge/Express-5.1.0-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express" />
  <img src="https://img.shields.io/badge/MongoDB-green?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/TailwindCSS-3.4.3-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind" />
</div>

<br/>

<p align="center">
  <strong>A comprehensive full-stack platform connecting wedding vendors with couples planning their special day</strong>
</p>

<p align="center">
  <a href="#✨-features">Features</a> •
  <a href="#🎬-screenshots">Screenshots</a> •
  <a href="#🛠️-tech-stack">Tech Stack</a> •
  <a href="#🚀-getting-started">Getting Started</a> •
  <a href="#📱-pages--routes">Pages & Routes</a>
</p>

---

## ✨ Features

### 🎭 Multi-Role System
- **Guest/Couple Portal**: Browse services, register, and plan weddings
- **Vendor Dashboard**: Manage profiles, services, and bookings
- **Admin Dashboard**: Platform management and oversight

### 💼 Vendor Management
- Complete vendor profile creation and editing
- Service category management (Catering, Photography, Venue, Decor, etc.)
- Portfolio showcase
- Contact and booking system

### 🔐 Authentication & Security
- JWT-based authentication
- Secure password hashing with bcryptjs
- Protected routes and role-based access control
- Session management with Zustand

### 🎨 Modern UI/UX
- Responsive design with TailwindCSS
- Smooth animations and transitions
- Mobile-first approach
- Intuitive navigation

### 🔍 Service Discovery
- Browse vendors by category
- Detailed service listings
- Vendor profiles with complete information
- Contact forms

---

## 🎬 Screenshots

> **Note**: Add screenshots of your application here to showcase each feature

### Home Page
![Home Page](#)
*Landing page with hero section and featured services*

### Categories Page
![Categories](#)
*Browse services by category - Catering, Photography, Venues, Decor, and more*

### Vendor Profile
![Vendor Profile](#)
*Detailed vendor information, services, and contact options*

### Admin Dashboard
![Admin Dashboard](#)
*Platform management and analytics*

### Vendor Dashboard
![Vendor Dashboard](#)
*Manage your business, services, and bookings*

### Wedding Planning
![Weddings](#)
*Plan and organize your perfect wedding day*

---

## 🛠️ Tech Stack

### Frontend
- **React 19.1.0** - UI library
- **TypeScript 5.8.3** - Type safety
- **Vite 5.2.0** - Build tool & dev server
- **React Router DOM 7.7.1** - Client-side routing
- **TailwindCSS 3.4.3** - Utility-first CSS
- **Zustand 5.0.6** - State management

### Backend
- **Express 5.1.0** - Node.js framework
- **MongoDB + Mongoose 8.17.0** - Database
- **JWT (jsonwebtoken 9.0.2)** - Authentication
- **bcryptjs 3.0.2** - Password hashing
- **CORS 2.8.5** - Cross-origin requests

### Development Tools
- **ESLint** - Code linting
- **PostCSS** - CSS processing
- **Autoprefixer** - CSS vendor prefixing

---

## 📱 Pages & Routes

| Route | Component | Description |
|-------|-----------|-------------|
| `/` | HomePage | Landing page with hero and services overview |
| `/categories` | CategoriesPage | Browse all service categories |
| `/services` | ServicesPage | View all available services |
| `/signin` | SignInPage | User authentication |
| `/register` | RegisterPage | New user registration |
| `/vendor` | VendorPage | Vendor listing |
| `/vendor/:id` | VendorProfilePage | Individual vendor details |
| `/weddings` | WeddingsPage | Wedding planning dashboard |
| `/admin` | AdminDashboard | Admin panel (protected) |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ installed
- MongoDB instance (local or cloud)
- npm or yarn package manager

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Naveenkumar2027/naandi.git
cd naandi
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
Create a `.env` file in the root directory:
```env
# Server
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=your_mongodb_connection_string

# JWT
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRE=7d

# CORS
CLIENT_URL=http://localhost:5173
```

4. **Run development servers**

**Frontend** (Vite dev server):
```bash
npm run dev
```
Runs on `http://localhost:5173`

**Backend** (Express server):
```bash
cd server
node index.js
```
Runs on `http://localhost:5000`

5. **Build for production**
```bash
npm run build
```

---

## 📂 Project Structure

```
naandi/
├── public/              # Static assets
├── server/              # Backend Express server
│   ├── models/          # MongoDB models
│   ├── routes/          # API routes
│   ├── controllers/     # Business logic
│   ├── middleware/      # Auth & validation
│   └── index.js         # Server entry
├── src/
│   ├── assets/          # Images, fonts, etc.
│   ├── components/      # Reusable React components
│   ├── contexts/        # React contexts
│   ├── pages/           # Route pages
│   │   ├── HomePage.tsx
│   │   ├── CategoriesPage.tsx
│   │   ├── ServicesPage.tsx
│   │   ├── SignInPage.tsx
│   │   ├── RegisterPage.tsx
│   │   ├── VendorPage.tsx
│   │   ├── VendorProfilePage.tsx
│   │   ├── WeddingsPage.tsx
│   │   └── AdminDashboard.tsx
│   ├── stores/          # Zustand state stores
│   ├── types/           # TypeScript type definitions
│   ├── App.tsx          # Root component
│   └── main.tsx         # Entry point
├── .env                 # Environment variables
├── package.json         # Dependencies
├── tailwind.config.cjs  # Tailwind configuration
├── tsconfig.json        # TypeScript config
└── vite.config.ts       # Vite configuration
```

---

## 🎯 Key Features Implementation

### State Management with Zustand
```typescript
// Simple, hooks-based state management
import create from 'zustand';

const useAuthStore = create((set) => ({
  user: null,
  setUser: (user) => set({ user }),
  logout: () => set({ user: null }),
}));
```

### Protected Routes
Role-based access control ensures only authenticated users access specific pages.

### Responsive Design
Mobile-first approach with TailwindCSS breakpoints for optimal viewing on all devices.

---

## 🔮 Future Enhancements

- [ ] Real-time chat between couples and vendors
- [ ] Advanced search filters (price, location, rating)
- [ ] Booking calendar system
- [ ] Payment gateway integration
- [ ] Review and rating system
- [ ] Email notifications
- [ ] Photo gallery with lightbox
- [ ] Multi-language support
- [ ] Analytics dashboard for vendors
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Developer

**Naveen Kumar**
- GitHub: [@Naveenkumar2027](https://github.com/Naveenkumar2027)
- Email: m.naveenkumar6360@gmail.com
- LinkedIn: [Connect with me](#)

---

## 🙏 Acknowledgments

- React team for the amazing library
- Vite for lightning-fast dev experience
- TailwindCSS for utility-first styling
- MongoDB for flexible data storage
- All contributors and supporters

---

<div align="center">
  <strong>⭐ Star this repo if you find it helpful! ⭐</strong>
</div>
