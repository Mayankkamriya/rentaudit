# RentAudit Admin Dashboard

A comprehensive admin dashboard for managing car rental listings built with Next.js, TypeScript, and MongoDB.

## Features

### Core Features
- ✅ **Authentication System** - Secure login with JWT tokens
- ✅ **Dashboard Overview** - Statistics and recent activity
- ✅ **Listings Management** - Paginated table with filtering and search
- ✅ **Approval Workflow** - Approve, reject, or edit listings
- ✅ **Audit Trail** - Complete logging of all admin actions
- ✅ **Responsive Design** - Works on desktop and mobile

### Technical Features
- ✅ **Next.js 14** with App Router
- ✅ **TypeScript** for type safety
- ✅ **Tailwind CSS** for styling
- ✅ **MongoDB** for data persistence
- ✅ **JWT Authentication** with bcrypt password hashing
- ✅ **Server-Side Rendering** with getServerSideProps
- ✅ **Context API** for state management
- ✅ **React Hook Form** for form handling
- ✅ **Toast Notifications** for user feedback
- ✅ **Performance Optimizations** - Efficient re-rendering

## Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn
- MongoDB Atlas account

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Mayankkamriya/rentaudit.git
   cd rentaudit
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   MONGODB_URI=your mongo uri
   JWT_SECRET=jwt secret
   NEXTAUTH_SECRET=jwt secret
   NEXT_PUBLIC_BASE_URL=http://localhost:3000
   ```

4. **Seed with real data**
   ```bash
   npm run seed
   ```

5. **Run the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

### Demo Credentials
- **Email:** admin@rentaudit.com
- **Password:** admin123

## Project Structure

```
rentaudit/
├── components/          # Reusable React components
│   ├── Layout.tsx      # Main layout with navigation
│   └── EditListingModal.tsx
├── contexts/           # React Context providers
│   └── AuthContext.tsx
├── lib/               # Utility libraries
│   ├── mongodb.ts     # MongoDB connection
│   └── auth.ts        # Authentication utilities
├── pages/             # Next.js pages
│   ├── api/           # API routes
│   │   ├── auth/      # Authentication endpoints
│   │   ├── listings/  # Listings management
│   │   └── audit-logs/ # Audit trail
│   ├── dashboard.tsx  # Main dashboard
│   ├── listings.tsx   # Listings management
│   ├── audit-logs.tsx # Audit logs
│   └── login.tsx      # Login page
├── scripts/           # Database setup scripts
├── styles/            # Global styles
├── types/             # TypeScript type definitions
└── public/            # Static assets
```

## API Endpoints

### Authentication
- `POST /api/auth/login` - Admin login
- `GET /api/auth/verify` - Verify JWT token

### Admin Listings Management
- `GET /api/listings` - Get paginated listings with filters
- `GET /api/listings/[id]` - Get specific listing
- `PUT /api/listings/[id]` - Update listing or change status

### Public APIs
- `GET /api/public/listings` - Get approved listings (no auth required)
- `POST /api/listings/submit` - Submit new listing for approval

### Audit Logs
- `GET /api/audit-logs` - Get paginated audit logs with filters

### Database Seeding
- `npm run seed` - Seed with comprehensive real data

## Database Collections

### admins
- Admin user accounts with hashed passwords

### listings
- Car rental listings with status tracking

### auditLogs
- Complete audit trail of all admin actions

## Key Features Explained

### Authentication Flow
1. Admin enters credentials on login page
2. Server validates against MongoDB
3. JWT token generated and stored in localStorage
4. Token verified on each protected route

### Listing Management
1. View paginated listings with search and filters
2. Approve/reject pending listings
3. Edit listing details with form validation
4. All actions logged in audit trail

### Audit Trail
- Tracks all admin actions (approve, reject, edit)
- Records who performed what action and when
- Shows detailed changes for edit operations
- Filterable by action type and admin

### Performance Optimizations
- Efficient pagination to handle large datasets
- Optimistic UI updates for better UX
- Minimal re-renders with React.memo
- Server-side rendering for SEO and performance

## License

MIT License - see LICENSE file for details

## Support

For support, email mayankkamriya305@gmail.com or create an issue in the repository. 