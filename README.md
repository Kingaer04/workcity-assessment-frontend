# Hospital Management System (HMS) - Frontend

A modern Hospital Management System frontend built with React and Vite. This system provides an intuitive user interface for hospital administrators and staff members to manage hospital operations efficiently.

## Features

### Admin Features
- Admin login/logout
- Dashboard with system overview
- Add new staff members with form validation
- View all staff members in a table/list format
- Delete existing staff members with confirmation
- Search and filter staff members

### Staff Features
- Staff login/logout (default password: phone number)
- Personal dashboard with profile overview
- Edit personal profile information
- View and update personal details
- Change password functionality

## Tech Stack

- **Frontend Framework:** React 18
- **Build Tool:** Vite
- **Styling:** CSS3 / Tailwind CSS (or your preferred styling solution)
- **HTTP Client:** Axios
- **Routing:** React Router DOM
- **State Management:** React Context API / Redux (if used)
- **Form Handling:** React Hook Form (if used)
- **UI Components:** Custom components / Material-UI / Chakra UI (if used)

## Prerequisites

Before running this application, make sure you have the following:

- Node.js (v16 or higher)
- npm or yarn package manager
- Backend server running (HMS Backend)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Kingaer04/workcity-assessment-frontend.git
   cd workcity-assessment-frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory and add the following variables:
   ```env
   VITE_API_BASE_URL=http://localhost:5500
   VITE_APP_NAME=Hospital Management System
   VITE_NODE_ENV=development
   ```

4. **Run the application**
   ```bash
   # Development mode
   npm run dev
   
   # Build for production
   npm run build
   
   # Preview production build
   npm run preview
   ```

The application will start on `http://localhost:5173` (default Vite port).

## API Integration

The frontend communicates with the backend through the following endpoints:

### Authentication
- `POST /api/auth/admin/login` - Admin login
- `POST /api/auth/staff/login` - Staff login
- `POST /api/auth/logout` - User logout

### Admin Operations
- `GET /api/admin/staff` - Fetch all staff members
- `POST /api/admin/staff` - Create new staff member
- `DELETE /api/admin/staff/:id` - Delete staff member

### Staff Operations
- `GET /api/staff/profile` - Get staff profile
- `PUT /api/staff/profile` - Update staff profile

## Component Structure

### Admin Components
- `AdminLogin` - Admin authentication form
- `AdminDashboard` - Main admin dashboard
- `StaffList` - Display all staff members
- `AddStaff` - Form to add new staff members
- `StaffCard` - Individual staff member card

### Staff Components
- `StaffLogin` - Staff authentication form
- `StaffDashboard` - Staff member dashboard
- `ProfileEdit` - Edit profile information
- `ProfileView` - View profile details

### Shared Components
- `Navbar` - Navigation component
- `Sidebar` - Side navigation
- `Loading` - Loading spinner/skeleton
- `ErrorBoundary` - Error handling component
- `ProtectedRoute` - Route protection wrapper

## User Authentication Flow

### Admin Flow
1. Admin navigates to `/admin/login`
2. Enters email and password
3. On successful login, redirected to `/admin/dashboard`
4. Can access all admin features

### Staff Flow
1. Staff navigates to `/staff/login`
2. Enters email and phone number (default password)
3. On successful login, redirected to `/staff/dashboard`
4. Can view and edit profile information

## Routing Structure

```
/                          - Landing page
/admin/login              - Admin login
/admin/dashboard          - Admin dashboard
/admin/staff              - Staff management
/admin/staff/add          - Add new staff
/staff/login              - Staff login
/staff/dashboard          - Staff dashboard
/staff/profile            - Staff profile
/staff/profile/edit       - Edit staff profile
```

## State Management

The application uses React Context API for global state management:

- `AuthContext` - Manages authentication state
- `StaffContext` - Manages staff data and operations
- `ThemeContext` - Manages UI theme preferences (if implemented)

## Form Validation

All forms include client-side validation:

- Email format validation
- Required field validation
- Phone number format validation
- Password strength requirements
- Real-time validation feedback

## Security Features

- Protected routes with authentication checks
- Automatic logout on token expiration
- Input sanitization and validation
- Secure API communication
- Role-based access control

## Default Credentials

### Admin Account
- Email: `admin@hospital.com`
- Password: `admin123`

### Staff Accounts
- Email: As provided by admin
- Password: Phone number (should be changed after first login)

## Scripts

```json
{
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview",
  "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0"
}
```

## Project Structure

```
Frontend/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   ├── admin/
│   │   │   ├── AdminDashboard.jsx
│   │   │   ├── AdminLogin.jsx
│   │   │   ├── StaffList.jsx
│   │   │   └── AddStaff.jsx
│   │   ├── staff/
│   │   │   ├── StaffDashboard.jsx
│   │   │   ├── StaffLogin.jsx
│   │   │   ├── ProfileView.jsx
│   │   │   └── ProfileEdit.jsx
│   │   ├── shared/
│   │   │   ├── Navbar.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── Loading.jsx
│   │   │   └── ProtectedRoute.jsx
│   ├── context/
│   │   ├── AuthContext.jsx
│   │   └── StaffContext.jsx
│   ├── hooks/
│   │   ├── useAuth.js
│   │   └── useApi.js
│   ├── services/
│   │   ├── api.js
│   │   ├── authService.js
│   │   └── staffService.js
│   ├── utils/
│   │   ├── helpers.js
│   │   └── constants.js
│   ├── styles/
│   │   ├── index.css
│   │   └── components.css
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── .env
├── .gitignore
├── package.json
├── vite.config.js
└── README.md
```

## Development Guidelines

### Code Style
- Use functional components with hooks
- Follow React best practices
- Use meaningful component and variable names
- Implement proper error handling
- Add loading states for better UX

### Performance Optimization
- Lazy loading for route components
- Memoization for expensive calculations
- Image optimization
- Bundle size optimization with Vite

## Deployment

### Build for Production
```bash
npm run build
```

### Deploy to Netlify/Vercel
1. Connect your GitHub repository
2. Set build command: `npm run build`
3. Set publish directory: `dist`
4. Add environment variables in deployment settings

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Future Enhancements

- [ ] Dark/Light theme toggle
- [ ] Mobile responsive design improvements
- [ ] Real-time notifications
- [ ] Advanced filtering and search
- [ ] Data export functionality
- [ ] Multi-language support
- [ ] Progressive Web App (PWA) features
