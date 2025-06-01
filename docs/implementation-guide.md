# Implementation Guide & Technical Specifications

## Technical Architecture

### Frontend Technology Stack
**Framework**: HTML5, CSS3, Vanilla JavaScript (for prototype)
**Production Recommendation**: React 18+ with TypeScript
**Styling**: Custom CSS with design tokens
**Icons**: Inline SVG system
**Performance**: Mobile-first responsive design

### File Structure
```
truist-commercial-banking/
├── index.html                 # Role selection landing page
├── assets/
│   ├── css/
│   │   ├── main.css          # Core styles and design tokens
│   │   ├── components.css    # Component-specific styles
│   │   └── responsive.css    # Responsive design rules
│   ├── js/
│   │   ├── main.js          # Core JavaScript functionality
│   │   ├── dashboard.js     # Dashboard interactions
│   │   └── utils.js         # Utility functions
│   └── icons/               # SVG icon library
├── analyst/
│   └── dashboard.html       # AP Analyst interface
├── manager/
│   └── dashboard.html       # AP Manager interface
├── compliance/
│   └── dashboard.html       # Compliance Officer interface
└── docs/                   # Design documentation
```

## Design Token Implementation

### CSS Custom Properties
```css
:root {
  /* Brand Colors */
  --truist-purple: #663399;
  --truist-purple-hover: #553388;
  --truist-purple-light: #f3f0ff;
  
  /* Text Colors */
  --text-primary: #1a1a1a;
  --text-secondary: #4a5568;
  --text-muted: #6b7280;
  
  /* Status Colors */
  --status-success: #16a34a;
  --status-warning: #f59e0b;
  --status-error: #ef4444;
  --status-info: #3b82f6;
  --status-neutral: #6b7280;
  
  /* Background Colors */
  --bg-primary: #ffffff;
  --bg-secondary: #f7fafc;
  --bg-muted: #f3f4f6;
  
  /* Border Colors */
  --border-light: #e5e7eb;
  --border-medium: #d1d5db;
  --border-dark: #9ca3af;
  
  /* Spacing Scale */
  --space-xs: 0.25rem;    /* 4px */
  --space-sm: 0.5rem;     /* 8px */
  --space-md: 1rem;       /* 16px */
  --space-lg: 1.5rem;     /* 24px */
  --space-xl: 2rem;       /* 32px */
  --space-2xl: 3rem;      /* 48px */
  
  /* Typography */
  --font-family: 'Truist Sans', system-ui, -apple-system, sans-serif;
  --font-size-xs: 0.75rem;   /* 12px */
  --font-size-sm: 0.875rem;  /* 14px */
  --font-size-base: 1rem;    /* 16px */
  --font-size-lg: 1.125rem;  /* 18px */
  --font-size-xl: 1.25rem;   /* 20px */
  --font-size-2xl: 1.5rem;   /* 24px */
  
  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 1px 3px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 4px 6px rgba(0, 0, 0, 0.1);
  
  /* Border Radius */
  --radius-sm: 0.25rem;   /* 4px */
  --radius-md: 0.5rem;    /* 8px */
  --radius-lg: 0.75rem;   /* 12px */
  
  /* Transitions */
  --transition-fast: 150ms ease-in-out;
  --transition-base: 200ms ease-in-out;
  --transition-slow: 300ms ease-in-out;
}
```

## Component Implementation

### Button Components
```css
/* Primary Button */
.btn-primary {
  background-color: var(--truist-purple);
  color: white;
  border: none;
  padding: var(--space-sm) var(--space-lg);
  border-radius: var(--radius-md);
  font-family: var(--font-family);
  font-size: var(--font-size-sm);
  font-weight: 500;
  cursor: pointer;
  transition: background-color var(--transition-fast);
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
}

.btn-primary:hover {
  background-color: var(--truist-purple-hover);
}

.btn-primary:focus {
  outline: 2px solid var(--truist-purple);
  outline-offset: 2px;
}

.btn-primary:disabled {
  background-color: var(--border-medium);
  cursor: not-allowed;
}

/* Secondary Button */
.btn-secondary {
  background-color: var(--bg-primary);
  color: var(--text-primary);
  border: 1px solid var(--border-medium);
  padding: var(--space-sm) var(--space-lg);
  border-radius: var(--radius-md);
  font-family: var(--font-family);
  font-size: var(--font-size-sm);
  font-weight: 500;
  cursor: pointer;
  transition: all var(--transition-fast);
}

.btn-secondary:hover {
  background-color: var(--bg-secondary);
  border-color: var(--truist-purple);
}
```

