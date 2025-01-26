# Next.js Folder Structure

## Overview

This folder structure is organized using a modular structure, designed for scalability, maintainability, and separation of concerns. Below is a detailed breakdown of the folder structure:

## Folder Structure Details

### `src/`

The `src/` directory contains all the source code for the application, including pages, components, features, and utilities.

### `app/`

The `app/` directory houses the main application structure, including root layouts and pages for routing and rendering. It follows the Next.js 13 app directory convention for enhanced flexibility in organizing and managing pages.

- **`layout.tsx`**: Defines the root layout for the entire application.
- **`page.tsx`**: The root page for the application.
- **`(features)/`**: This folder contains dynamic features that are grouped logically by their functionality. These are routes for different areas of the application, such as dashboard, authentication, and patient management.

### `components/`

The `components/` directory contains reusable UI components, organized into various subfolders based on their functionality:

- **`forms/`**: Contains all form components like login and registration forms.
- **`layouts/`**: Defines layout components for different page structures.
- **`ui/`**: Includes common UI elements like buttons, modals, and spinners.
- **`tables/`**: Contains table components for displaying data like patients, appointments, and reports.
- **`headers/`**: Header components used throughout the application.
- **`navigation/`**: Navigation components like the sidebar and top navbar.
- **`charts/`**: Chart components for visualizing data.
- **`notifications/`**: Contains notification components like toast alerts and custom notifications.

### `config/`

The `config/` directory holds app-wide configurations, constants, and API client setup.

### `features/`

The `features/` directory is where the core business logic is implemented. Each feature (such as authentication, patient management, or appointments) has its own folder containing APIs, hooks, Redux slices, components, and types related to that feature.

### `hooks/`

Global custom hooks that provide reusable functionality across the application, such as data fetching, debouncing, pagination, and responsiveness hooks.

### `lib/`

The `lib/` folder contains shared utilities and helper functions used throughout the project:

- **`validation/`**: Zod schemas for validation.
- **`utils/`**: Utility functions like date formatting and ID generation.
- **`constants/`**: Common constants such as user roles and statuses.

### `store/`

The `store/` directory holds Redux store setup, including slices and typed hooks to interact with the state.

### `styles/`

The `styles/` directory contains all the styles for the project:

- **`themes/`**: Custom theme overrides for UI libraries (e.g., Ant Design).
- **`globals.css`**: Global CSS for basic styling.
- **`tailwind.css`**: Tailwind CSS setup if used in the project.
- **`variables.css`**: Custom CSS variables for design consistency.

### `tests/`

The `tests/` folder contains unit and integration tests, organized by their respective functionality. This ensures that the application’s features and components are thoroughly tested.

## Example Of Folder Structure

