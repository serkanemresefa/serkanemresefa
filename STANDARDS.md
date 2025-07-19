# STANDARDS.md - Code Standards & Best Practices

## Genel Prensipler

### 1. Code Quality
- **Readability First**: Kod okunabilirliği performanstan önce gelir
- **Consistency**: Proje boyunca tutarlı stil
- **Maintainability**: Kolay bakım yapılabilir kod
- **Accessibility**: Erişilebilir web standartları

### 2. Performance
- **Mobile First**: Mobil cihazlar öncelikli optimizasyon
- **Progressive Enhancement**: Temel işlevsellik önce, gelişmiş özellikler sonra
- **Lazy Loading**: Gerektiğinde yükleme
- **Minimal Dependencies**: Gereksiz kütüphane kullanımından kaçınma

### 3. Security
- **Input Validation**: Tüm kullanıcı girişlerini doğrulama
- **XSS Prevention**: Cross-site scripting koruması
- **CSRF Protection**: Cross-site request forgery koruması
- **HTTPS Only**: Güvenli bağlantı zorunluluğu

## HTML Standards

### Semantic HTML5
```html
<!-- Doğru yapı -->
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Serkan Emre Sefa - UEFA Pro Coach">
    <title>Serkan Emre Sefa - Futbol Antrenörlüğü</title>
</head>
<body>
    <header role="banner">
        <nav aria-label="Ana navigasyon">
            <!-- Navigation -->
        </nav>
    </header>
    
    <main role="main">
        <section aria-labelledby="about-heading">
            <h1 id="about-heading">Hakkımda</h1>
            <!-- Content -->
        </section>
    </main>
    
    <footer role="contentinfo">
        <!-- Footer -->
    </footer>
</body>
</html>
```

### Accessibility Standards
```html
<!-- Form accessibility -->
<form>
    <label for="name">Ad Soyad</label>
    <input type="text" id="name" name="name" required aria-describedby="name-help">
    <span id="name-help">Lütfen ad ve soyadınızı girin</span>
</form>

<!-- Image accessibility -->
<img src="profile.jpg" alt="Serkan Emre Sefa profil fotoğrafı" loading="lazy">

<!-- Button accessibility -->
<button type="button" aria-expanded="false" aria-controls="mobile-menu">
    <span class="sr-only">Menü aç/kapat</span>
    <span aria-hidden="true">☰</span>
</button>
```

### Meta Tags Standard
```html
<head>
    <!-- Basic Meta -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="UEFA Pro Coach, Futbol Antrenörlüğü Eğitimi">
    <meta name="keywords" content="futbol, antrenör, UEFA, eğitim, maç analizi">
    <meta name="author" content="Serkan Emre Sefa">
    
    <!-- Open Graph -->
    <meta property="og:title" content="Serkan Emre Sefa - UEFA Pro Coach">
    <meta property="og:description" content="Profesyonel futbol antrenörlüğü eğitimi">
    <meta property="og:image" content="https://example.com/og-image.jpg">
    <meta property="og:url" content="https://example.com">
    <meta property="og:type" content="website">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Serkan Emre Sefa - UEFA Pro Coach">
    <meta name="twitter:description" content="Profesyonel futbol antrenörlüğü eğitimi">
    <meta name="twitter:image" content="https://example.com/twitter-image.jpg">
    
    <!-- Favicon -->
    <link rel="icon" href="images/favicon.ico" type="image/x-icon">
    <link rel="icon" href="images/favicon.svg" type="image/svg+xml">
    <link rel="apple-touch-icon" href="images/apple-touch-icon.png">
</head>
```

## CSS Standards

