# 🗺️ КАРТА ЗВ'ЯЗКІВ: ФАЙЛИ БАЗИ ДАНИХ
## Візуалізація взаємозалежностей та рекомендованих комбінацій

---

## 📊 ЛЕГЕНДА

```
[FILE] ──────> [FILE]  = "Часто використовується разом"
[FILE] ═════> [FILE]  = "Критична залежність"
[FILE] - - -> [FILE]  = "Опціональний зв'язок"
```

**Критичність:**
- 🔴 CRITICAL (must have)
- 🟡 HIGH (strongly recommended)
- 🟢 MEDIUM (nice to have)

---

# ЯДРО СИСТЕМИ (Core Hub)

```
                    ┌─────────────────────┐
                    │   6.1 AI PROMPTING  │ 🔴
                    │   (Central Hub)     │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
     ┌────────────┐   ┌────────────┐   ┌────────────┐
     │ 2.1 Design │   │ 3.1 Landing│   │ 4.1 Vitals │
     │ Responsive │🔴 │ Structures │🔴 │ Performance│🔴
     └────────────┘   └────────────┘   └────────────┘
```

**Ці 4 файли = 60% всіх проектів**

---

# КАТЕГОРІЯ 1: ТЕХНОЛОГІЇ (Foundation Layer)

```
1.1 HTML Semantic ═══════════> 2.1 Responsive Design
       │                              │
       │                              ▼
       └────────────────────> 3.1 Landing Structures
       │
       └───────────────> 4.1 Core Web Vitals


1.2 CSS Frameworks ═════════> 2.1 Responsive Design
       │                           │
       └────────> 1.4 Preprocessors│
                         │         │
                         └─────────┴────> 4.3 Code Optimization


1.3 JavaScript ═════════> 2.2 Navigation
       │                       │
       ├──────────────> 2.4 Touch Interactions
       │                       │
       └──────────────> 2.5 UX Patterns


1.4 Preprocessors ──────> 4.3 Code Optimization
       │
       └──────────────> 1.5 Build Tools


1.5 Build Tools ═══════> 4.3 Code Optimization
       │
       └──────────────> 7.4 CI/CD
```

**Використання:**
- Почни з 1.1 + 1.2 для structure
- Додай 1.3 для interactivity
- 1.4 + 1.5 для optimization

---

# КАТЕГОРІЯ 2: DESIGN PATTERNS (UI Layer)

```
                    2.1 Responsive Design 🔴
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
      2.2 Navigation  2.3 Layout    2.4 Touch
              │             │             │
              └─────────────┴─────────────┘
                            │
                            ▼
                      2.5 UX Patterns


ЗОВНІШНІ ЗВ'ЯЗКИ:

2.1 ═════════> 3.1 Landing (CRITICAL)
2.1 ═════════> 4.1 Core Vitals (CRITICAL)
2.1 ─────────> 1.1 HTML Semantic

2.2 ─────────> 1.3 JavaScript
2.2 ─────────> 2.4 Touch

2.3 ═════════> 3.1 Landing
2.3 ─────────> 3.5 Proposals
2.3 ─────────> 5.5 Media

2.4 ─────────> 1.3 JavaScript
2.4 ═════════> 2.1 Responsive

2.5 ─────────> 3.3 Forms
2.5 ─────────> 4.1 Performance (loading states)
```

**Типовий flow:**
2.1 → 2.3 → 2.2 → 2.4 → 2.5

---

# КАТЕГОРІЯ 3: CONVERSION (Business Layer)

```
                    3.1 Landing Structures 🔴
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
        3.2 CTA 🔴    3.3 Forms 🟡   3.4 Pricing 🟡
              │             │             │
              └─────────────┴─────────────┘
                            │
                            ▼
                  3.5 Commercial Proposals


CRITICAL LINKS:

3.1 ═════════> 2.1 Responsive (structure)
3.1 ═════════> 2.3 Layout (components)
3.1 ─────────> 4.1 Performance (above fold)

3.2 ═════════> 3.1 Landing (CTA placement)
3.2 ═════════> 2.4 Touch (button sizing)
3.2 ─────────> 5.1 Analytics (tracking)

3.3 ═════════> 2.5 UX Patterns (validation)
3.3 ═════════> 1.3 JavaScript (validation)
3.3 ─────────> 5.1 Analytics (conversion)

3.4 ─────────> 3.1 Landing (pricing section)
3.4 ─────────> 2.3 Layout (tables)

3.5 ═════════> 3.4 Pricing (proposals)
3.5 ═════════> 2.3 Layout (structure)
3.5 ─────────> 5.5 Media (video/images)
```

