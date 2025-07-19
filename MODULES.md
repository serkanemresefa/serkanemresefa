# MODULES.md - Modül Development Rehberi

## Modüler Yapı Genel Bakış

Proje modüler bir yapıda tasarlanmıştır. Her modül kendi sorumluluğunu üstlenir ve diğer modüllerle minimal bağımlılık içinde çalışır.

## Mevcut Modüller

### 1. Header Module
**Dosya**: `components/header/`
```
header/
├── header.html
├── header.css
├── header.js
└── README.md
```

**Sorumluluklar**:
- Site navigasyonu
- Logo ve branding
- Dil seçimi (gelecek faz)
- Responsive menü

**API**:
```javascript
// Header module API
const HeaderModule = {
    init: () => {},
    toggleMobileMenu: () => {},
    setActiveMenuItem: (itemId) => {},
    updateLanguage: (lang) => {}
};
```

### 2. Hero Module
**Dosya**: `components/hero/`
```
hero/
├── hero.html
├── hero.css
├── hero.js
├── animations.css
└── README.md
```

**Sorumluluklar**:
- İlk izlenim ve ana mesaj
- Profil fotoğrafı ve tanıtım
- Call-to-action butonları
- Animasyonlar

**API**:
```javascript
const HeroModule = {
    init: () => {},
    startAnimations: () => {},
    handleCTAClick: (action) => {},
    updateContent: (content) => {}
};
```

### 3. About Module
**Dosya**: `components/about/`
```
about/
├── about.html
├── about.css
├── about.js
├── timeline.css
└── README.md
```

**Sorumluluklar**:
- Profesyonel geçmiş
- Sertifikalar ve eğitim
- Uzmanlık alanları
- Timeline görünümü

**API**:
```javascript
const AboutModule = {
    init: () => {},
    loadTimeline: () => {},
    showCertificate: (certId) => {},
    filterExperience: (category) => {}
};
```

### 4. Education Module
**Dosya**: `components/education/`
```
education/
├── education.html
├── education.css
├── education.js
├── tabs.css
├── modal.css
└── README.md
```

**Sorumluluklar**:
- UEFA lisans programları
- Sertifika programları
- Eğitim içeriği showcase
- İnteraktif tabs

**API**:
```javascript
const EducationModule = {
    init: () => {},
    showProgram: (programId) => {},
    openModal: (contentId) => {},
    loadCurriculum: (programId) => {}
};
```

### 5. Portfolio Module
**Dosya**: `components/portfolio/`
```
portfolio/
├── portfolio.html
├── portfolio.css
├── portfolio.js
├── gallery.css
├── lightbox.css
└── README.md
```

**Sorumluluklar**:
- Proje showcase
- Kulüp deneyimleri
- Başarı hikayeleri
- Görsel galeri

**API**:
```javascript
const PortfolioModule = {
    init: () => {},
    showProject: (projectId) => {},
    openLightbox: (imageId) => {},
    filterProjects: (category) => {}
};
```

### 6. Tools Module
**Dosya**: `components/tools/`
```
tools/
├── tools.html
├── tools.css
├── tools.js
├── integration.js
└── README.md
```

**Sorumluluklar**:
- X platform araçları entegrasyonu
- İnteraktif demo'lar
- Analiz araçları showcase
- iFrame yönetimi

**API**:
```javascript
const ToolsModule = {
    init: () => {},
    loadDemo: (toolId) => {},
    resizeIframe: (iframe) => {},
    trackUsage: (toolId) => {}
};
```

### 7. Contact Module
**Dosya**: `components/contact/`
```
contact/
├── contact.html
├── contact.css
├── contact.js
├── form-validation.js
└── README.md
```

**Sorumluluklar**:
- İletişim formu
- Form validasyonu
- Email gönderimi
- Sosyal medya linkleri

**API**:
```javascript
const ContactModule = {
    init: () => {},
    validateForm: (formData) => {},
    submitForm: (formData) => {},
    showNotification: (message, type) => {}
};
```

## Yeni Modül Ekleme

### 1. Modül Klasörü Oluşturma
```bash
mkdir components/new-module
cd components/new-module
```

### 2. Temel Dosyalar
```bash
# HTML template
touch new-module.html

# CSS styles
touch new-module.css

# JavaScript functionality
touch new-module.js

# Documentation
touch README.md
```

### 3. Modül Template'i
**new-module.html**:
```html
<section class="new-module" id="new-module">
    <div class="container">
        <h2 class="module-title">New Module</h2>
        <div class="module-content">
            <!-- Module content -->
        </div>
    </div>
</section>
```

**new-module.css**:
```css
.new-module {
    /* Module styles */
    padding: 60px 0;
    background-color: var(--bg-color);
}

.new-module .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

.module-title {
    text-align: center;
    margin-bottom: 40px;
    font-size: 2.5rem;
    color: var(--primary-color);
}

/* Responsive design */
@media (max-width: 768px) {
    .new-module {
        padding: 40px 0;
    }
    
    .module-title {
        font-size: 2rem;
    }
}
```

