# Clinical Trials Management System

This project has been transformed from a CoreUI admin template into a Clinical Trials Management System.

## Overview

A comprehensive management system for clinical trials with the following modules:
- **Trial Management** - Create and manage clinical trials, protocols, and phases
- **Patient Management** - Handle patient enrollment, consent forms, and demographics
- **Site Management** - Manage research sites, investigators, and site staff
- **Document Management** - Organize protocols, regulatory documents, and case report forms
- **User Management** - Control user access and permissions
- **Roles Management** - Define and manage user roles and permissions

## Key Changes Made

### 1. Navigation Structure ([src/_nav.js](src/_nav.js))
- Removed all demo menu items
- Added Clinical Trials specific menu sections:
  - Dashboard
  - Trial Management (All Trials, Create New Trial, Protocols)
  - Patient Management (All Patients, Enrollment, Consent Forms)
  - Site Management (All Sites, Investigators, Site Staff)
  - Document Management
  - User Management
  - Roles Management

### 2. Routes ([src/routes.js](src/routes.js))
- Removed all demo routes
- Added clinical trials routes for all new modules

### 3. New View Components Created

#### Trial Management
- `src/views/trials/AllTrials.js` - List all clinical trials
- `src/views/trials/CreateTrial.js` - Form to create new trials
- `src/views/trials/Protocols.js` - Manage trial protocols

#### Patient Management
- `src/views/patients/AllPatients.js` - List all enrolled patients
- `src/views/patients/Enrollment.js` - Patient enrollment form
- `src/views/patients/ConsentForms.js` - Manage consent forms

#### Site Management
- `src/views/sites/AllSites.js` - List research sites
- `src/views/sites/Investigators.js` - Manage principal investigators
- `src/views/sites/SiteStaff.js` - Manage site staff members

#### Document Management
- `src/views/documents/Documents.js` - Document repository

#### Administration
- `src/views/administration/UserManagement.js` - Manage system users
- `src/views/administration/RolesManagement.js` - Manage user roles and permissions

### 4. Dashboard ([src/views/dashboard/Dashboard.js](src/views/dashboard/Dashboard.js))
Updated with clinical trials metrics:
- Active Trials count
- Total Enrolled patients
- Active Sites count
- Average Enrollment percentage
- Patient Enrollment Progress
- Recent Clinical Trials table

### 5. Removed Unused Components
Deleted the following demo folders and files:
- `src/views/base/` - Base component examples
- `src/views/buttons/` - Button examples
- `src/views/charts/` - Chart examples
- `src/views/forms/` - Form examples
- `src/views/icons/` - Icon examples
- `src/views/notifications/` - Notification examples
- `src/views/theme/` - Theme examples
- `src/views/widgets/` - Widget examples
- `src/components/DocsComponents.js`
- `src/components/DocsExample.js`
- `src/components/DocsIcons.js`
- `src/components/DocsLink.js`
- `src/scss/examples.scss`

### 6. Package Configuration ([package.json](package.json))
- Updated name to: `clinical-trials-management-system`
- Updated version to: `1.0.0`
- Updated description to reflect clinical trials purpose
- Removed unnecessary repository and author information

### 7. App Configuration ([src/App.js](src/App.js))
- Removed import for `examples.scss`

## Getting Started

### Installation
```bash
npm install
```

### Development
```bash
npm start
```
The application will run on http://localhost:3000

### Build for Production
```bash
npm run build
```

## Next Steps

To fully implement the Clinical Trials Management System, you should:

1. **Backend Integration**
   - Connect to a backend API for data persistence
   - Implement authentication and authorization
   - Add API endpoints for CRUD operations

2. **Data Models**
   - Define comprehensive data models for trials, patients, sites, etc.
   - Implement data validation

3. **Enhanced Features**
   - Add search and filtering capabilities
   - Implement pagination for large datasets
   - Add data export functionality (CSV, PDF)
   - Implement file upload for documents
   - Add audit trails and logging

4. **Security**
   - Implement role-based access control (RBAC)
   - Add secure authentication (OAuth, JWT)
   - Implement data encryption for sensitive information
   - Add HIPAA compliance features

5. **Reporting**
   - Create dashboards with charts and visualizations
   - Add report generation capabilities
   - Implement custom reports

6. **Compliance**
   - Add regulatory compliance features (FDA 21 CFR Part 11, GCP)
   - Implement electronic signatures
   - Add version control for documents

## Features Available

All components currently use mock data for demonstration. Each module includes:
- ✅ List views with tables
- ✅ Status badges
- ✅ Action buttons (View, Edit, Delete)
- ✅ Form layouts for data entry
- ✅ Responsive design
- ✅ Clean, professional UI

## Current Module Status

| Module | Status | Notes |
|--------|--------|-------|
| Dashboard | ✅ Complete | Shows key metrics with mock data |
| Trial Management | ✅ Complete | All Trials, Create, Protocols |
| Patient Management | ✅ Complete | Patients, Enrollment, Consent Forms |
| Site Management | ✅ Complete | Sites, Investigators, Staff |
| Document Management | ✅ Complete | Document repository |
| User Management | ✅ Complete | User list and management |
| Roles Management | ✅ Complete | Role definitions and permissions |

## Technology Stack

- **React** 19.2.3
- **CoreUI React** 5.9.2
- **React Router** 7.11.0
- **Redux** 5.0.1
- **Vite** 7.3.0

## License

MIT