### Card Components
```css
/* Base Card */
.card {
  background-color: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  padding: var(--space-lg);
  box-shadow: var(--shadow-sm);
  transition: all var(--transition-base);
}

.card:hover {
  box-shadow: var(--shadow-md);
  border-color: var(--truist-purple);
}

/* Payment Card */
.payment-card {
  background-color: var(--bg-primary);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  padding: var(--space-md);
  margin-bottom: var(--space-md);
  transition: all var(--transition-base);
  cursor: pointer;
}

.payment-card:hover {
  transform: translateY(-2px);
  border-color: var(--truist-purple);
  box-shadow: 0 8px 24px rgba(102, 51, 153, 0.15);
}

.payment-card-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: var(--space-sm);
}

.payment-card-vendor {
  font-size: var(--font-size-lg);
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: var(--space-xs);
}

.payment-card-description {
  font-size: var(--font-size-sm);
  color: var(--text-secondary);
}

.payment-card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: var(--space-md);
}

.payment-amount {
  font-size: var(--font-size-2xl);
  font-weight: bold;
  color: var(--text-primary);
}

.payment-due-date {
  text-align: right;
}

.payment-due-label {
  font-size: var(--font-size-xs);
  color: var(--text-secondary);
  margin-bottom: var(--space-xs);
}

.payment-due-value {
  font-size: var(--font-size-sm);
  font-weight: 500;
  color: var(--text-primary);
}
```

### Status Indicator Components
```css
/* Status Indicator Base */
.status-indicator {
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  padding: var(--space-xs) var(--space-sm);
  border-radius: var(--radius-sm);
  font-size: var(--font-size-xs);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.025em;
}

/* Status Variants */
.status-completed {
  background-color: rgba(22, 163, 74, 0.1);
  color: var(--status-success);
}

.status-pending {
  background-color: rgba(245, 158, 11, 0.1);
  color: var(--status-warning);
}

.status-overdue {
  background-color: rgba(239, 68, 68, 0.1);
  color: var(--status-error);
}

.status-scheduled {
  background-color: rgba(59, 130, 246, 0.1);
  color: var(--status-info);
}

/* Status Icons */
.status-icon {
  width: 16px;
  height: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.status-icon svg {
  width: 12px;
  height: 12px;
  fill: currentColor;
}
```

## Responsive Design Implementation

### Mobile-First CSS Grid
```css
/* Container */
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-md);
}

/* Grid System */
.grid {
  display: grid;
  gap: var(--space-lg);
}

.grid-cols-1 {
  grid-template-columns: 1fr;
}

.grid-cols-2 {
  grid-template-columns: 1fr;
}

.grid-cols-3 {
  grid-template-columns: 1fr;
}

/* Tablet Breakpoint */
@media (min-width: 768px) {
  .container {
    padding: 0 var(--space-xl);
  }
  
  .grid-cols-2 {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .grid-cols-3 {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop Breakpoint */
@media (min-width: 1024px) {
  .grid-cols-3 {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* Large Desktop */
@media (min-width: 1440px) {
  .container {
    padding: 0 var(--space-2xl);
  }
}
```