### CSS Architecture
```css
/* 1. CSS Reset/Normalize */
/* 2. CSS Variables */
/* 3. Base Styles */
/* 4. Layout */
/* 5. Components */
/* 6. Utilities */
/* 7. Media Queries */

/* CSS Variables */
:root {
    /* Colors */
    --primary-color: #1a365d;
    --secondary-color: #2d3748;
    --accent-color: #3182ce;
    --text-color: #2d3748;
    --bg-color: #ffffff;
    --gray-100: #f7fafc;
    --gray-200: #edf2f7;
    --gray-300: #e2e8f0;
    
    /* Typography */
    --font-family-base: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    --font-family-heading: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    --font-size-xs: 0.75rem;
    --font-size-sm: 0.875rem;
    --font-size-base: 1rem;
    --font-size-lg: 1.125rem;
    --font-size-xl: 1.25rem;
    --font-size-2xl: 1.5rem;
    --font-size-3xl: 1.875rem;
    --font-size-4xl: 2.25rem;
    
    /* Spacing */
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 1.5rem;
    --spacing-xl: 2rem;
    --spacing-2xl: 3rem;
    --spacing-3xl: 4rem;
    
    /* Breakpoints */
    --breakpoint-sm: 640px;
    --breakpoint-md: 768px;
    --breakpoint-lg: 1024px;
    --breakpoint-xl: 1280px;
    
    /* Animations */
    --transition-fast: 0.15s ease-in-out;
    --transition-base: 0.3s ease-in-out;
    --transition-slow: 0.5s ease-in-out;
}
```

### Mobile-First Responsive Design
```css
/* Mobile styles (default) */
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--spacing-md);
}

/* Tablet styles */
@media (min-width: 768px) {
    .container {
        padding: 0 var(--spacing-lg);
    }
}

/* Desktop styles */
@media (min-width: 1024px) {
    .container {
        padding: 0 var(--spacing-xl);
    }
}

/* Large desktop styles */
@media (min-width: 1280px) {
    .container {
        padding: 0 var(--spacing-2xl);
    }
}
```

### Component Naming Convention (BEM)
```css
/* Block */
.card {
    background: var(--bg-color);
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    padding: var(--spacing-lg);
}

/* Element */
.card__title {
    font-size: var(--font-size-xl);
    font-weight: 600;
    margin-bottom: var(--spacing-md);
    color: var(--text-color);
}

.card__content {
    color: var(--gray-600);
    line-height: 1.6;
}

/* Modifier */
.card--highlighted {
    border: 2px solid var(--accent-color);
}

.card--large {
    padding: var(--spacing-xl);
}
```

## JavaScript Standards

### Modern JavaScript (ES6+)
```javascript
// Use const/let instead of var
const CONFIG = {
    API_URL: 'https://api.example.com',
    VERSION: '2.0.0'
};

let currentUser = null;

// Arrow functions
const fetchData = async (endpoint) => {
    try {
        const response = await fetch(`${CONFIG.API_URL}/${endpoint}`);
        return await response.json();
    } catch (error) {
        console.error('Fetch error:', error);
        throw error;
    }
};

// Destructuring
const { name, email } = userObject;
const [first, second] = arrayData;

// Template literals
const message = `Hello ${name}, welcome to our platform!`;

// Modules
export { fetchData };
import { fetchData } from './api.js';
```

### Event Handling
```javascript
// Modern event handling
class EventManager {
    constructor() {
        this.listeners = new Map();
    }
    
    // Add event listener
    on(element, event, handler, options = {}) {
        element.addEventListener(event, handler, options);
        
        // Store for cleanup
        if (!this.listeners.has(element)) {
            this.listeners.set(element, []);
        }
        this.listeners.get(element).push({ event, handler, options });
    }
    
    // Remove all listeners
    cleanup() {
        this.listeners.forEach((events, element) => {
            events.forEach(({ event, handler, options }) => {
                element.removeEventListener(event, handler, options);
            });
        });
        this.listeners.clear();
    }
}

// Usage
const eventManager = new EventManager();

eventManager.on(document, 'DOMContentLoaded', () => {
    initializeApp();
});

eventManager.on(window, 'resize', debounce(() => {
    handleResize();
}, 250));
```