**Conversion Flow:**
3.1 → 3.2 → 3.3 → 5.1 (complete funnel)

---

# КАТЕГОРІЯ 4: PERFORMANCE (Optimization Layer)

```
                    4.1 Core Web Vitals 🔴
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
      4.2 Assets 🟡  4.3 Code 🟡   4.4 Caching 🟢
                            │
                            └─────────────┐
                                         │
                                         ▼
                            4.5 Mobile Performance 🟡


ОПТИМІЗАЦІЯ ПОТОКУ:

4.1 ═════════> 2.1 Responsive (CLS prevention)
4.1 ═════════> 3.1 Landing (LCP optimization)

4.2 ═════════> 2.1 Responsive (images)
4.2 ─────────> 5.5 Media (video optimization)

4.3 ═════════> 1.4 Preprocessors (CSS optimization)
4.3 ═════════> 1.5 Build Tools (bundling)

4.4 ─────────> 1.5 Build Tools (service workers)
4.4 ─────────> 7.3 Deployment (CDN)

4.5 ═════════> 4.1 Core Vitals (mobile metrics)
4.5 ─────────> 2.4 Touch (mobile interactions)
```

**Optimization Sequence:**
4.1 (audit) → 4.2 (assets) → 4.3 (code) → 4.4 (caching)

---

# КАТЕГОРІЯ 5: INTEGRATIONS (Functionality Layer)

```
5.1 Analytics ═══> 3.2 CTA (conversion tracking)
       │
       └═════════> 3.3 Forms (form tracking)
       │
       └─────────> 7.5 Monitoring (data integration)


5.2 Marketing ═══> 3.3 Forms (lead capture)
       │
       └─────────> 5.1 Analytics (pixel tracking)
       │
       └─────────> 3.1 Landing (chat widgets)


5.3 Payment ═════> 3.3 Forms (checkout forms)
       │
       └─────────> 3.4 Pricing (gateway integration)
       │
       └─────────> 7.2 QA (security checks)


5.4 APIs ────────> 2.3 Layout (maps, widgets)
       │
       └─────────> 1.3 JavaScript (API calls)


5.5 Media ═══════> 2.3 Layout (galleries)
       │
       └═════════> 4.2 Assets (optimization)
       │
       └─────────> 3.5 Proposals (video embeds)
```

**Integration Priority:**
5.1 (analytics) → 5.2 (marketing) → 5.5 (media)

---

# КАТЕГОРІЯ 6: AI WORKFLOW (Meta Layer)

```
                    6.1 Claude Prompting 🔴
                      (CONTROLS ALL)
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
      6.2 Chain of    6.3 Code       6.4 Components
         Thought         Review         Library
              │             │             │
              └─────────────┴─────────────┘
                            │
                            ▼
                    6.5 Advanced Techniques


AI -> PROJECT CONNECTIONS:

6.1 ═════════> ВСІ ФАЙЛИ (prompting strategy)

6.2 ═════════> 2.3 Layout (component breakdown)
6.2 ═════════> 3.1 Landing (structure planning)

6.3 ═════════> 4.1 Performance (audit)
6.3 ═════════> 7.1 Testing (automated checks)

6.4 ═════════> 2.3 Layout (reusable components)
6.4 ─────────> 1.2 CSS Frameworks (design system)

6.5 ═════════> 1.4 Preprocessors (refactoring)
6.5 ─────────> 4.3 Code Optimization (advanced)
```

**AI Workflow:**
6.1 (foundation) → 6.2 (development) → 6.3 (review) → 6.4 (library)

---

# КАТЕГОРІЯ 7: TESTING & DEPLOYMENT (Release Layer)

```
7.1 Testing ═════> 4.1 Performance (metrics)
       │
       └═════════> 1.1 HTML (validation)
       │
       └─────────> 6.3 AI Review (automation)


7.2 QA ══════════> 7.1 Testing (validation)
       │
       └─────────> 4.2 Assets (optimization check)


7.3 Deployment ══> 4.4 Caching (CDN setup)
       │
       └═════════> 7.4 CI/CD (platform integration)


7.4 CI/CD ═══════> 7.1 Testing (pipelines)
       │
       └═════════> 7.3 Deployment (automation)
       │
       └─────────> 4.3 Code Optimization (build)


7.5 Monitoring ══> 5.1 Analytics (integration)
       │
       └═════════> 4.1 Performance (tracking)
       │
       └─────────> 7.3 Deployment (uptime)
```