### Navigation Responsive Patterns
```css
/* Mobile Navigation */
.nav-primary {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-md);
  background-color: var(--bg-primary);
  border-bottom: 1px solid var(--border-light);
}

.nav-menu {
  display: none;
}

.nav-toggle {
  display: block;
  background: none;
  border: none;
  cursor: pointer;
  padding: var(--space-xs);
}

/* Tablet and Desktop Navigation */
@media (min-width: 768px) {
  .nav-menu {
    display: flex;
    gap: var(--space-lg);
  }
  
  .nav-toggle {
    display: none;
  }
}

.nav-item {
  display: flex;
  align-items: center;
  gap: var(--space-xs);
  padding: var(--space-sm) var(--space-md);
  text-decoration: none;
  color: var(--text-secondary);
  font-weight: 500;
  border-radius: var(--radius-md);
  transition: all var(--transition-fast);
}

.nav-item:hover {
  background-color: var(--bg-secondary);
  color: var(--truist-purple);
}

.nav-item.active {
  background-color: var(--truist-purple-light);
  color: var(--truist-purple);
}
```

## JavaScript Implementation

### Core Functionality
```javascript
// Main Application Object
const TruistCommercialBanking = {
  // Initialize the application
  init() {
    this.bindEvents();
    this.initializeRoleSelection();
    this.setupResponsiveHandlers();
  },

  // Event binding
  bindEvents() {
    document.addEventListener('DOMContentLoaded', () => {
      this.init();
    });
    
    window.addEventListener('resize', () => {
      this.handleResize();
    });
  },

  // Role selection functionality
  initializeRoleSelection() {
    const roleCards = document.querySelectorAll('.role-card');
    
    roleCards.forEach(card => {
      card.addEventListener('click', (e) => {
        const role = e.currentTarget.dataset.role;
        this.navigateToRole(role);
      });
      
      card.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          const role = e.currentTarget.dataset.role;
          this.navigateToRole(role);
        }
      });
    });
  },

  // Navigation
  navigateToRole(role) {
    const roleUrls = {
      'analyst': './analyst/dashboard.html',
      'manager': './manager/dashboard.html',
      'compliance': './compliance/dashboard.html'
    };
    
    if (roleUrls[role]) {
      window.location.href = roleUrls[role];
    }
  },

  // Responsive handling
  handleResize() {
    const viewport = window.innerWidth;
    
    if (viewport < 768) {
      this.handleMobileView();
    } else if (viewport < 1024) {
      this.handleTabletView();
    } else {
      this.handleDesktopView();
    }
  },

  handleMobileView() {
    // Mobile-specific functionality
    document.body.classList.add('mobile-view');
    document.body.classList.remove('tablet-view', 'desktop-view');
  },

  handleTabletView() {
    // Tablet-specific functionality
    document.body.classList.add('tablet-view');
    document.body.classList.remove('mobile-view', 'desktop-view');
  },

  handleDesktopView() {
    // Desktop-specific functionality
    document.body.classList.add('desktop-view');
    document.body.classList.remove('mobile-view', 'tablet-view');
  }
};

// Dashboard Functionality
const DashboardManager = {
  // Initialize dashboard
  init() {
    this.bindEvents();
    this.loadPaymentData();
    this.setupFilters();
    this.initializeQuickActions();
  },

  // Event binding for dashboard
  bindEvents() {
    // Payment card interactions
    const paymentCards = document.querySelectorAll('.payment-card');
    paymentCards.forEach(card => {
      card.addEventListener('click', (e) => {
        if (!e.target.closest('.btn')) {
          this.showPaymentDetails(card.dataset.paymentId);
        }
      });
    });

    // Quick action buttons
    const quickActions = document.querySelectorAll('.quick-action');
    quickActions.forEach(button => {
      button.addEventListener('click', (e) => {
        const action = e.currentTarget.dataset.action;
        this.handleQuickAction(action);
      });
    });

    // Filter functionality
    const filterInputs = document.querySelectorAll('.filter-input');
    filterInputs.forEach(input => {
      input.addEventListener('change', () => {
        this.applyFilters();
      });
    });
  },

  // Payment data management
  loadPaymentData() {
    // Simulate API call for payment data
    const mockPayments = [
      {
        id: '1',
        vendor: 'ABC Corporation',
        amount: 15750.00,
        dueDate: '2024-02-15',
        status: 'pending',
        description: 'Office supplies and equipment'
      },
      {
        id: '2',
        vendor: 'XYZ Services Inc.',
        amount: 8200.50,
        dueDate: '2024-02-18',
        status: 'completed',
        description: 'Monthly service contract'
      }
    ];
    
    this.renderPayments(mockPayments);
  },

  // Render payment cards
  renderPayments(payments) {
    const container = document.querySelector('.payments-list');
    if (!container) return;
    
    container.innerHTML = payments.map(payment => `
      <div class="payment-card" data-payment-id="${payment.id}">
        <div class="payment-card-header">
          <div>
            <div class="payment-card-vendor">${payment.vendor}</div>
            <div class="payment-card-description">${payment.description}</div>
          </div>
          <div class="status-indicator status-${payment.status}">
            <span class="status-icon">${this.getStatusIcon(payment.status)}</span>
            <span class="status-text">${this.getStatusText(payment.status)}</span>
          </div>
        </div>
        <div class="payment-card-footer">
          <div class="payment-amount">${this.formatCurrency(payment.amount)}</div>
          <div class="payment-due-date">
            <div class="payment-due-label">Due Date</div>
            <div class="payment-due-value">${this.formatDate(payment.dueDate)}</div>
          </div>
        </div>
        <div class="payment-actions">
          <button class="btn btn-primary" data-action="review">Review</button>
          <button class="btn btn-secondary" data-action="schedule">Schedule</button>
        </div>
      </div>
    `).join('');
  },

  // Utility functions
  formatCurrency(amount) {
    return new Intl.NumberFormat('en-US', {
      style: 'currency',
      currency: 'USD'
    }).format(amount);
  },

  formatDate(dateString) {
    return new Date(dateString).toLocaleDateString('en-US', {
      month: 'short',
      day: 'numeric',
      year: 'numeric'
    });
  },

  getStatusIcon(status) {
    const icons = {
      completed: '✓',
      pending: '⏰',
      processing: '↻',
      overdue: '⚠',
      scheduled: '📅'
    };
    return icons[status] || '•';
  },

  getStatusText(status) {
    const texts = {
      completed: 'Completed',
      pending: 'Pending',
      processing: 'Processing',
      overdue: 'Overdue',
      scheduled: 'Scheduled'
    };
    return texts[status] || 'Unknown';
  },

  // Quick actions
  handleQuickAction(action) {
    switch (action) {
      case 'pay':
        this.showPaymentModal();
        break;
      case 'schedule':
        this.showScheduleModal();
        break;
      case 'batch':
        this.showBatchModal();
        break;
      default:
        console.log(`Unknown action: ${action}`);
    }
  },

  // Modal functionality
  showPaymentModal() {
    // Implementation for payment modal
    console.log('Opening payment modal...');
  },

  showScheduleModal() {
    // Implementation for schedule modal
    console.log('Opening schedule modal...');
  },

  showBatchModal() {
    // Implementation for batch modal
    console.log('Opening batch modal...');
  },

  showPaymentDetails(paymentId) {
    // Implementation for payment details view
    console.log(`Showing details for payment ${paymentId}`);
  },

  // Filter functionality
  applyFilters() {
    const statusFilter = document.querySelector('#status-filter')?.value;
    const dateFilter = document.querySelector('#date-filter')?.value;
    const searchFilter = document.querySelector('#search-filter')?.value;

    // Apply filters to payment data
    console.log('Applying filters:', { statusFilter, dateFilter, searchFilter });
  }
};

// Initialize application
TruistCommercialBanking.init();

// Initialize dashboard if on dashboard page
if (document.querySelector('.dashboard')) {
  DashboardManager.init();
}
```