```
src/
├── app/                          # Next.js app directory
│   ├── layout.tsx                # Root layout for the app
│   ├── page.tsx                  # Root page for the app
│   └── (features)/               # Dynamic features grouped logically
│       ├── dashboard/
│       │   ├── layout.tsx        # Dashboard-specific layout
│       │   └── page.tsx          # Dashboard landing page
│       ├── auth/
│       │   ├── login/
│       │   │   └── page.tsx      # Login page
│       │   └── register/
│       │       └── page.tsx      # Register page
│       └── patients/
│           ├── list/
│           │   └── page.tsx      # List of patients
│           └── profile/
│               └── page.tsx      # Patient profile details
├── components/                   # Reusable UI components
│   ├── forms/                    # Form components
│   │   ├── LoginForm.tsx         # Login form
│   │   ├── RegisterForm.tsx      # Register form
│   │   ├── PatientForm.tsx       # Form for managing patients
│   │   └── AppointmentForm.tsx   # Form for scheduling appointments
│   ├── layouts/                  # Layout components
│   │   ├── MainLayout.tsx        # Main application layout
│   │   ├── SidebarLayout.tsx     # Layout with a sidebar
│   │   ├── AuthLayout.tsx        # Layout for authentication pages
│   │   └── DashboardLayout.tsx   # Layout for dashboard pages
│   ├── ui/                       # Common UI components
│   │   ├── Button.tsx            # Custom button component
│   │   ├── Modal.tsx             # Modal dialog
│   │   ├── Spinner.tsx           # Loading spinner
│   │   ├── Card.tsx              # Reusable card component
│   │   └── Badge.tsx             # Badge component
│   ├── tables/                   # Table components
│   │   ├── PatientTable.tsx      # Table for displaying patients
│   │   ├── AppointmentTable.tsx  # Table for displaying appointments
│   │   └── ReportTable.tsx       # Table for displaying reports
│   ├── headers/                  # Header components
│   │   ├── MainHeader.tsx        # Main header
│   │   ├── AuthHeader.tsx        # Header for authentication pages
│   │   └── DashboardHeader.tsx   # Header for the dashboard
│   ├── navigation/               # Navigation components
│   │   ├── Sidebar.tsx           # Sidebar navigation
│   │   ├── Navbar.tsx            # Top navigation bar
│   │   └── Breadcrumbs.tsx       # Breadcrumbs for navigation
│   ├── charts/                   # Chart components
│   │   ├── BarChart.tsx          # Bar chart
│   │   ├── LineChart.tsx         # Line chart
│   │   └── PieChart.tsx          # Pie chart
│   └── notifications/            # Notification components
│       ├── Toast.tsx             # Toast notifications
│       ├── Alert.tsx             # Alert component
│       └── NotificationList.tsx  # List of notifications
├── config/                       # App configuration and constants
│   ├── api.ts                    # Axios or API client configuration
│   ├── routes.ts                 # Centralized route definitions
│   └── settings.ts               # App-wide settings and constants
├── features/                     # Feature-specific logic
│   ├── auth/                     # Authentication feature
│   │   ├── api/                  # API calls for auth
│   │   │   └── authApi.ts
│   │   ├── hooks/                # Custom hooks for auth
│   │   │   ├── useLogin.ts
│   │   │   └── useLogout.ts
│   │   ├── slices/               # Redux slices for auth
│   │   │   └── authSlice.ts
│   │   ├── components/           # Auth-specific components
│   │   │   ├── ForgotPassword.tsx
│   │   │   └── ResetPassword.tsx
│   │   └── types/                # TypeScript types for auth
│   │       └── authTypes.ts
│   ├── patients/                 # Patient management feature
│   │   ├── api/                  # API calls for patients
│   │   │   └── patientApi.ts
│   │   ├── hooks/                # Custom hooks for patients
│   │   │   └── usePatientData.ts
│   │   ├── slices/               # Redux slices for patients
│   │   │   └── patientSlice.ts
│   │   └── components/           # Patient-specific components
│   │       ├── PatientCard.tsx
│   │       ├── PatientList.tsx
│   │       └── PatientDetails.tsx
│   ├── appointments/             # Appointment feature
│   │   ├── api/
│   │   │   └── appointmentApi.ts
│   │   ├── hooks/
│   │   │   └── useAppointments.ts
│   │   ├── slices/
│   │   │   └── appointmentSlice.ts
│   │   └── components/
│   │       ├── AppointmentCard.tsx
│   │       └── AppointmentList.tsx
│   └── reports/                  # Reports feature
│       ├── api/
│       │   └── reportApi.ts
│       ├── hooks/
│       │   └── useReportData.ts
│       ├── slices/
│       │   └── reportSlice.ts
│       └── components/
│           ├── ReportCard.tsx
│           └── ReportDetails.tsx
├── hooks/                        # Global custom hooks
│   ├── useRedux.ts               # Custom hook for Redux store
│   ├── useResponsive.ts          # Hook for responsive layouts
│   ├── useFetch.ts               # General data-fetching hook
│   ├── useDebounce.ts            # Debouncing hook for inputs
│   └── usePagination.ts          # Pagination hook
├── lib/                          # Shared utilities and helpers
│   ├── validation/               # Zod schemas for validation
│   │   ├── authSchema.ts
│   │   ├── patientSchema.ts
│   │   └── formSchema.ts
│   ├── utils/                    # Utility functions
│   │   ├── formatDate.ts         # Format date utility
│   │   ├── formatCurrency.ts     # Format currency utility
│   │   └── generateId.ts         # ID generator
│   └── constants/                # Application constants
│       ├── roles.ts              # User roles
│       └── statuses.ts           # Common statuses
├── store/                        # Redux store setup
│   ├── slices/                   # Redux slices
│   │   ├── authSlice.ts
│   │   ├── patientSlice.ts
│   │   └── appointmentSlice.ts
│   ├── hooks.ts                  # Typed Redux hooks
│   └── index.ts                  # Redux store configuration
├── styles/                       # Global and modular styles
│   ├── themes/                   # Ant Design theme overrides
│   │   └── customTheme.ts
│   ├── globals.css               # Global CSS
│   ├── tailwind.css              # Tailwind CSS (if used)
│   └── variables.css             # CSS variables
└── tests/                        # Unit and integration tests
    ├── components/               # Component tests
    ├── features/                 # Feature tests
    ├── hooks/                    # Hook tests
    └── utils/                    # Utility tests

```