**new-module.js**:
```javascript
const NewModule = {
    // Module configuration
    config: {
        animationDuration: 300,
        breakpoints: {
            mobile: 768,
            tablet: 1024
        }
    },

    // Initialize module
    init() {
        this.bindEvents();
        this.setupAnimations();
        console.log('NewModule initialized');
    },

    // Bind event listeners
    bindEvents() {
        // Event bindings
    },

    // Setup animations
    setupAnimations() {
        // Animation setup
    },

    // Public methods
    publicMethod() {
        // Public functionality
    },

    // Private methods
    _privateMethod() {
        // Private functionality
    }
};

// Auto-initialize on DOM ready
document.addEventListener('DOMContentLoaded', () => {
    NewModule.init();
});

// Export for use in other modules
if (typeof module !== 'undefined' && module.exports) {
    module.exports = NewModule;
}
```

**README.md**:
```markdown
# New Module

## Description
Brief description of the module's purpose and functionality.

## Features
- Feature 1
- Feature 2
- Feature 3

## Usage
```javascript
// Initialize module
NewModule.init();

// Use public methods
NewModule.publicMethod();
```

## Dependencies
- List any dependencies
- CSS variables from main.css
- JavaScript utilities

## Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge)
- IE11+ (if needed)

## Testing
- Unit tests location
- Integration tests
- Manual testing steps
```

### 4. Ana Dosyalara Entegrasyon
**index.html'e ekleme**:
```html
<!-- New Module -->
<link rel="stylesheet" href="components/new-module/new-module.css">
<script src="components/new-module/new-module.js"></script>

<!-- HTML content -->
<main>
    <!-- Other modules -->
    
    <!-- New Module -->
    <div id="new-module-container"></div>
    
    <!-- Other modules -->
</main>
```

**main.css'e ekleme**:
```css
/* Import new module styles */
@import url('components/new-module/new-module.css');
```

**main.js'e ekleme**:
```javascript
// Import new module
import NewModule from './components/new-module/new-module.js';

// Initialize in main app
const App = {
    init() {
        // Other module initializations
        NewModule.init();
    }
};
```

## Modül İletişimi

### Event System
```javascript
// Custom event dispatch
const moduleEvent = new CustomEvent('moduleAction', {
    detail: { data: 'some data' }
});
document.dispatchEvent(moduleEvent);

// Event listener
document.addEventListener('moduleAction', (e) => {
    console.log('Module action:', e.detail.data);
});
```

### Shared State Management
```javascript
// Global state object
const AppState = {
    currentLanguage: 'tr',
    activeModule: null,
    userData: {},
    
    // State methods
    setState(key, value) {
        this[key] = value;
        this.notifyModules(key, value);
    },
    
    getState(key) {
        return this[key];
    },
    
    notifyModules(key, value) {
        const stateChangeEvent = new CustomEvent('stateChange', {
            detail: { key, value }
        });
        document.dispatchEvent(stateChangeEvent);
    }
};
```

### Module Registry
```javascript
// Module registry for managing modules
const ModuleRegistry = {
    modules: new Map(),
    
    register(name, module) {
        this.modules.set(name, module);
    },
    
    get(name) {
        return this.modules.get(name);
    },
    
    initializeAll() {
        this.modules.forEach((module, name) => {
            if (module.init) {
                module.init();
                console.log(`${name} module initialized`);
            }
        });
    }
};

// Register modules
ModuleRegistry.register('header', HeaderModule);
ModuleRegistry.register('hero', HeroModule);
ModuleRegistry.register('about', AboutModule);
```

## Modül Testing

### Unit Testing Template
```javascript
// new-module.test.js
describe('NewModule', () => {
    beforeEach(() => {
        // Setup DOM
        document.body.innerHTML = `
            <div id="new-module-container"></div>
        `;
        
        // Initialize module
        NewModule.init();
    });
    
    afterEach(() => {
        // Cleanup
        document.body.innerHTML = '';
    });
    
    test('should initialize correctly', () => {
        expect(NewModule.config).toBeDefined();
        expect(typeof NewModule.init).toBe('function');
    });
    
    test('should bind events', () => {
        // Test event binding
    });
    
    test('public method should work', () => {
        // Test public methods
    });
});
```

### Integration Testing
```javascript
// Integration test for module communication
describe('Module Integration', () => {
    test('modules should communicate via events', () => {
        // Test inter-module communication
    });
    
    test('state changes should update modules', () => {
        // Test state management
    });
});
```

## Performance Optimization

### Lazy Loading
```javascript
// Lazy load modules
const lazyLoadModule = (moduleName) => {
    return new Promise((resolve) => {
        const script = document.createElement('script');
        script.src = `components/${moduleName}/${moduleName}.js`;
        script.onload = resolve;
        document.head.appendChild(script);
    });
};

// Usage
lazyLoadModule('portfolio').then(() => {
    PortfolioModule.init();
});
```

### Code Splitting
```javascript
// Dynamic imports (for modern browsers)
const loadModule = async (moduleName) => {
    const module = await import(`./components/${moduleName}/${moduleName}.js`);
    return module.default;
};

// Usage
loadModule('tools').then(ToolsModule => {
    ToolsModule.init();
});
```

## Deployment Checklist

### Yeni Modül Deployment
- [ ] Modül dosyaları oluşturuldu
- [ ] CSS/JS entegrasyonu yapıldı
- [ ] Cross-browser testing tamamlandı
- [ ] Performance testi yapıldı
- [ ] Documentation güncellendi
- [ ] Git commit/push yapıldı

### Modül Güncelleme
- [ ] Backward compatibility kontrol edildi
- [ ] Dependent modüller test edildi
- [ ] Version numarası güncellendi
- [ ] Changelog güncellendi

---

*Bu modül rehberi, yeni modüller eklendikçe güncellenecektir.*