## Accessibility Implementation

### ARIA Labels and Semantic HTML
```html
<!-- Navigation with proper ARIA -->
<nav aria-label="Main navigation" role="navigation">
  <ul role="menubar">
    <li role="none">
      <a href="/dashboard" role="menuitem" aria-current="page">Dashboard</a>
    </li>
    <li role="none">
      <a href="/payments" role="menuitem">Payments</a>
    </li>
  </ul>
</nav>

<!-- Form with accessibility features -->
<form role="form" aria-labelledby="payment-form-title">
  <h2 id="payment-form-title">Payment Information</h2>
  
  <div class="form-group">
    <label for="vendor-name">Vendor Name</label>
    <input 
      type="text" 
      id="vendor-name" 
      name="vendor" 
      required 
      aria-describedby="vendor-help"
      aria-invalid="false"
    >
    <div id="vendor-help" class="form-help">
      Enter the full legal name of the vendor
    </div>
  </div>
  
  <div class="form-group">
    <label for="amount">Payment Amount</label>
    <input 
      type="number" 
      id="amount" 
      name="amount" 
      required 
      min="0.01" 
      step="0.01"
      aria-describedby="amount-format"
    >
    <div id="amount-format" class="form-help">
      Enter amount in USD (e.g., 1250.50)
    </div>
  </div>
</form>

<!-- Status indicators with accessibility -->
<div class="status-indicator status-pending" role="status" aria-label="Payment status: Pending approval">
  <span class="status-icon" aria-hidden="true">⏰</span>
  <span class="status-text">Pending</span>
</div>
```