**Release Flow:**
7.1 (test) → 7.2 (validate) → 7.3 (deploy) → 7.4 (automate) → 7.5 (monitor)

---

# РЕКОМЕНДОВАНІ КОМБІНАЦІЇ (Presets)

## 🎯 PRESET 1: Quick Landing Page
```
MUST LOAD:
6.1 ═══> 2.1 ═══> 3.1 ═══> 3.2 ═══> 4.1
```
**5 файлів | ~10-12k tokens**
**Use case:** Швидкий лендінг, 1-2 години

## 📊 PRESET 2: High-Converting Sales Page
```
MUST LOAD:
6.1 ═══> 2.1 ═══> 3.1 ═══> 3.2 ═══> 3.3
         │
         └───> 3.4 ═══> 5.1 ═══> 4.1
```
**8 файлів | ~16-20k tokens**
**Use case:** Product launch, pricing page

## 💼 PRESET 3: B2B Commercial Proposal
```
MUST LOAD:
6.1 ═══> 2.1 ═══> 3.5 ═══> 3.4 ═══> 2.3
                   │
                   └───> 5.5 ═══> 4.1
```
**7 файлів | ~14-16k tokens**
**Use case:** Комерційна пропозиція, презентація

## 🚀 PRESET 4: Performance Optimization
```
MUST LOAD:
4.1 ═══> 4.2 ═══> 4.3 ═══> 4.4 ═══> 4.5
 │
 └───> 6.1 (для AI audit)
```
**6 файлів | ~12-14k tokens**
**Use case:** Оптимізація існуючої сторінки

## 📝 PRESET 5: Lead Gen Form Page
```
MUST LOAD:
6.1 ═══> 2.1 ═══> 3.3 ═══> 3.2 ═══> 2.5
                   │
                   └───> 5.1 ═══> 5.2
```
**7 файлів | ~14-16k tokens**
**Use case:** Форма збору контактів, registration

## 🎨 PRESET 6: Full-Feature Landing
```
MUST LOAD:
6.1 → 2.1 → 3.1 → 3.2 → 3.3 → 2.3 → 4.1 → 5.1 → 2.2 → 5.5
```
**10 файлів | ~20-24k tokens**
**Use case:** Повнофункціональний лендінг з усім

---

# DEPENDENCY CHAINS (Ланцюги залежностей)

## Chain 1: HTML Foundation
```
1.1 → 2.1 → 2.3 → 3.1 → 4.1
```
**Мета:** Семантична, responsive, оптимізована структура

## Chain 2: CSS Architecture
```
1.2 → 1.4 → 2.1 → 4.3 → 7.2
```
**Мета:** Масштабована, оптимізована стилізація

## Chain 3: JavaScript Functionality
```
1.3 → 2.2 → 2.4 → 2.5 → 4.1
```
**Мета:** Інтерактивність без performance жертв

## Chain 4: Conversion Funnel
```
3.1 → 3.2 → 3.3 → 5.1 → 5.2
```
**Мета:** Повний conversion tracking flow

## Chain 5: Performance Pipeline
```
4.1 → 4.2 → 4.3 → 4.4 → 7.1
```
**Мета:** Комплексна оптимізація

## Chain 6: AI Development
```
6.1 → 6.2 → 6.3 → 6.4 → 6.5
```
**Мета:** Майстерність AI-assisted development

## Chain 7: Launch Pipeline
```
7.1 → 7.2 → 7.3 → 7.4 → 7.5
```
**Мета:** Від testing до production monitoring

---

# CONFLICT MATRIX (Несумісності та обережності)

## ⚠️ Потенційні конфлікти:

### 1.2 (CSS Frameworks) ⚡ 1.4 (Preprocessors)
**Проблема:** Tailwind vs Sass можуть конфліктувати
**Рішення:** Обери один підхід, або використовуй Tailwind з PostCSS

