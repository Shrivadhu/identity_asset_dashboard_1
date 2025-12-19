# Identity Asset Dashboard

A modern, production-grade frontend dashboard for managing identity assets including SSL/TLS certificates, SSH keys, code signing keys, and audit logs.

![Dashboard Preview](https://img.shields.io/badge/React-18-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Status](https://img.shields.io/badge/status-production-success)

## 📋 Overview

The Identity Asset Dashboard is a single-page application (SPA) built with React 18 that provides a comprehensive interface for managing security credentials and monitoring access logs. It features a clean, professional design with dark mode support and full offline capability.

## ✨ Features

### 🔐 Core Modules

- **📜 Certificates Management**
  - View and manage SSL/TLS certificates
  - Filter by domain
  - Sort by expiry date
  - Status tracking (active/expired/expiring)
  - Pagination support
  - View certificate details in modal
  - Edit certificates via drawer interface

- **🔑 SSH Keys Management**
  - View SSH key inventory
  - Search by owner or fingerprint
  - Trust level indicators (high/medium/low)
  - Expandable rows showing associated servers
  - Smooth animations

- **✍️ Code Signing Keys**
  - Manage code signing keys
  - Toggle between table and grid views
  - Protection level indicators (HSM/Software)
  - Algorithm and metadata display
  - Visual card-based grid layout

- **📊 Audit Logs**
  - Comprehensive audit trail
  - Filter by action type
  - Infinite scrolling
  - Expandable rows with JSON metadata
  - Formatted JSON display

### 🎨 UI/UX Features

- ✅ **Dark Mode** - Toggle between light and dark themes
- ✅ **Responsive Design** - Works on desktop and tablet
- ✅ **Loading Skeletons** - Professional loading states
- ✅ **Smooth Animations** - Polished transitions throughout
- ✅ **LocalStorage Caching** - Instant load with cached data
- ✅ **Modal & Drawer Components** - Clean interaction patterns
- ✅ **Expandable Rows** - Show additional information inline

## 🏗️ Technology Stack

- **React 18** - Modern UI library
- **Vanilla JavaScript** - No build tools required
- **CSS Variables** - Theming system
- **LocalStorage API** - Client-side persistence
- **Babel Standalone** - In-browser JSX transformation

## 🎯 Architecture

### Component Structure

```
App
├── Sidebar (Navigation)
├── TopBar (Theme toggle, User avatar)
└── Content Area
    ├── Certificates Module
    │   ├── Filter & Pagination
    │   ├── Data Table
    │   ├── View Modal
    │   └── Edit Drawer
    ├── SSH Keys Module
    │   ├── Search
    │   └── Expandable Rows
    ├── Code Signing Keys Module
    │   ├── View Toggle (Table/Grid)
    │   └── Protection Level Indicators
    └── Audit Logs Module
        ├── Action Filters
        ├── Infinite Scroll
        └── JSON Metadata Display
```

### State Management

- **Local State** - Component-level state with React hooks
- **LocalStorage** - Persistent data across sessions
- **Custom Hooks** - `useLocalStorage` for automatic persistence
- **Memoization** - `useMemo` for optimized filtering/sorting

## 📦 Installation

### Option 1: Direct Download (Recommended)

1. Download `dashboard-working.html`
2. Open directly in your browser
3. Done! No installation required

### Option 2: Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/identity-asset-dashboard.git
cd identity-asset-dashboard

# Serve with any static server
python -m http.server 8000
# OR
npx serve

# Open http://localhost:8000/dashboard-working.html
```

### Option 3: Deploy to Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

Or use the Vercel Dashboard:
1. Go to [vercel.com](https://vercel.com)
2. Import your GitHub repository
3. Deploy!

## 🎨 Design Philosophy

The dashboard features a **refined, professional aesthetic** that avoids generic admin interface patterns:

- **Typography**: Outfit font family for modern, clean readability
- **Color System**: CSS variables for consistent theming
- **Spatial Design**: Generous whitespace with intentional density
- **Motion**: Purposeful animations for state transitions
- **Dark Mode**: Carefully chosen contrast ratios

## 💾 Data Structure

The application uses mock JSON data stored in localStorage:

```javascript
{
  certificates: [
    {
      id: 1,
      name: "wildcard.example.com",
      domain: "*.example.com",
      issuer: "Let's Encrypt",
      status: "active",
      expiryDate: "2026-03-15"
    }
    // ...more certificates
  ],
  sshKeys: [...],
  codeSigningKeys: [...],
  auditLogs: [...]
}
```

## 🎥 Demo Video

Create a 3-5 minute demo showing:

1. **Navigation** (30s) - Show all modules and dark mode
2. **Certificates** (60s) - Filter, sort, pagination, modal, drawer
3. **SSH Keys** (45s) - Search, expand rows
4. **Code Signing** (45s) - Toggle views, protection levels
5. **Audit Logs** (45s) - Filter, infinite scroll, JSON metadata
6. **Technical** (30s) - Refresh to show caching, responsive behavior

## 📊 Feature Checklist

### ✅ Global Layout
- [x] Left sidebar navigation
- [x] Top bar with user menu and theme toggle
- [x] Responsive design for desktop and tablet

### ✅ Certificates Module
- [x] Filter by domain
- [x] Sort by expiry date
- [x] Pagination (5 items per page)
- [x] Status badges (active/expired/expiring)
- [x] View modal with certificate details
- [x] Edit drawer for updating fields

### ✅ SSH Keys Module
- [x] Debounced search functionality
- [x] Sort by trust level
- [x] Trust level color indicators
- [x] Expandable rows showing associated servers
- [x] Smooth expand/collapse animations

### ✅ Code Signing Keys Module
- [x] Toggle between grid and table views
- [x] Grid cards with protection level icons
- [x] Protection level styling (HSM vs Software)
- [x] Algorithm and metadata display

### ✅ Audit Logs Module
- [x] Filter by action type
- [x] Infinite scrolling (no pagination)
- [x] Row expansion for JSON metadata
- [x] Formatted JSON display

### ✅ Cross-Cutting Features
- [x] LocalStorage caching for all modules
- [x] Loading skeletons for all data views
- [x] Dark mode with persistence
- [x] Smooth transitions and animations
- [x] State-based routing

## 🔧 Technical Decisions

### Why Single HTML File?

- **Simplicity** - No build process required
- **Portability** - Easy to deploy anywhere
- **Performance** - Everything loads from one file
- **Demo-friendly** - Perfect for assessments and demos

### Why Custom CSS vs Framework?

- **Full Control** - Complete control over design system
- **Performance** - No unused CSS
- **Uniqueness** - Avoids framework look-and-feel
- **Learning** - Demonstrates CSS skills

### Why No React Router?

- **Compatibility** - Avoids CDN/version conflicts
- **Simplicity** - State-based routing is more reliable
- **File Protocol** - Works when opened as `file://`
- **Performance** - Faster initial load

## 🚀 Performance

- **First Contentful Paint** - < 1s
- **Time to Interactive** - < 2s
- **Bundle Size** - Self-contained single file
- **Caching** - LocalStorage for instant subsequent loads

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built as a technical assessment for frontend engineering
- Designed to demonstrate modern React patterns
- Showcases professional UI/UX design
- Emphasizes clean, maintainable code

