# Authentication Pages - Login & Signup

Modern, beautiful authentication pages with shadcn-inspired design for the Clinical Trials Management System.

## ✨ Features

### Login Page
**Location:** `src/views/pages/login/Login.js`

#### Features
- ✅ **Email & Password** authentication
- ✅ **Form validation** with real-time error feedback
- ✅ **Remember me** checkbox (30 days)
- ✅ **Forgot password** link
- ✅ **Sign up** redirect link
- ✅ **Loading state** during submission
- ✅ **Beautiful gradient background**
- ✅ **Responsive design**

#### Form Validation
- Email format validation
- Minimum password length (6 characters)
- Required field validation
- Real-time error clearing

### Signup/Register Page
**Location:** `src/views/pages/register/Register.js`

#### Features
- ✅ **Full name, email, password** fields
- ✅ **Password confirmation** matching
- ✅ **Terms & conditions** checkbox
- ✅ **Strong password validation**
- ✅ **Form validation** with helpful hints
- ✅ **Loading state** during submission
- ✅ **Beautiful gradient background**
- ✅ **Responsive design**

#### Form Validation
- Full name minimum 3 characters
- Valid email format
- Password requirements:
  - Minimum 8 characters
  - Must contain uppercase letter
  - Must contain lowercase letter
  - Must contain number
- Password confirmation matching
- Terms acceptance required

## 🎨 Design Features

### Visual Design

#### Gradient Backgrounds
**Login:** Purple gradient (`#667eea` → `#764ba2`)
**Signup:** Reverse gradient (`#764ba2` → `#667eea`)

#### Components
- **Logo card**: White rounded square with medical cross icon
- **Form card**: Clean white card with shadow
- **Backdrop blur**: Subtle blur effect over gradient
- **Fade-in animation**: Smooth entrance animation

### Typography
```scss
Font Family: System font stack (Inter-style)
Title: 1.75rem, Weight 600
Subtitle: 0.9375rem, Weight 400
Labels: 0.875rem, Weight 500
Inputs: 0.9375rem, Weight 400
```

### Colors (Light Mode)
```scss
Background: Gradient purple
Card: #ffffff
Text: #18181b
Labels: #18181b
Muted: #71717a
Error: #ef4444
Primary: #667eea (Login) / #764ba2 (Signup)
Button: #18181b (Black)
```

### Spacing
```scss
Card Padding: 2rem
Input Height: 44px
Border Radius: 8px (inputs), 12px (cards)
Logo Size: 64px × 64px
```

## 📋 Form Fields

### Login Form
```
┌─────────────────────────────┐
│ Email                       │
│ [name@example.com         ] │
│                             │
│ Password        Forgot pwd? │
│ [••••••••••••••••••••••••] │
│                             │
│ ☑ Remember me for 30 days   │
│                             │
│ [     Sign in     ]         │
└─────────────────────────────┘
Don't have an account? Sign up
```

### Signup Form
```
┌─────────────────────────────┐
│ Full Name                   │
│ [John Doe                 ] │
│                             │
│ Email                       │
│ [name@example.com         ] │
│                             │
│ Password                    │
│ [••••••••••••••••••••••••] │
│ Hint: 8+ chars, upper, num  │
│                             │
│ Confirm Password            │
│ [••••••••••••••••••••••••] │
│                             │
│ ☑ I agree to Terms & Privacy│
│                             │
│ [ Create account ]          │
└─────────────────────────────┘
Already have an account? Sign in
```

## 🔒 Validation Rules

### Login Validation
| Field | Rules |
|-------|-------|
| Email | Required, Valid email format |
| Password | Required, Min 6 characters |

### Signup Validation
| Field | Rules |
|-------|-------|
| Full Name | Required, Min 3 characters |
| Email | Required, Valid email format |
| Password | Required, Min 8 chars, Uppercase, Lowercase, Number |
| Confirm | Required, Must match password |
| Terms | Required, Must be checked |

## 💡 Interactive States

### Input States
```scss
Default:  Border #e4e4e7
Focus:    Border #667eea, Shadow rgba(102,126,234,0.1)
Error:    Border #ef4444, Shadow rgba(239,68,68,0.1)
Disabled: Opacity 0.6
```

### Button States
```scss
Default:  Background #18181b
Hover:    Background #27272a, Lift -1px, Shadow
Active:   Transform back
Loading:  Opacity 0.6, Disabled
```

