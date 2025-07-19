# DEVELOPMENT.md - Development Guide

## Setup ve Kurulum

### Gereksinimler
- **Web Browser**: Modern browser (Chrome, Firefox, Safari, Edge)
- **Code Editor**: VS Code, Sublime Text, veya benzeri
- **Git**: Version control için
- **Python**: X platform entegrasyonları için (optional)

### Proje Kurulumu
```bash
# Proje klonlama
git clone <repository-url>
cd serkanemresefa

# Geliştirme ortamı hazırlama
# Basit HTTP server başlatma
python -m http.server 8000
# veya
npx serve .

# Browser'da açma
open http://localhost:8000
```

## Geliştirme Komutları

### Temel Komutlar
```bash
# Proje durumunu kontrol etme
git status

# Değişiklikleri stage'e alma
git add .

# Commit oluşturma
git commit -m "feat: new feature implementation"

# Push işlemi
git push origin main
```

### Dosya Yapısı Kontrolleri
```bash
# HTML validasyonu
# Online: https://validator.w3.org/
# Local: html5validator index.html

# CSS validasyonu
# Online: https://jigsaw.w3.org/css-validator/

# JavaScript linting
# ESLint kullanımı (gelecek faz)
npx eslint assets/js/
```

## Geliştirme Workflow'u

### 1. Branch Stratejisi
```bash
# Feature branch oluşturma
git checkout -b feature/new-section

# Development branch'e merge
git checkout develop
git merge feature/new-section

# Main branch'e release
git checkout main
git merge develop
```

### 2. Commit Konvansiyonları
```bash
# Feature ekleme
git commit -m "feat: add hero section with animations"

# Bug fix
git commit -m "fix: resolve mobile responsive issues"

# Styling değişiklikleri
git commit -m "style: improve header navigation design"

# Refactoring
git commit -m "refactor: reorganize CSS structure"

# Dokumentasyon
git commit -m "docs: update development guide"
```

### 3. Testing Süreci
```bash
# Manual testing checklist
# - Desktop browsers (Chrome, Firefox, Safari, Edge)
# - Mobile devices (iOS Safari, Android Chrome)
# - Tablet devices
# - Accessibility testing
# - Performance testing

# Automated testing (gelecek faz)
npm test
```

## Dosya Organizasyonu

### Proje Yapısı
```
serkanemresefa/
├── index.html                 # Ana sayfa
├── assets/                    # Statik dosyalar
│   ├── css/
│   │   ├── main.css          # Ana stil dosyası
│   │   ├── responsive.css    # Responsive stiller
│   │   └── components/       # Bileşen stilleri
│   ├── js/
│   │   ├── main.js           # Ana JavaScript
│   │   └── components/       # Bileşen scriptleri
│   └── images/               # Optimized görseller
├── components/               # HTML bileşenleri
├── integrations/            # X platform entegrasyonları
└── docs/                    # Proje dokümantasyonu
```

### Dosya Adlandırma Kuralları
- **HTML**: `kebab-case.html`
- **CSS**: `kebab-case.css`
- **JavaScript**: `camelCase.js`
- **Images**: `kebab-case.jpg/png/svg`
- **Directories**: `kebab-case/`

## Kodlama Standartları

### HTML Standartları
```html
<!-- HTML5 semantic structure -->
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Serkan Emre Sefa</title>
</head>
<body>
    <header>
        <nav aria-label="Main navigation">
            <!-- Navigation content -->
        </nav>
    </header>
    <main>
        <!-- Main content -->
    </main>
    <footer>
        <!-- Footer content -->
    </footer>
</body>
</html>
```

### CSS Standartları
```css
/* CSS organization */
/* 1. Reset/normalize */
/* 2. Variables */
/* 3. Base styles */
/* 4. Layout */
/* 5. Components */
/* 6. Utilities */
/* 7. Media queries */

:root {
    --primary-color: #333;
    --secondary-color: #666;
    --accent-color: #0066cc;
    --font-family: 'Helvetica', Arial, sans-serif;
}

/* Mobile-first approach */
.component {
    /* Mobile styles */
}

@media (min-width: 768px) {
    .component {
        /* Tablet styles */
    }
}

@media (min-width: 1024px) {
    .component {
        /* Desktop styles */
    }
}
```

