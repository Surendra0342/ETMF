# DataTable Component - Visual Preview

## 🎨 Design Overview

The DataTable component features a clean, modern design inspired by shadcn/ui with the following characteristics:

### UI Features

```
┌─────────────────────────────────────────────────────────────┐
│  Search: [🔍 Search...]              Showing 5 of 10 entries │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌───────────────────────────────────────────────────────┐  │
│  │ Trial ID ↕ │ Title ↕ │ Phase ↕ │ Status ↕ │ Actions  │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │ CT-001     │ Phase III Diabetes... │ Phase III │      │  │
│  │            │                       │           │ 🟢Active│  │
│  │            │                       │      [View] [Edit] │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │ CT-002     │ Cancer Immuno...      │ Phase II  │      │  │
│  │            │                       │           │ 🔵Recruiting │
│  │            │                       │      [View] [Edit] │  │
│  └───────────────────────────────────────────────────────┘  │
│                                                               │
│            [< Previous] [1] [2] ... [Next >]                 │
└─────────────────────────────────────────────────────────────┘
```

## 🎯 Key Visual Elements

### 1. Search Bar
```
┌────────────────────────┐
│ 🔍 Search...           │
└────────────────────────┘
```
- Clean input with search icon
- Real-time filtering
- Placeholder text guide

### 2. Info Display
```
Showing 5 of 10 entries
```
- Shows current visible items
- Updates with search/filter

### 3. Table Headers
```
Trial ID ↕ │ Title ↕ │ Phase ↕ │ Status ↕
```
- Sortable columns show swap icon (↕)
- Active sort shows direction (↑ or ↓)
- Hover effects on sortable columns
- Clean, bold typography

### 4. Table Rows
- Subtle hover effect (light background)
- Clean borders between rows
- Proper spacing and padding
- Responsive cell alignment

### 5. Status Badges
```
🟢 Active       (Green)
🔵 Recruiting   (Blue)
⚫ Completed    (Gray)
🟡 Suspended    (Yellow)
```

### 6. Action Buttons
```
[View] [Edit]
```
- Outline style buttons
- Hover effects
- Proper spacing

### 7. Pagination
```
[< Previous] [1] [2] ... [Next >]
```
- Smart page number display
- Current page highlighted
- Ellipsis for many pages
- Disabled state for boundaries

## 🎨 Color Scheme

### Light Mode
- **Background**: White (#ffffff)
- **Borders**: Light gray (#e0e0e0)
- **Text**: Dark gray (#333333)
- **Header Background**: Light tertiary (#f8f9fa)
- **Hover**: Light gray (#f5f5f5)
- **Primary**: Blue (#0d6efd)

### Dark Mode
- **Background**: Dark (#1a1a1a)
- **Borders**: Dark gray (#404040)
- **Text**: Light gray (#e0e0e0)
- **Header Background**: Dark tertiary (#2d2d2d)
- **Hover**: Dark gray (#2a2a2a)
- **Primary**: Blue (#0d6efd)

## 📏 Spacing & Typography

### Table Padding
- **Header cells**: 0.75rem (12px) vertical, 1rem (16px) horizontal
- **Body cells**: 0.875rem (14px) vertical, 1rem (16px) horizontal
- **Table border radius**: 0.375rem (6px)

### Font Sizes
- **Headers**: 0.875rem (14px) - Semi-bold
- **Body text**: 0.875rem (14px) - Regular
- **Search placeholder**: 0.875rem (14px)
- **Info text**: 0.875rem (14px) - Muted

### Transitions
- All hover effects: 0.15s ease-in-out
- Smooth and professional feel

## 🖼️ Example Table Layouts

### Full-Width Table (Desktop)
```
┌──────────────────────────────────────────────────────────────────┐
│ Trial ID   │ Title                    │ Phase     │ Status   │ ... │
├──────────────────────────────────────────────────────────────────┤
│ CT-001     │ Phase III Diabetes Study │ Phase III │ 🟢Active │ ... │
│ CT-002     │ Cancer Immunotherapy...  │ Phase II  │ 🔵Recruit│ ... │
└──────────────────────────────────────────────────────────────────┘
```

### Compact Table (Tablet)
```
┌─────────────────────────────────────────────────┐
│ ID     │ Title           │ Status   │ Actions  │
├─────────────────────────────────────────────────┤
│ CT-001 │ Diabetes...     │ 🟢Active │ [V] [E] │
│ CT-002 │ Cancer...       │ 🔵Recruit│ [V] [E] │
└─────────────────────────────────────────────────┘
```

### Mobile (Scrollable)
```
┌──────────────────────┐
│ ID     │ Title       │ → (scroll)
├──────────────────────┤
│ CT-001 │ Diabetes... │ →
│ CT-002 │ Cancer...   │ →
└──────────────────────┘
```

## ✨ Interactive States

### Hover on Row
```
┌─────────────────────────────────────┐
│ 👆 CT-001 │ Diabetes... │ Active   │  ← Light background
└─────────────────────────────────────┘
```

### Active Sort (Ascending)
```
Trial ID ↑
```

### Active Sort (Descending)
```
Trial ID ↓
```

### Pagination - Current Page
```
[Previous] [1] [[2]] [3] [Next]
              ^^^^
           Highlighted
```

### Search Active
```
┌────────────────────────┐
│ 🔍 diabetes|           │  ← User typing
└────────────────────────┘

Results filter in real-time
```

## 🎭 Component States

### Empty State
```
┌─────────────────────────────────────┐
│                                     │
│        No data available            │
│                                     │
└─────────────────────────────────────┘
```

### Loading State (if implemented)
```
┌─────────────────────────────────────┐
│                                     │
│           ⏳ Loading...             │
│                                     │
└─────────────────────────────────────┘
```

### No Search Results
```
Search: [🔍 xyz]     Showing 0 of 10 entries

┌─────────────────────────────────────┐
│                                     │
│        No data available            │
│                                     │
└─────────────────────────────────────┘
```

## 🌟 Special Features

### Custom Cell Content
```
Enrollment Column:
145 / 200    ← Custom format
 67 / 150
312 / 400
```

### Status Badges
```
Different colors based on status:
┌──────────┐ ┌────────────┐ ┌──────────┐
│ ✓ Active │ │ ⓘ Recruiting│ │ ● Completed│
└──────────┘ └────────────┘ └──────────┘
   Green         Blue           Gray
```

### Action Buttons
```
┌──────┐ ┌──────┐
│ View │ │ Edit │  ← Outline style
└──────┘ └──────┘

On hover:
┌──────┐ ┌──────┐
│■View■│ │■Edit■│  ← Slight background
└──────┘ └──────┘
```

## 📱 Responsive Behavior

### Desktop (> 1024px)
- Full table with all columns
- Comfortable spacing
- All features visible

### Tablet (768px - 1024px)
- Slightly condensed columns
- Horizontal scroll if needed
- Maintained readability

### Mobile (< 768px)
- Horizontal scroll enabled
- Compact button sizes
- Touch-friendly targets
- Search moves to full width

## 🎯 Accessibility Features

- ✅ Semantic HTML (`<table>`, `<thead>`, `<tbody>`)
- ✅ Keyboard navigation
- ✅ ARIA labels
- ✅ High contrast text
- ✅ Focus indicators
- ✅ Screen reader friendly

## 🚀 Performance

- Virtualization for large datasets (optional)
- Memoized calculations
- Efficient re-renders
- Smooth animations

---

**See it live:** Navigate to Trial Management > All Trials after running `npm start`
