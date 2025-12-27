# Custom Card Component

Modern, shadcn-inspired Card component for the Clinical Trials Management System.

## Features

- Clean, minimal design with subtle shadows
- Proper typography hierarchy
- Responsive padding
- Dark mode support
- Hover effects
- Modular sub-components

## Components

### Card
Main card container with border, shadow, and background.

### CardHeader
Header section with bottom border, contains title and description.

### CardTitle
Large, semibold title text.

### CardDescription
Smaller, muted description text.

### CardContent
Main content area with proper padding.

### CardFooter
Footer section for actions or additional info.

## Usage

### Basic Card

```jsx
import { Card, CardHeader, CardTitle, CardDescription, CardContent } from 'src/components'

<Card>
  <CardHeader>
    <CardTitle>Clinical Trial Details</CardTitle>
    <CardDescription>View and manage trial information</CardDescription>
  </CardHeader>
  <CardContent>
    <p>Your content here...</p>
  </CardContent>
</Card>
```

### Stat Card (Minimal)

```jsx
<Card>
  <CardContent>
    <div className="text-2xl font-bold">12</div>
    <p className="text-sm text-muted">Active Trials</p>
  </CardContent>
</Card>
```

### Card with Footer

```jsx
<Card>
  <CardHeader>
    <CardTitle>Patient Enrollment</CardTitle>
  </CardHeader>
  <CardContent>
    <p>Current: 480 / Target: 700</p>
  </CardContent>
  <CardFooter>
    <button>View Details</button>
  </CardFooter>
</Card>
```

### Card with Custom Styling

```jsx
<Card className="hover-shadow-lg">
  <CardContent>
    <p>Custom styled card</p>
  </CardContent>
</Card>
```

## Design Specifications

### Colors
```scss
Background: #ffffff
Border: #e4e4e7 (zinc-200)
Text: #18181b (zinc-900)
Muted Text: #71717a (zinc-500)
```

### Typography
```scss
Title: 1.125rem (18px), Weight 600
Description: 0.875rem (14px), Weight 400
Content: 0.875rem (14px), Weight 400
```

### Spacing
```scss
Card Padding: 1.5rem (24px)
Header Gap: 0.375rem (6px)
Border Radius: 8px
```

### Shadows
```scss
Default: 0 1px 3px rgba(0, 0, 0, 0.1)
Hover: 0 4px 6px rgba(0, 0, 0, 0.1)
```

## Examples in Dashboard

### Replace CCard with Custom Card

**Before:**
```jsx
<CCard className="mb-4">
  <CCardBody>
    <div className="fs-4 fw-semibold">12</div>
    <div className="text-body-secondary text-uppercase fw-semibold small">
      Active Trials
    </div>
  </CCardBody>
</CCard>
```

**After:**
```jsx
<Card className="mb-4">
  <CardContent>
    <div className="text-2xl font-semibold">12</div>
    <div className="text-xs text-muted uppercase font-semibold">
      Active Trials
    </div>
  </CardContent>
</Card>
```

### Table Card

**Before:**
```jsx
<CCard className="mb-4">
  <CCardHeader>
    <strong>Recent Clinical Trials</strong>
  </CCardHeader>
  <CCardBody>
    <CTable>...</CTable>
  </CCardBody>
</CCard>
```

**After:**
```jsx
<Card className="mb-4">
  <CardHeader>
    <CardTitle>Recent Clinical Trials</CardTitle>
    <CardDescription>View enrollment progress and status</CardDescription>
  </CardHeader>
  <CardContent>
    <DataTable
      columns={columns}
      data={recentTrials}
      searchable={false}
    />
  </CardContent>
</Card>
```

## Responsive Behavior

### Desktop (> 576px)
- Full padding: 1.5rem (24px)

### Mobile (≤ 576px)
- Reduced padding: 1rem (16px)
- Maintains readability and touch targets

## Dark Mode

Automatically adapts when system prefers dark mode:

```scss
Background: #18181b (zinc-900)
Border: #27272a (zinc-800)
Text: #fafafa (zinc-50)
Muted Text: #a1a1aa (zinc-400)
```

## Accessibility

- Semantic HTML structure
- Proper heading hierarchy with CardTitle
- Color contrast meets WCAG AA standards
- Touch-friendly spacing on mobile

## Best Practices

1. **Use CardHeader for titles**: Always wrap titles in CardHeader for consistent spacing
2. **CardDescription is optional**: Only use when additional context is needed
3. **Keep content structured**: Use proper HTML elements inside CardContent
4. **Combine with DataTable**: Card + DataTable = perfect table layout
5. **Add custom classes**: Use className prop for specific styling needs

## Integration with Existing Code

The custom Card component can coexist with CoreUI's CCard:

```jsx
// Use custom Card for shadcn-style UI
import { Card, CardContent } from 'src/components'

// Use CCard for CoreUI-specific features
import { CCard, CCardBody } from '@coreui/react'
```

Choose based on your needs:
- **Custom Card**: Modern, minimal, shadcn-inspired design
- **CCard**: CoreUI theming and specific component features