### JavaScript Standartları
```javascript
// ES6+ syntax
const config = {
    apiUrl: 'https://api.example.com',
    version: '2.0'
};

// Arrow functions
const initializeApp = () => {
    // App initialization
};

// Modules
export { initializeApp };
import { initializeApp } from './config.js';

// Event listeners
document.addEventListener('DOMContentLoaded', initializeApp);
```

## X Platform Entegrasyonu

### İnteraktif Araçlar Entegrasyonu
```bash
# X platform araçlarını test etme
cd ../X/EDUCATION/Interactive-Apps/
python -m http.server 8001

# iFrame entegrasyonu test etme
# index.html içinde:
<iframe src="http://localhost:8001/C2-FutbolOyuncuAnalizSistemi.html"></iframe>
```

### Eğitim İçeriği Entegrasyonu
```bash
# UEFA lisans içeriklerini inceleme
ls ../X/EDUCATION/UEFA-Licenses/
ls ../X/EDUCATION/Specialist-Certs/

# İçerik yapısını anlama
cat ../X/EDUCATION/UEFA-Licenses/UEFA-C/modules.json
```

## Debugging ve Troubleshooting

### Yaygın Sorunlar
1. **Responsive Issues**
   ```css
   /* Debug helper */
   * {
       border: 1px solid red;
   }
   ```

2. **JavaScript Errors**
   ```javascript
   // Console debugging
   console.log('Debug info:', variable);
   console.error('Error:', error);
   ```

3. **CSS Conflicts**
   ```css
   /* Specificity debugging */
   .component {
       color: red !important; /* Temporary debug */
   }
   ```

### Browser DevTools
- **Elements**: HTML/CSS inspection
- **Console**: JavaScript debugging
- **Network**: Resource loading
- **Performance**: Performance profiling
- **Application**: Storage inspection

## Performance Optimization

### Image Optimization
```bash
# Image compression
# Tools: TinyPNG, ImageOptim, Squoosh

# WebP conversion
cwebp input.jpg -o output.webp

# Responsive images
<img src="image-small.jpg" 
     srcset="image-small.jpg 320w, 
             image-medium.jpg 768w, 
             image-large.jpg 1200w"
     sizes="(max-width: 768px) 320px, 
            (max-width: 1200px) 768px, 
            1200px"
     alt="Description">
```

### CSS Optimization
```css
/* Critical CSS inline */
<style>
    /* Above-the-fold styles */
</style>

/* Non-critical CSS async */
<link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
```

### JavaScript Optimization
```javascript
// Lazy loading
const lazyLoad = (entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            // Load content
            observer.unobserve(entry.target);
        }
    });
};

const observer = new IntersectionObserver(lazyLoad);
```

## Deployment

### GitHub Pages Deployment
```bash
# Settings > Pages > Source: Deploy from a branch
# Branch: main
# URL: https://username.github.io/serkanemresefa/
```

### Manual Deployment
```bash
# Build process (gelecek faz)
npm run build

# Deploy to production
rsync -av dist/ user@server:/var/www/html/
```

## Monitoring ve Analytics

### Performance Monitoring
- **Google PageSpeed Insights**
- **GTmetrix**
- **WebPageTest**
- **Lighthouse**

### Analytics Integration
```javascript
// Google Analytics (gelecek faz)
gtag('config', 'GA_TRACKING_ID');

// User behavior tracking
gtag('event', 'click', {
    event_category: 'engagement',
    event_label: 'hero-cta'
});
```

## Bakım ve Güncelleme

### Düzenli Kontroller
- **Haftalık**: Broken links kontrolü
- **Aylık**: Performance audit
- **Çeyrek dönem**: Security update
- **Yılda**: Full redesign review

### Güncelleme Süreci
1. **Backup**: Mevcut versiyonu yedekleme
2. **Staging**: Test ortamında güncelleme
3. **Testing**: Kapsamlı test süreci
4. **Deployment**: Production'a yayınlama
5. **Monitoring**: Post-deployment izleme

---

*Bu geliştirme rehberi, proje gelişimi boyunca güncellenecektir.*