### Error Handling
```javascript
// Comprehensive error handling
class ApiService {
    static async request(endpoint, options = {}) {
        try {
            const response = await fetch(endpoint, {
                headers: {
                    'Content-Type': 'application/json',
                    ...options.headers
                },
                ...options
            });
            
            if (!response.ok) {
                throw new Error(`HTTP ${response.status}: ${response.statusText}`);
            }
            
            const data = await response.json();
            return { success: true, data };
        } catch (error) {
            console.error('API Request failed:', error);
            
            // User-friendly error messages
            const userMessage = this.getUserFriendlyError(error);
            
            return { 
                success: false, 
                error: error.message, 
                userMessage 
            };
        }
    }
    
    static getUserFriendlyError(error) {
        if (error.message.includes('Failed to fetch')) {
            return 'Bağlantı hatası. Lütfen internet bağlantınızı kontrol edin.';
        }
        return 'Beklenmeyen bir hata oluştu. Lütfen tekrar deneyin.';
    }
}
```

### Performance Utilities
```javascript
// Debounce function
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

// Throttle function
const throttle = (func, limit) => {
    let inThrottle;
    return function executedFunction(...args) {
        if (!inThrottle) {
            func.apply(this, args);
            inThrottle = true;
            setTimeout(() => inThrottle = false, limit);
        }
    };
};

// Lazy loading
const lazyLoad = (entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.classList.remove('lazy');
            observer.unobserve(img);
        }
    });
};

const imageObserver = new IntersectionObserver(lazyLoad, {
    rootMargin: '50px'
});
```

## File Organization

### Directory Structure
```
serkanemresefa/
├── index.html
├── assets/
│   ├── css/
│   │   ├── main.css
│   │   ├── components/
│   │   │   ├── header.css
│   │   │   ├── hero.css
│   │   │   └── footer.css
│   │   └── utilities/
│   │       ├── reset.css
│   │       └── utilities.css
│   ├── js/
│   │   ├── main.js
│   │   ├── components/
│   │   │   ├── header.js
│   │   │   ├── hero.js
│   │   │   └── contact.js
│   │   └── utils/
│   │       ├── api.js
│   │       ├── helpers.js
│   │       └── validators.js
│   └── images/
│       ├── hero/
│       ├── portfolio/
│       └── icons/
├── components/
│   ├── header/
│   ├── hero/
│   ├── about/
│   ├── education/
│   ├── portfolio/
│   ├── tools/
│   └── contact/
└── docs/
    ├── ARCHITECTURE.md
    ├── DEVELOPMENT.md
    ├── MODULES.md
    ├── ROADMAP.md
    └── STANDARDS.md
```

### Naming Conventions
- **Files**: `kebab-case.ext`
- **Directories**: `kebab-case/`
- **CSS Classes**: `kebab-case` (BEM)
- **JavaScript Variables**: `camelCase`
- **JavaScript Constants**: `UPPER_SNAKE_CASE`
- **JavaScript Functions**: `camelCase`
- **JavaScript Classes**: `PascalCase`

## Git Standards

### Commit Message Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Commit Types
- **feat**: Yeni özellik
- **fix**: Bug fix
- **docs**: Dokümantasyon değişikliği
- **style**: Kod formatı değişikliği
- **refactor**: Kod refactoring
- **test**: Test ekleme/düzenleme
- **chore**: Build/maintenance tasks

### Commit Examples
```bash
feat(hero): add animated hero section with CTA buttons

- Implement hero section with professional profile display
- Add smooth animations for text and buttons
- Include responsive design for mobile devices
- Add accessibility features for screen readers

Closes #123

fix(navigation): resolve mobile menu toggle issue

- Fix hamburger menu not responding on mobile
- Improve touch target size for better UX
- Add proper ARIA attributes for accessibility

style(css): reorganize stylesheet structure

- Split main.css into component-specific files
- Add CSS variables for consistent theming
- Improve comment structure and organization

docs(readme): update installation instructions

- Add detailed setup steps
- Include troubleshooting section
- Update dependencies list
```

### Branch Naming
- **Feature**: `feature/hero-section`
- **Bug Fix**: `fix/navigation-mobile`
- **Hotfix**: `hotfix/critical-security`
- **Release**: `release/v2.0.0`

## Testing Standards

