# Cursor Abu Dhabi Slides - Style Guide

## 🎨 Design Philosophy

Esta presentación fue transformada de slides estáticas a una experiencia **energética, vibrante y minimalista** para el evento Cursor Abu Dhabi del 2 de agosto de 2025.

## 🌈 Color Palette

### Primary Colors
- **Rosa vibrante:** `from-[#EC4899] to-[#F472B6]`
- **Azul energético:** `from-[#1E3A8A] to-[#3B82F6]`
- **Verde dinámico:** `from-[#059669] to-[#10B981]`
- **Naranja brillante:** `from-[#F59E0B] to-[#F97316]`
- **Púrpura moderno:** `from-[#7C3AED] to-[#A855F7]`
- **Cian vibrante:** `from-[#06B6D4] to-[#0EA5E9]`
- **Rojo pasión:** `from-[#DC2626] to-[#EF4444]`

### Social Media Colors
- **Twitter Blue:** `from-[#1DA1F2] to-[#0284C7]`
- **LinkedIn Blue:** `from-[#0A66C2] to-[#004182]`

## ✨ Animation System

### Hover Effects
```css
/* Scale + Shadow Pattern */
transform hover:scale-105 transition-all duration-300 hover:shadow-2xl hover:shadow-[color]/25

/* Emoji Bounce Pattern */
group-hover:animate-bounce

/* Magnetic Rotation */
hover:rotate-12 / hover:-rotate-12
```

### Continuous Animations
- **Pulse:** `animate-pulse` - Para títulos principales
- **Bounce:** `animate-bounce` - Para subtítulos y elementos dinámicos
- **Spin:** `animate-spin` (4s duration) - Para conceptos de pensamiento
- **Ping:** `animate-ping` (2s duration) - Para elementos de acción

### Cascading Effects
Emojis con delays escalonados:
```css
style="animation-delay: 0.1s"
style="animation-delay: 0.2s"
style="animation-delay: 0.3s"
```

## 🎯 Typography Scale

### Headers
- **H1 Principal:** `text-7xl` → `text-6xl` (compacto)
- **H2 Secciones:** `text-3xl` → `text-2xl`
- **H3 Subsecciones:** `text-xl` → `text-lg`

### Body Text
- **Párrafos principales:** `text-lg` → `text-sm`
- **Texto descriptivo:** `text-sm` → `text-xs`
- **Opacidad estándar:** `text-white/90` para contenido, `text-white/80` para descripciones

## 📐 Spacing System

### Compactación Progresiva
- **Gaps principales:** `gap-8` → `gap-6` → `gap-4` → `gap-3`
- **Margins:** `mt-16` → `mt-12` → `mt-8` → `mt-6` → `mt-4`
- **Padding:** `p-8` → `p-6` → `p-5` → `p-4` → `p-3`

### Container Widths
- **Máximo ancho:** `max-w-5xl` → `max-w-4xl` → `max-w-3xl` → `max-w-2xl` → `max-w-xl`

## 🎪 Interactive Elements

### Welcome Section
```css
/* Host Cards */
bg-gradient-to-br from-[#7C3AED] to-[#A855F7] (Juanjo)
bg-gradient-to-br from-[#EC4899] to-[#F472B6] (Juan Bautista)

/* Avatar Effects */
bg-gradient-to-br from-[#F97316] to-[#FBBF24] border-2 border-white shadow-lg
```

### About Your Host
```css
/* Professional Card */
group bg-gradient-to-br from-[#1E3A8A] to-[#3B82F6] 
transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/25

/* Personal Card */
group bg-gradient-to-br from-[#059669] to-[#10B981]
transform hover:scale-105 hover:shadow-2xl hover:shadow-green-500/25
```

## 🚀 Slide-Specific Styles

### Cursor Is All You Need (Hero)
```css
/* Title with pulse */
text-7xl animate-pulse

/* Subtitle with bounce */
text-2xl animate-bounce

/* Interactive emojis */
text-4xl hover:scale-150 hover:rotate-12 transition-transform duration-500
```

### What is Cursor? (Compact)
```css
/* Compact layout */
gap-4 mt-4

/* Animated concepts grid */
grid-cols-2 gap-3 max-w-2xl

/* Emoji animations */
text-xl animate-spin|pulse|bounce|ping
```

### Core Features
```css
/* Feature cards with gradients */
bg-gradient-to-br from-[#1E3A8A] to-[#3B82F6] (Tab)
bg-gradient-to-br from-[#059669] to-[#10B981] (Edit)
bg-gradient-to-br from-[#D97706] to-[#F59E0B] (Agent)
bg-gradient-to-br from-[#DC2626] to-[#EF4444] (BugBot)
```