### Focus Management
```css
/* Focus indicators */
*:focus {
  outline: 2px solid var(--truist-purple);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}

/* Skip to content link */
.skip-link {
  position: absolute;
  top: -40px;
  left: 6px;
  background: var(--truist-purple);
  color: white;
  padding: 8px;
  text-decoration: none;
  border-radius: var(--radius-sm);
  z-index: 1000;
  transition: top var(--transition-fast);
}

.skip-link:focus {
  top: 6px;
}

/* High contrast mode support */
@media (prefers-contrast: high) {
  :root {
    --border-light: #000000;
    --border-medium: #000000;
    --text-secondary: #000000;
  }
}

/* Reduced motion support */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Screen Reader Support
```javascript
// Live region announcements
const announceToScreenReader = (message, priority = 'polite') => {
  const announcement = document.createElement('div');
  announcement.setAttribute('aria-live', priority);
  announcement.setAttribute('aria-atomic', 'true');
  announcement.className = 'sr-only';
  announcement.textContent = message;
  
  document.body.appendChild(announcement);
  
  setTimeout(() => {
    document.body.removeChild(announcement);
  }, 1000);
};

// Usage examples
announceToScreenReader('Payment of $1,250.00 processed successfully');
announceToScreenReader('Error: Please check the payment amount', 'assertive');
```

## Performance Optimization

### CSS Optimization
```css
/* Critical CSS - inline in head */
.critical-above-fold {
  /* Only styles needed for above-the-fold content */
}

/* Optimize for paint performance */
.will-change {
  will-change: transform;
}

.hardware-accelerated {
  transform: translateZ(0);
  backface-visibility: hidden;
}

/* Efficient animations */
@keyframes fadeIn {
  from { opacity: 0; transform: translate3d(0, 10px, 0); }
  to { opacity: 1; transform: translate3d(0, 0, 0); }
}

.fade-in {
  animation: fadeIn 0.3s ease-out;
}
```

### JavaScript Performance
```javascript
// Debounced search function
const debounce = (func, wait) => {
  let timeout;
  return function executedFunction(...args) {
    const later = () => {
      clearTimeout(timeout);
      func(...args);
    };
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
};

// Usage for search input
const handleSearch = debounce((searchTerm) => {
  // Perform search operation
  console.log('Searching for:', searchTerm);
}, 300);

// Intersection Observer for lazy loading
const observeElements = () => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  });

  document.querySelectorAll('.lazy-load').forEach(el => {
    observer.observe(el);
  });
};
```

## Testing Strategy

### HTML Validation
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Truist Commercial Banking - Accounts Payable Dashboard">
  <title>Truist Commercial Banking</title>
  <!-- Proper meta tags for SEO and accessibility -->
</head>
```