### Manual Testing Checklist
```markdown
## Browser Testing
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)

## Device Testing
- [ ] iPhone (Safari)
- [ ] Android (Chrome)
- [ ] iPad (Safari)
- [ ] Desktop (1920x1080)

## Accessibility Testing
- [ ] Keyboard navigation
- [ ] Screen reader compatibility
- [ ] Color contrast
- [ ] Focus indicators

## Performance Testing
- [ ] Page load speed < 3s
- [ ] Lighthouse score > 90
- [ ] Mobile performance
- [ ] Image optimization
```

### Code Quality Checks
```javascript
// ESLint configuration example
module.exports = {
    extends: ['eslint:recommended'],
    env: {
        browser: true,
        es6: true
    },
    rules: {
        'no-console': 'warn',
        'no-unused-vars': 'error',
        'prefer-const': 'error',
        'no-var': 'error'
    }
};
```

## Documentation Standards

### Code Comments
```javascript
/**
 * Calculates the responsive breakpoint for given screen size
 * @param {number} screenWidth - Current screen width in pixels
 * @returns {string} Breakpoint name (mobile, tablet, desktop, xl)
 */
const getBreakpoint = (screenWidth) => {
    if (screenWidth < 768) return 'mobile';
    if (screenWidth < 1024) return 'tablet';
    if (screenWidth < 1280) return 'desktop';
    return 'xl';
};

// TODO: Add support for custom breakpoints
// FIXME: Handle edge case when screenWidth is negative
// NOTE: This function is called frequently, consider memoization
```

### README Template
```markdown
# Component Name

## Description
Brief description of the component's purpose.

## Usage
```javascript
// Example usage
const component = new Component();
component.init();
```

## Props/Options
- `option1` (string): Description of option1
- `option2` (boolean): Description of option2

## Methods
- `init()`: Initialize the component
- `destroy()`: Clean up the component

## Events
- `component:ready`: Fired when component is ready
- `component:error`: Fired when an error occurs

## Browser Support
- Chrome 70+
- Firefox 65+
- Safari 12+
- Edge 79+
```

## Security Standards

### Input Validation
```javascript
// Form validation
const validateForm = (formData) => {
    const errors = {};
    
    // Email validation
    if (!formData.email || !isValidEmail(formData.email)) {
        errors.email = 'Geçerli bir email adresi girin';
    }
    
    // XSS prevention
    if (formData.message) {
        formData.message = sanitizeHtml(formData.message);
    }
    
    return {
        isValid: Object.keys(errors).length === 0,
        errors
    };
};

const isValidEmail = (email) => {
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailRegex.test(email);
};

const sanitizeHtml = (input) => {
    const div = document.createElement('div');
    div.textContent = input;
    return div.innerHTML;
};
```

### Content Security Policy
```html
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self'; 
               script-src 'self' 'unsafe-inline'; 
               style-src 'self' 'unsafe-inline'; 
               img-src 'self' data: https:; 
               font-src 'self' https:">
```

## Performance Standards

### Core Web Vitals Targets
- **Largest Contentful Paint (LCP)**: < 2.5s
- **First Input Delay (FID)**: < 100ms
- **Cumulative Layout Shift (CLS)**: < 0.1

### Optimization Techniques
```javascript
// Image lazy loading
const lazyLoadImages = () => {
    const images = document.querySelectorAll('img[data-src]');
    const imageObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const img = entry.target;
                img.src = img.dataset.src;
                img.removeAttribute('data-src');
                imageObserver.unobserve(img);
            }
        });
    });
    
    images.forEach(img => imageObserver.observe(img));
};

// Critical CSS inlining
const loadCSS = (href) => {
    const link = document.createElement('link');
    link.rel = 'stylesheet';
    link.href = href;
    document.head.appendChild(link);
};
```

---

*Bu standartlar, proje geliştirme süresince takip edilmeli ve düzenli olarak güncellenmelidir.*

**Son Güncelleme**: 2025-07-16  
**Geçerlilik**: Proje süresince  
**Review Frequency**: Aylık