### Why Cursor Is All You Need
```css
/* 2x2 Grid with unique colors */
grid-cols-2 gap-6

/* Knowledge Hub */
bg-gradient-to-br from-[#EC4899] to-[#F472B6]

/* Content Creator */
bg-gradient-to-br from-[#06B6D4] to-[#0EA5E9]

/* Team & Personal */
bg-gradient-to-br from-[#F59E0B] to-[#F97316]

/* Always Evolving */
bg-gradient-to-br from-[#8B5CF6] to-[#A78BFA]
```

### Q&A Section
```css
/* Large gradient title */
text-8xl bg-gradient-to-r from-[#EC4899] to-[#A855F7] bg-clip-text text-transparent

/* Animated bars */
w-8 h-2 bg-gradient-to-r animate-pulse (with delays)

/* Interactive cards */
bg-gradient-to-br from-[#EC4899] to-[#F472B6] (Ask Anything)
bg-gradient-to-br from-[#A855F7] to-[#7C3AED] (Share Ideas)
```

### Demo Time
```css
/* Title gradient */
text-7xl bg-gradient-to-r from-[#F59E0B] to-[#06B6D4]

/* Demo cards */
bg-gradient-to-br from-[#F59E0B] to-[#F97316] (Quick Slides)
bg-gradient-to-br from-[#10B981] to-[#059669] (Knowledge)
bg-gradient-to-br from-[#06B6D4] to-[#0EA5E9] (AI Coding)
```

### Thank You (Compact)
```css
/* Compact social cards */
max-w-3xl gap-3 p-3

/* Branded colors */
bg-gradient-to-br from-[#1DA1F2] to-[#0284C7] (Twitter)
bg-gradient-to-br from-[#0A66C2] to-[#004182] (LinkedIn)
bg-gradient-to-br from-[#7C3AED] to-[#A855F7] (AI Community)

/* Final message */
bg-gradient-to-br from-[#F59E0B] to-[#10B981] rounded-2xl p-4
```

## 🎭 Special Effects

### Glassmorphism (Not used, kept minimal)
```css
/* Subtle glass effects when needed */
bg-gradient-to-r from-white/10 to-white/5 backdrop-blur-sm border border-white/20
```

### Shadow System
```css
/* Color-matched shadows */
hover:shadow-2xl hover:shadow-blue-500/25
hover:shadow-2xl hover:shadow-green-500/25
hover:shadow-2xl hover:shadow-purple-500/25
hover:shadow-2xl hover:shadow-pink-500/25
```

## 📱 Responsive Approach

### Mobile-First Scaling
- **Emoji sizes:** `text-6xl` → `text-4xl` → `text-3xl` → `text-2xl` → `text-xl`
- **Container widths:** Progressive reduction from `max-w-5xl` to `max-w-xl`
- **Spacing:** Consistent reduction maintaining proportions

### Compact Mode
Para pantallas pequeñas, todos los elementos se reducen ~30% manteniendo legibilidad y animaciones.

## 🎪 Animation Performance

### CSS Animations Used
```css
@keyframes floating {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

/* Tailwind built-ins optimized */
animate-pulse, animate-bounce, animate-spin, animate-ping
```

### Transition Standards
- **Hover transitions:** `transition-all duration-300`
- **Scale effects:** `hover:scale-105`
- **Long animations:** `duration-500` for dramatic effects

## 🎯 Content Guidelines

### Emoji Usage
- **Functional emojis:** 🧠💻🚀⚡🎯📝🔤🤖
- **Geographic:** 🇦🇪 para UAE
- **Social:** 🐦💼🤖 para redes sociales
- **Actions:** ✨⚡🔥 para energy

### Text Hierarchy
1. **Slide titles:** Bold, large, animated
2. **Section headers:** Medium, gradient text when appropriate
3. **Content:** Clean, readable, proper opacity
4. **Descriptions:** Small but legible, `text-white/80`

## 🚀 Implementation Notes

### Framework Compatibility
- **Slidev-ready:** All animations work with Slidev
- **Tailwind CSS:** Utility-first approach
- **No custom CSS:** Everything uses Tailwind classes
- **Performance:** Hardware-accelerated transforms only

### Browser Support
- **Modern browsers:** Full animation support
- **Fallback:** Graceful degradation without animations
- **Mobile:** Touch-friendly hover states

---

## 📋 Quick Reference

### Color Combinations That Work
- **Blue + Orange:** Professional + Creative
- **Purple + Pink:** Modern + Vibrant  
- **Green + Cyan:** Growth + Tech
- **Red + Yellow:** Energy + Action

### Animation Timing
- **Fast:** 300ms for hovers
- **Medium:** 500ms for dramatic effects
- **Slow:** 2-4s for continuous animations

### Spacing Scale
- **Tight:** gap-3, mt-4, p-3
- **Normal:** gap-6, mt-8, p-6  
- **Loose:** gap-12, mt-16, p-8

---

*Esta guía documenta la transformación completa de las slides estáticas de Cursor Dubai a la versión energética y vibrante de Cursor Abu Dhabi 2025.* 🎉