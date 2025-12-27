# DataTable Component - Modern Table with Shadcn-Inspired Design

I've created a custom, reusable **DataTable** component with a modern, clean UI inspired by shadcn design principles.

## 🎯 What's New

### Custom DataTable Component
**Location:** `src/components/DataTable/`

A fully-featured, modern table component that includes:

#### ✨ Features
- **🔍 Search** - Real-time search across all columns
- **🔀 Sorting** - Click column headers to sort ascending/descending
- **📄 Pagination** - Smart pagination with configurable items per page
- **🎨 Modern UI** - Clean, minimal design with smooth transitions
- **📱 Responsive** - Works perfectly on all screen sizes
- **🎭 Custom Rendering** - Render badges, buttons, or any JSX in cells
- **🌓 Dark Mode** - Automatically adapts to light/dark themes
- **♿ Accessible** - Semantic HTML and keyboard navigation

### Updated Components

#### AllTrials.js
The Clinical Trials table now uses the new DataTable component with:
- Search functionality
- Sortable columns
- Pagination (5 items per page)
- Custom badge rendering for status
- Action buttons for each row
- 10 sample trials for demo

## 🚀 Quick Start

### Basic Usage

```jsx
import DataTable from '../../components/DataTable'

const columns = [
  {
    key: 'id',
    name: 'ID',
    sortable: true,
  },
  {
    key: 'name',
    name: 'Name',
    sortable: true,
  },
]

const data = [
  { id: 1, name: 'Item 1' },
  { id: 2, name: 'Item 2' },
]

<DataTable
  columns={columns}
  data={data}
  searchable={true}
  sortable={true}
  pagination={true}
  itemsPerPage={10}
/>
```

## 📋 Column Configuration

### Simple Column
```javascript
{
  key: 'title',
  name: 'Title',
  sortable: true,
  width: '200px', // optional
}
```

### Custom Cell Rendering (Badges)
```javascript
{
  key: 'status',
  name: 'Status',
  sortable: true,
  cell: (row) => (
    <CBadge color={row.status === 'Active' ? 'success' : 'secondary'}>
      {row.status}
    </CBadge>
  ),
}
```

### Custom Cell with Action Buttons
```javascript
{
  key: 'actions',
  name: 'Actions',
  sortable: false,
  cell: (row) => (
    <div className="d-flex gap-2">
      <CButton color="info" size="sm" variant="outline">View</CButton>
      <CButton color="primary" size="sm" variant="outline">Edit</CButton>
    </div>
  ),
}
```

### Custom Sorting Logic
```javascript
{
  key: 'enrollment',
  name: 'Enrollment',
  selector: (row) => row.enrolled, // Sort by this value
  cell: (row) => `${row.enrolled} / ${row.target}`, // Display custom format
}
```

## 🎨 Design Features

### Clean, Modern UI
- Subtle borders and spacing
- Hover effects on rows
- Smooth transitions
- Professional typography

### Visual Indicators
- Sort direction arrows (↑↓)
- Search icon with input
- Entry count display
- Smart pagination dots

### Responsive Design
- Mobile-friendly layout
- Horizontal scrolling for wide tables
- Adaptive column widths
- Touch-friendly controls

## 📦 Component Structure

```
src/components/DataTable/
├── DataTable.js       # Main component logic
├── DataTable.scss     # Styling
├── index.js          # Export
└── README.md         # Full documentation
```

## 🔧 Props Reference

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `columns` | Array | required | Column configuration |
| `data` | Array | required | Data to display |
| `searchable` | Boolean | `true` | Enable search |
| `sortable` | Boolean | `true` | Enable sorting |
| `pagination` | Boolean | `true` | Enable pagination |
| `itemsPerPage` | Number | `10` | Rows per page |
| `onRowClick` | Function | - | Row click handler |
| `className` | String | `''` | Custom CSS class |

## 🎯 Live Example

Check out the Clinical Trials page to see the DataTable in action:

1. Start the dev server:
   ```bash
   npm start
   ```

2. Navigate to: **Trial Management > All Trials**

3. Try these features:
   - **Search**: Type in the search box to filter trials
   - **Sort**: Click column headers to sort
   - **Pagination**: Navigate through pages at the bottom
   - **View Data**: See 10 sample clinical trials

## 🔄 Converting Other Tables

To update other tables to use DataTable:

### Before (Old Table)
```jsx
<CTable hover responsive>
  <CTableHead>
    <CTableRow>
      <CTableHeaderCell>Name</CTableHeaderCell>
    </CTableRow>
  </CTableHead>
  <CTableBody>
    {data.map(row => (
      <CTableRow key={row.id}>
        <CTableDataCell>{row.name}</CTableDataCell>
      </CTableRow>
    ))}
  </CTableBody>
</CTable>
```

### After (DataTable)
```jsx
import DataTable from '../../components/DataTable'

const columns = [
  {
    key: 'name',
    name: 'Name',
    sortable: true,
  },
]

<DataTable columns={columns} data={data} />
```

## 🎨 Styling Customization

Override styles in your component:

```scss
.my-custom-table {
  .data-table-wrapper {
    border-radius: 0.5rem;
  }

  .data-table thead th {
    background: #f8f9fa;
  }
}
```

Then use:
```jsx
<DataTable className="my-custom-table" ... />
```

## 📚 Full Documentation

See `src/components/DataTable/README.md` for complete documentation including:
- Advanced examples
- All configuration options
- Styling guide
- Performance tips
- Accessibility features

## ✅ Next Steps

Consider updating these tables to use DataTable:

- ✅ **AllTrials.js** - Already updated!
- ⬜ **AllPatients.js** - Patient management table
- ⬜ **AllSites.js** - Research sites table
- ⬜ **Investigators.js** - Investigators table
- ⬜ **SiteStaff.js** - Site staff table
- ⬜ **Documents.js** - Document management table
- ⬜ **UserManagement.js** - User management table
- ⬜ **RolesManagement.js** - Roles table
- ⬜ **Protocols.js** - Protocols table
- ⬜ **ConsentForms.js** - Consent forms table

## 🎉 Benefits

- **Consistency**: Same look and feel across all tables
- **Maintainability**: Update one component, all tables improve
- **Features**: Search, sort, pagination out of the box
- **Performance**: Optimized with React hooks and memoization
- **DX**: Easy to use with simple column configuration
- **UX**: Modern, intuitive interface for users

---

**Test it now:**
```bash
npm start
# Navigate to: Trial Management > All Trials
```

Enjoy your new modern table component! 🎊
