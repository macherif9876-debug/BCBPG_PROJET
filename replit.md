# AURA Marketplace

## Overview

AURA is a mobile-first e-commerce marketplace platform targeting Senegal and Guinea. Built with Flask and Supabase, it provides a complete shopping experience with user authentication, product browsing, cart functionality, and multi-role admin capabilities. The platform supports regular customers, merchants (commercants), and super administrators with distinct access levels and dashboards.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Backend Architecture
- **Framework**: Flask (Python web framework)
- **Authentication**: Session-based authentication with role-based access control
- **Decorators**: Custom decorators for route protection (`login_required`, `admin_access_required`, `merchant_required`)
- **Role System**: Three-tier user roles - `super_admin`, `commercant` (merchant), and regular users
- **Environment**: Uses python-dotenv for configuration management

### Frontend Architecture
- **Templating**: Jinja2 templates with a base template inheritance pattern (`base.html`)
- **Styling**: Tailwind CSS via CDN with custom CSS variables for theming
- **Design System**: Premium/luxury aesthetic with gold (#D4AF37) and navy blue (#0A192F) color scheme
- **Mobile-First**: Responsive design optimized for mobile devices with bottom navigation
- **Icons**: Font Awesome for iconography
- **Charts**: Chart.js for analytics visualization in admin panels

### Template Structure
- `base.html`: Main layout with header, navigation, and footer
- `home.html`: Product discovery and featured items
- `categories.html`: Category browsing with animated transitions
- `panier.html`: Shopping cart functionality
- `compte.html`: User account management with role-specific options
- `login.html` / `signup.html`: Authentication pages
- `admin_super.html`: Super administrator control panel
- `admin_commercant.html`: Merchant dashboard with inventory management
- `inscription_commercant.html`: Merchant verification/onboarding

### Data Model (Inferred from code)
- **profil**: User profiles with role, name, email, and region association
- **regions**: Geographic regions for localization
- **pays**: Countries (Senegal, Guinea)
- Products, orders, and payment tracking (referenced but not fully visible)

## External Dependencies

### Database & Backend Services
- **Supabase**: Primary backend-as-a-service providing:
  - PostgreSQL database
  - Authentication infrastructure
  - Storage buckets for user assets (avatars, merchant verification documents)
  - Real-time capabilities

### Python Packages
- `supabase`: Supabase Python client
- `python-dotenv`: Environment variable management
- `flask`: Web framework
- `flet`: Listed but purpose unclear (possibly for future mobile app)
- `mcp`: Listed but purpose unclear

### Frontend CDNs
- Tailwind CSS (styling)
- Chart.js (analytics charts)
- Font Awesome (icons)
- Google Fonts (Plus Jakarta Sans, Syncopate)

### Environment Variables Required
- `SUPABASE_URL`: Supabase project URL
- `SUPABASE_KEY`: Supabase anonymous/service key
- `FLASK_SECRET_KEY`: Session encryption key