### Accessibility Testing Checklist
- [ ] **Keyboard Navigation**: All functionality accessible via keyboard
- [ ] **Screen Reader**: Content properly announced by NVDA/JAWS
- [ ] **Color Contrast**: WCAG AA compliance verified with tools
- [ ] **Focus Management**: Clear focus indicators on all interactive elements
- [ ] **ARIA Labels**: Proper labeling for complex UI components
- [ ] **Semantic HTML**: Proper heading hierarchy and landmarks
- [ ] **Error Handling**: Clear error messages with recovery instructions

### Cross-Browser Testing
```javascript
// Feature detection instead of browser detection
const supportsGrid = CSS.supports('display', 'grid');
const supportsCustomProperties = CSS.supports('color', 'var(--test)');

if (!supportsGrid) {
  // Fallback layout for older browsers
  document.body.classList.add('no-grid-support');
}

if (!supportsCustomProperties) {
  // Load polyfill for CSS custom properties
  loadPolyfill('css-vars-ponyfill');
}
```

### Performance Testing
```javascript
// Performance monitoring
const measurePerformance = () => {
  // First Contentful Paint
  const fcp = performance.getEntriesByName('first-contentful-paint')[0];
  console.log('First Contentful Paint:', fcp?.startTime);

  // Largest Contentful Paint
  const observer = new PerformanceObserver((list) => {
    const entries = list.getEntries();
    const lcp = entries[entries.length - 1];
    console.log('Largest Contentful Paint:', lcp.startTime);
  });
  observer.observe({ entryTypes: ['largest-contentful-paint'] });

  // Cumulative Layout Shift
  let clsValue = 0;
  const clsObserver = new PerformanceObserver((list) => {
    for (const entry of list.getEntries()) {
      if (!entry.hadRecentInput) {
        clsValue += entry.value;
      }
    }
    console.log('Cumulative Layout Shift:', clsValue);
  });
  clsObserver.observe({ entryTypes: ['layout-shift'] });
};

// Run performance measurement
measurePerformance();
```

## Deployment Guidelines

### Production Build Process
```bash
# Build optimization steps
1. Minify CSS and JavaScript
2. Optimize images (WebP, appropriate sizing)
3. Generate critical CSS
4. Set up proper caching headers
5. Enable gzip compression
6. Configure CDN for static assets
```

### Environment Configuration
```javascript
// Environment-specific configuration
const config = {
  development: {
    apiUrl: 'http://localhost:3000/api',
    debug: true,
    analytics: false
  },
  staging: {
    apiUrl: 'https://staging-api.truist.com',
    debug: false,
    analytics: true
  },
  production: {
    apiUrl: 'https://api.truist.com',
    debug: false,
    analytics: true
  }
};

const currentConfig = config[process.env.NODE_ENV] || config.development;
```

### Security Headers
```nginx
# Nginx configuration for security headers
add_header X-Frame-Options "SAMEORIGIN";
add_header X-Content-Type-Options "nosniff";
add_header X-XSS-Protection "1; mode=block";
add_header Referrer-Policy "strict-origin-when-cross-origin";
add_header Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline';";
```

## Future Enhancements