### Checkbox States
```scss
Unchecked: Border #d4d4d8
Checked:   Background #667eea, Border #667eea
Focus:     Shadow rgba(102,126,234,0.1)
```

## 📱 Responsive Design

### Desktop (> 992px)
- Centered card with max-width
- Full padding and spacing
- Comfortable form fields

### Tablet (768px - 992px)
- Slightly narrower card
- Maintained spacing
- Touch-friendly targets

### Mobile (< 576px)
- Full-width with side padding
- Reduced card padding (1.5rem)
- Smaller title font (1.5rem)
- Optimized for vertical scroll

## 🎯 User Flow

### Login Flow
1. User enters email & password
2. Clicks "Sign in"
3. Form validates input
4. Shows errors if invalid
5. Loading state shows "Signing in..."
6. On success → Navigate to `/dashboard`
7. On error → Show error message

### Signup Flow
1. User enters full name, email, password
2. Confirms password
3. Agrees to terms
4. Clicks "Create account"
5. Form validates all fields
6. Shows errors if invalid
7. Loading state shows "Creating account..."
8. On success → Navigate to `/login`
9. On error → Show error message

## 🔗 Navigation Links

### Login Page Links
- **Forgot password?** → `/forgot-password` (top right)
- **Sign up** → `/register` (bottom)

### Signup Page Links
- **Terms and Conditions** → `/terms`
- **Privacy Policy** → `/privacy`
- **Sign in** → `/login` (bottom)

## 🚀 Usage

### Navigate to Pages
```
Login:  http://localhost:3000/#/login
Signup: http://localhost:3000/#/register
```

### Test Accounts
Currently using simulated API calls (1 second delay).

For testing, any valid format works:
- **Email:** anything@example.com
- **Password:** Test123 (for signup)

## 🎨 Customization

### Change Colors
Edit the SCSS files:

**Login.scss:**
```scss
// Change gradient
background: linear-gradient(135deg, #YOUR_COLOR_1 0%, #YOUR_COLOR_2 100%);

// Change focus color
&:focus {
  border-color: #YOUR_PRIMARY_COLOR;
}
```

**Register.scss:**
```scss
// Same customization points
```

### Change Validation Rules
Edit validation functions in the component:

```javascript
const validateForm = () => {
  // Add your custom rules
  if (formData.password.length < YOUR_MIN_LENGTH) {
    newErrors.password = 'Your custom message'
  }
}
```

## ✨ Animations

### Fade-in Animation
```scss
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

Duration: `0.5s ease`

### Button Hover
- Transform: `translateY(-1px)`
- Shadow: `0 4px 12px rgba(0, 0, 0, 0.15)`
- Transition: `0.2s ease`

## 🌓 Dark Mode Support

Both pages include dark mode styles:

```scss
@media (prefers-color-scheme: dark) {
  // Card background: #18181b
  // Input background: #27272a
  // Text: #fafafa
  // Auto-adapting colors
}
```

## 📦 Files Structure

```
src/views/pages/
├── login/
│   ├── Login.js       # Login component
│   └── Login.scss     # Login styles
└── register/
    ├── Register.js    # Signup component
    └── Register.scss  # Signup styles
```

## ✅ Features Checklist

### Login Page
- ✅ Email validation
- ✅ Password validation
- ✅ Remember me checkbox
- ✅ Forgot password link
- ✅ Sign up redirect
- ✅ Loading state
- ✅ Error messages
- ✅ Responsive design
- ✅ Gradient background
- ✅ Dark mode support

### Signup Page
- ✅ Full name validation
- ✅ Email validation
- ✅ Strong password validation
- ✅ Password confirmation
- ✅ Terms checkbox with links
- ✅ Password hint
- ✅ Loading state
- ✅ Error messages
- ✅ Responsive design
- ✅ Gradient background
- ✅ Dark mode support

## 🎊 Result

Beautiful, modern authentication pages with:
- Professional gradient backgrounds
- Clean, minimal forms
- Comprehensive validation
- Smooth animations
- Excellent UX
- Mobile-friendly design
- Production-ready code

---

**Test them now:**
```bash
npm start
# Navigate to: http://localhost:3000/#/login
# Or: http://localhost:3000/#/register
```

Enjoy your new authentication system! 🚀
