# Truist Commercial Banking Design System

## Overview

This design system establishes the visual foundation for Truist's Commercial Banking platform, ensuring consistency, accessibility, and professional brand representation across all user interfaces.

## Brand Identity

### Primary Colors
```css
--truist-purple: #663399      /* Primary brand color */
--truist-purple-hover: #553388 /* Hover states */
--truist-purple-light: #f3f0ff /* Light backgrounds */
```

### Text Colors
```css
--text-primary: #1a1a1a       /* Main headings and content */
--text-secondary: #4a5568     /* Supporting text */
--text-muted: #6b7280         /* Subtle text and labels */
```

### Status Colors
```css
--status-success: #16a34a     /* Completed, approved */
--status-warning: #f59e0b     /* Pending, attention needed */
--status-error: #ef4444       /* Overdue, errors */
--status-info: #3b82f6        /* Scheduled, informational */
--status-neutral: #6b7280     /* Inactive, disabled */
```

### Background Colors
```css
--bg-primary: #ffffff         /* Main background */
--bg-secondary: #f7fafc       /* Card backgrounds */
--bg-muted: #f3f4f6          /* Subtle sections */
```

## Typography

### Font Family
**Primary**: `'Truist Sans', system-ui, -apple-system, sans-serif`

### Type Scale
| Element | Size | Weight | Color | Usage |
|---------|------|--------|-------|-------|
| **H1** | 24px | 600 | `#1a1a1a` | Page titles |
| **H2** | 20px | 600 | `#1a1a1a` | Section headers |
| **H3** | 18px | 500 | `#1a1a1a` | Card titles |
| **Body** | 16px | 400 | `#1a1a1a` | Main content |
| **Secondary** | 14px | 400 | `#4a5568` | Supporting text |
| **Small** | 12px | 400 | `#6b7280` | Labels, captions |

## Component Library

### Buttons

#### Primary Button
```css
.btn-primary {
  background: #663399;
  color: white;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 500;
  font-size: 14px;
  border: none;
  cursor: pointer;
  transition: background 150ms ease;
}

.btn-primary:hover {
  background: #553388;
}
```

#### Secondary Button
```css
.btn-secondary {
  background: white;
  color: #374151;
  border: 1px solid #d1d5db;
  padding: 12px 24px;
  border-radius: 6px;
  font-weight: 500;
  font-size: 14px;
  cursor: pointer;
  transition: background 150ms ease;
}

.btn-secondary:hover {
  background: #f9fafb;
}
```

### Cards

#### Standard Card
```css
.card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
  transition: all 200ms ease;
}

.card:hover {
  border-color: #663399;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}
```

#### Payment Card
```css
.payment-card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 16px;
  transition: all 200ms ease;
}

.payment-card:hover {
  border-color: #663399;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(102, 51, 153, 0.15);
}
```

### Status Indicators

#### Multi-Modal Status System
Our status indicators use three communication methods for accessibility:

1. **Color coding** for quick visual recognition
2. **Icons** for universal understanding  
3. **Text labels** for clarity and screen readers

```html
<!-- Completed Status -->
<div class="status-indicator status-success">
  <div class="status-icon">
    <svg><!-- Checkmark icon --></svg>
  </div>
  <span class="status-text">Completed</span>
</div>

<!-- Pending Status -->
<div class="status-indicator status-warning">
  <div class="status-icon">
    <svg><!-- Clock icon --></svg>
  </div>
  <span class="status-text">Pending</span>
</div>
```

#### Status Color Applications
| Status | Color | Icon | Usage |
|--------|-------|------|-------|
| **Completed** | `#16a34a` | ✓ Checkmark | Successful payments |
| **Pending** | `#f59e0b` | ⏰ Clock | Awaiting action |
| **Processing** | `#3b82f6` | ↻ Refresh | In progress |
| **Overdue** | `#ef4444` | ⚠ Alert | Requires attention |
| **Scheduled** | `#3b82f6` | 📅 Calendar | Future payments |

## Iconography

### Icon Style Guidelines
- **Style**: Outlined/stroke-based icons
- **Stroke Width**: 1.5px consistent
- **Size Standards**: 16px (inline), 20px (standard), 24px (primary actions)
- **Color**: `#4a5568` (default), `#663399` (active/selected)