### React Migration Path
```typescript
// Component architecture for React migration
interface PaymentCardProps {
  payment: {
    id: string;
    vendor: string;
    amount: number;
    dueDate: string;
    status: 'completed' | 'pending' | 'overdue' | 'scheduled';
    description?: string;
  };
  onAction?: (action: string, paymentId: string) => void;
}

const PaymentCard: React.FC<PaymentCardProps> = ({ payment, onAction }) => {
  const handleAction = (action: string) => {
    onAction?.(action, payment.id);
  };

  return (
    <div className="payment-card">
      <div className="payment-card-header">
        <div>
          <h3 className="payment-card-vendor">{payment.vendor}</h3>
          <p className="payment-card-description">{payment.description}</p>
        </div>
        <StatusIndicator status={payment.status} />
      </div>
      <div className="payment-card-footer">
        <div className="payment-amount">
          {formatCurrency(payment.amount)}
        </div>
        <div className="payment-due-date">
          <div className="payment-due-label">Due Date</div>
          <div className="payment-due-value">
            {formatDate(payment.dueDate)}
          </div>
        </div>
      </div>
      <div className="payment-actions">
        <button 
          className="btn-primary" 
          onClick={() => handleAction('review')}
        >
          Review
        </button>
        <button 
          className="btn-secondary" 
          onClick={() => handleAction('schedule')}
        >
          Schedule
        </button>
      </div>
    </div>
  );
};
```

### API Integration Guidelines
```javascript
// API service layer structure
class PaymentService {
  constructor(baseURL) {
    this.baseURL = baseURL;
    this.headers = {
      'Content-Type': 'application/json',
      'Authorization': `Bearer ${this.getAuthToken()}`
    };
  }

  async getPayments(filters = {}) {
    const queryParams = new URLSearchParams(filters);
    const response = await fetch(`${this.baseURL}/payments?${queryParams}`, {
      headers: this.headers
    });
    
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    
    return response.json();
  }

  async updatePaymentStatus(paymentId, status) {
    const response = await fetch(`${this.baseURL}/payments/${paymentId}`, {
      method: 'PATCH',
      headers: this.headers,
      body: JSON.stringify({ status })
    });
    
    if (!response.ok) {
      throw new Error(`Failed to update payment status: ${response.status}`);
    }
    
    return response.json();
  }

  async batchUpdatePayments(paymentIds, action) {
    const response = await fetch(`${this.baseURL}/payments/batch`, {
      method: 'POST',
      headers: this.headers,
      body: JSON.stringify({ paymentIds, action })
    });
    
    if (!response.ok) {
      throw new Error(`Batch update failed: ${response.status}`);
    }
    
    return response.json();
  }

  getAuthToken() {
    // Implementation for retrieving auth token
    return localStorage.getItem('authToken') || '';
  }
}

// Error handling wrapper
const withErrorHandling = (apiCall) => {
  return async (...args) => {
    try {
      return await apiCall(...args);
    } catch (error) {
      console.error('API Error:', error);
      
      // Show user-friendly error message
      showNotification({
        type: 'error',
        message: 'Something went wrong. Please try again.',
        duration: 5000
      });
      
      throw error;
    }
  };
};
```

## Maintenance Guidelines

### Code Standards
```javascript
// ESLint configuration example
module.exports = {
  extends: ['eslint:recommended'],
  rules: {
    'no-console': 'warn',
    'no-unused-vars': 'error',
    'prefer-const': 'error',
    'no-var': 'error'
  }
};

// Prettier configuration
module.exports = {
  singleQuote: true,
  trailingComma: 'es5',
  tabWidth: 2,
  semi: true
};
```

### Documentation Standards
```javascript
/**
 * Processes a payment transaction
 * @param {Object} paymentData - The payment information
 * @param {string} paymentData.vendorId - Unique vendor identifier
 * @param {number} paymentData.amount - Payment amount in USD
 * @param {string} paymentData.dueDate - Due date in ISO format
 * @returns {Promise<Object>} Promise resolving to payment confirmation
 * @throws {Error} When payment validation fails
 */
async function processPayment(paymentData) {
  // Implementation
}
```

### Version Control
```bash
# Git workflow for feature development
git checkout -b feature/payment-batch-operations
git add .
git commit -m "feat: add batch payment operations functionality"
git push origin feature/payment-batch-operations

# Create pull request with:
# - Clear description of changes
# - Screenshots of UI updates
# - Test coverage information
# - Accessibility audit results
```

This comprehensive implementation guide provides all necessary technical specifications for developing, testing, and deploying the Truist Commercial Banking platform while maintaining high standards of accessibility, performance, and code quality.