### 4.4 (Caching) ⚡ 7.3 (Deployment)
**Проблема:** Некоректне cache busting
**Рішення:** Завжди використовуй обидва разом

### 5.1 (Analytics) ⚡ Privacy regulations
**Проблема:** GDPR compliance
**Рішення:** Читай privacy-compliant секцію в 5.1

### 3.3 (Forms) ⚡ 4.1 (Performance)
**Проблема:** Heavy validation бібліотеки
**Рішення:** Lightweight validation з 1.3 + 2.5

---

# WORKFLOW MAPS (Карти робочих процесів)

## 🗺️ MAP 1: New Project from Scratch

```
START
  │
  ├──> 6.1 (Setup AI prompts)
  │
  ├──> 1.1 + 2.1 (Structure + Responsive)
  │
  ├──> 1.2 (Choose CSS approach)
  │
  ├──> 3.1 + 3.2 (Content + CTAs)
  │
  ├──> 2.3 (Layout components)
  │
  ├──> 3.3 (Forms if needed)
  │
  ├──> 5.x (Integrations)
  │
  ├──> 4.1 + 4.2 + 4.3 (Optimize)
  │
  ├──> 7.1 + 7.2 (Test + Validate)
  │
  └──> 7.3 (Deploy)
       │
       └──> 7.5 (Monitor)
```

## 🗺️ MAP 2: Optimize Existing Page

```
START (existing page)
  │
  ├──> 4.1 (Audit Core Web Vitals)
  │     │
  │     ├──> Problems found?
  │     │
  │     ├──> 4.2 (Asset issues?)
  │     ├──> 4.3 (Code bloat?)
  │     └──> 4.5 (Mobile slow?)
  │
  ├──> 3.2 (Conversion rate low?)
  │     │
  │     ├──> 3.1 (Structure issues?)
  │     └──> 3.3 (Form problems?)
  │
  ├──> 6.3 (AI Code Review)
  │
  ├──> Apply fixes
  │
  └──> 7.1 (Test improvements)
```

## 🗺️ MAP 3: AI-Assisted Development

```
START (requirements)
  │
  ├──> 6.1 (Craft initial prompt)
  │     │
  │     └──> Load relevant domain files:
  │           - Project type (3.x)
  │           - Design needs (2.x)
  │           - Technical (1.x, 4.x)
  │
  ├──> 6.2 (Use CoT for complex parts)
  │
  ├──> Generate code
  │
  ├──> 6.3 (AI Review)
  │
  ├──> Iterate with 6.1 + 6.2
  │
  ├──> 6.4 (Save components to library)
  │
  └──> 6.5 (Advanced techniques if needed)
```

---

# ЗАГАЛЬНІ PATTERNS ВИКОРИСТАННЯ

## Pattern A: Foundation First
```
Завжди починай з: 1.1, 2.1, 6.1
Потім додавай specialized файли
```

## Pattern B: Type-Driven
```
1. Визнач тип проекту (landing/proposal/form)
2. Завантаж всі релевантні 3.x файли
3. Додай 2.x для design
4. Finish з 4.x для performance
```

## Pattern C: Problem-Solving
```
1. Ідентифікуй проблему
2. Знайди primary файл (Quick Reference)
3. Завантаж dependency chain
4. Застосуй з AI (6.1, 6.2)
```

## Pattern D: Iterative Development
```
6.1 → Generate → 6.3 Review → 6.1 Refine → Repeat
```

---

# ОЦІНКА СКЛАДНОСТІ КОМБІНАЦІЙ

| Файлів | Tokens | Складність | Use Case |
|--------|--------|------------|----------|
| 3-5 | 6-10k | ⭐ Easy | Quick landing, simple page |
| 6-8 | 12-16k | ⭐⭐ Medium | Full landing, form page |
| 9-12 | 18-24k | ⭐⭐⭐ Complex | Full-feature project |
| 13-15 | 26-30k | ⭐⭐⭐⭐ Advanced | Multi-page equivalen, complex |
| 16+ | 32k+ | ⭐⭐⭐⭐⭐ Expert | Comprehensive, all features |

**Рекомендація:** Тримай 6-10 файлів для оптимального context management

---

**VERSION:** 1.0 Connection Map
**PURPOSE:** Розуміння взаємозв'язків між файлами
**BENEFIT:** Швидший вибір правильних комбінацій

---

*Використовуй цю карту для планування завантаження файлів перед проектом*