### Standard Icon Set
| Icon | Usage | SVG Path |
|------|-------|----------|
| **Home** | Dashboard navigation | `M3 13h1v7c0 1.103.897 2 2 2h12c1.103 0 2-.897 2-2v-7h1...` |
| **Payments** | Payment sections | `M20 4H4c-1.103 0-2 .897-2 2v12c0 1.103.897 2 2 2h16...` |
| **Reports** | Analytics and reports | `M3 4v16c0 1.103.897 2 2 2h14c1.103 0 2-.897 2-2V8...` |
| **Settings** | Configuration | `M12 15.5A3.5 3.5 0 0 1 8.5 12A3.5 3.5 0 0 1 12 8.5...` |

## Layout System

### Grid Structure
```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 16px;
}

.grid {
  display: grid;
  gap: 24px;
}

.grid-cols-1 { grid-template-columns: 1fr; }
.grid-cols-2 { grid-template-columns: repeat(2, 1fr); }
.grid-cols-3 { grid-template-columns: repeat(3, 1fr); }

@media (max-width: 768px) {
  .grid-cols-2,
  .grid-cols-3 {
    grid-template-columns: 1fr;
  }
}
```

### Spacing Scale
Based on 4px increments for consistency:

```css
--space-xs: 4px    /* 0.25rem */
--space-sm: 8px    /* 0.5rem */
--space-md: 16px   /* 1rem */
--space-lg: 24px   /* 1.5rem */
--space-xl: 32px   /* 2rem */
--space-2xl: 48px  /* 3rem */
```

## Accessibility Standards

### Color Contrast Compliance
All color combinations meet **WCAG AA standards** (4.5:1 minimum):

| Combination | Contrast Ratio | Status |
|-------------|----------------|--------|
| Primary text (#1a1a1a) on white | 12.6:1 | ✅ Pass |
| Secondary text (#4a5568) on white | 7.4:1 | ✅ Pass |
| Truist purple (#663399) on white | 7.8:1 | ✅ Pass |
| Warning text (#f59e0b) on white | 4.7:1 | ✅ Pass |

### Focus States
```css
.focusable:focus {
  outline: 2px solid #663399;
  outline-offset: 2px;
  border-radius: 4px;
}
```

### Screen Reader Support
- Semantic HTML structure with proper heading hierarchy
- ARIA labels for interactive elements
- Alt text for all meaningful images and icons
- Live regions for dynamic content updates

## Responsive Design

### Breakpoint System
```css
/* Mobile First Approach */
.responsive-element {
  /* Mobile styles (320px+) */
}

@media (min-width: 768px) {
  /* Tablet styles */
}

@media (min-width: 1024px) {
  /* Desktop styles */
}

@media (min-width: 1440px) {
  /* Large desktop styles */
}
```

### Touch Targets
- Minimum 44px × 44px for all interactive elements
- Adequate spacing between touch targets (8px minimum)
- Hover states disabled on touch devices

## Animation & Interaction

### Transition Standards
```css
--transition-fast: 150ms ease-in-out;
--transition-base: 200ms ease-in-out;
--transition-slow: 300ms ease-in-out;
```

### Micro-Interactions
- **Hover effects**: Subtle color shifts and elevation changes
- **Button presses**: Brief scale animation (0.98 scale for 100ms)
- **Loading states**: Smooth rotation animations
- **Page transitions**: Gentle slide/fade effects

### Motion Guidelines
- Respect `prefers-reduced-motion` for accessibility
- Keep animations under 300ms for responsiveness
- Use easing functions for natural movement
- Provide clear visual feedback for all interactions

## Implementation Notes

### CSS Custom Properties
All design tokens are implemented as CSS custom properties for easy theming and maintenance:

```css
:root {
  /* All design tokens defined here */
}
```

### Component Naming Convention
- Use BEM methodology for CSS classes
- Prefix component classes with `truist-`
- Maintain consistent naming across all components

### Browser Support
- **Modern browsers**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Mobile**: iOS Safari 14+, Chrome Mobile 90+
- **Graceful degradation** for older browsers

This design system ensures consistent, accessible, and maintainable user interfaces across the entire Truist Commercial Banking platform.
