# Classplay Design System — Spec Completa

## Visão Geral

Design system completo para o Classplay, uma plataforma de LMS gamificada inspirada no Duolingo, voltada para adultos (35-45 anos) da Comunidade Sem Codar, focada em IA e vibe coding. O sistema prioriza sensação de evolução, interatividade satisfatória e riqueza visual sem parecer infantil.

**Entregável:** Página HTML única autocontida documentando todo o design system com previews visuais, CSS custom properties, e botão para download do markdown completo.

**Agnóstico de framework** — documentado em CSS custom properties puras, compatível com qualquer stack.

---

## 1. Cores

Prefixo de todas as variáveis: `--cp-` (Classplay).

### 1.1 Cor Primária — Roxo

| Token | Hex | Uso |
|---|---|---|
| `--cp-primary-50` | `#FAF5FF` | Background sutil (light) |
| `--cp-primary-100` | `#F3E8FF` | Hover backgrounds (light) |
| `--cp-primary-200` | `#E9D5FF` | Borders (light) |
| `--cp-primary-300` | `#D8B4FE` | Ícones inativos |
| `--cp-primary-400` | `#C084FC` | Texto secundário (dark) |
| `--cp-primary-500` | `#A855F7` | Hover estado de botões |
| `--cp-primary-600` | `#7C3AED` | **Cor principal — botões, links, identidade** |
| `--cp-primary-700` | `#6D28D9` | Sombra 3D dos botões |
| `--cp-primary-800` | `#5B21B6` | Texto sobre backgrounds claros |
| `--cp-primary-900` | `#4C1D95` | Backgrounds densos |

### 1.2 Cores Funcionais de Gamificação

Cada cor funcional tem escala completa (50-900). Tokens nomeados como `--cp-{cor}-{escala}`, ex: `--cp-xp-300`, `--cp-success-700`.

| Token base | Hex (500) | Papel |
|---|---|---|
| `--cp-xp` | `#F59E0B` | XP, recompensas, moedas |
| `--cp-streak` | `#F97316` | Streaks, energia, urgência |
| `--cp-success` | `#10B981` | Conclusão, correto, progresso |
| `--cp-info` | `#3B82F6` | Informação, dicas, links |
| `--cp-danger` | `#EF4444` | Erros, alertas, vidas |
| `--cp-bonus` | `#EC4899` | Bônus, eventos especiais |
| `--cp-level` | `#06B6D4` | Níveis, rankings, divisões |

**Escala completa de cada cor funcional:**

| Escala | XP | Streak | Success | Info | Danger | Bonus | Level |
|---|---|---|---|---|---|---|---|
| 50 | `#FFFBEB` | `#FFF7ED` | `#ECFDF5` | `#EFF6FF` | `#FEF2F2` | `#FDF2F8` | `#ECFEFF` |
| 100 | `#FEF3C7` | `#FFEDD5` | `#D1FAE5` | `#DBEAFE` | `#FEE2E2` | `#FCE7F3` | `#CFFAFE` |
| 200 | `#FDE68A` | `#FED7AA` | `#A7F3D0` | `#BFDBFE` | `#FECACA` | `#FBCFE8` | `#A5F3FC` |
| 300 | `#FCD34D` | `#FDBA74` | `#6EE7B7` | `#93C5FD` | `#FCA5A5` | `#F9A8D4` | `#67E8F9` |
| 400 | `#FBBF24` | `#FB923C` | `#34D399` | `#60A5FA` | `#F87171` | `#F472B6` | `#22D3EE` |
| 500 | `#F59E0B` | `#F97316` | `#10B981` | `#3B82F6` | `#EF4444` | `#EC4899` | `#06B6D4` |
| 600 | `#D97706` | `#EA580C` | `#059669` | `#2563EB` | `#DC2626` | `#DB2777` | `#0891B2` |
| 700 | `#B45309` | `#C2410C` | `#047857` | `#1D4ED8` | `#B91C1C` | `#BE185D` | `#0E7490` |
| 800 | `#92400E` | `#9A3412` | `#065F46` | `#1E40AF` | `#991B1B` | `#9D174D` | `#155E75` |
| 900 | `#78350F` | `#7C2D12` | `#064E3B` | `#1E3A8A` | `#7F1D1D` | `#831843` | `#164E63` |

### 1.3 Superfícies (Tema Dark / Light)

Aplicadas via `data-theme="dark"` ou `data-theme="light"` no `<html>`.

```css
[data-theme="dark"] {
  --cp-bg-primary: #0F0A1A;
  --cp-bg-secondary: #1A1128;
  --cp-bg-tertiary: #2D1F42;
  --cp-bg-elevated: #251A38;
  --cp-text-primary: #F5F0FF;
  --cp-text-secondary: #B8A0D4;
  --cp-text-muted: #7A6895;
  --cp-border: #2D1F42;
  --cp-border-subtle: #1F1630;
  --cp-shadow-color: rgba(0, 0, 0, 0.4);
  --cp-overlay: rgba(15, 10, 26, 0.8);
}

[data-theme="light"] {
  --cp-bg-primary: #FFFFFF;
  --cp-bg-secondary: #FAF5FF;
  --cp-bg-tertiary: #F3E8FF;
  --cp-bg-elevated: #FFFFFF;
  --cp-text-primary: #1A1128;
  --cp-text-secondary: #6B5A82;
  --cp-text-muted: #9B8AB3;
  --cp-border: #E9D5FF;
  --cp-border-subtle: #F3E8FF;
  --cp-shadow-color: rgba(124, 58, 237, 0.08);
  --cp-overlay: rgba(255, 255, 255, 0.8);
}
```

### 1.4 Declaração Completa de Tokens de Cor

Todas as cores devem ser declaradas em `:root` para ficarem disponíveis independente do tema:

```css
:root {
  /* Primary scale */
  --cp-primary-50: #FAF5FF;
  --cp-primary-100: #F3E8FF;
  --cp-primary-200: #E9D5FF;
  --cp-primary-300: #D8B4FE;
  --cp-primary-400: #C084FC;
  --cp-primary-500: #A855F7;
  --cp-primary-600: #7C3AED;
  --cp-primary-700: #6D28D9;
  --cp-primary-800: #5B21B6;
  --cp-primary-900: #4C1D95;

  /* XP (amber) */
  --cp-xp: #F59E0B;
  --cp-xp-50: #FFFBEB; --cp-xp-100: #FEF3C7; --cp-xp-200: #FDE68A;
  --cp-xp-300: #FCD34D; --cp-xp-400: #FBBF24; --cp-xp-500: #F59E0B;
  --cp-xp-600: #D97706; --cp-xp-700: #B45309; --cp-xp-800: #92400E;
  --cp-xp-900: #78350F;

  /* Streak (orange) */
  --cp-streak: #F97316;
  --cp-streak-50: #FFF7ED; --cp-streak-100: #FFEDD5; --cp-streak-200: #FED7AA;
  --cp-streak-300: #FDBA74; --cp-streak-400: #FB923C; --cp-streak-500: #F97316;
  --cp-streak-600: #EA580C; --cp-streak-700: #C2410C; --cp-streak-800: #9A3412;
  --cp-streak-900: #7C2D12;

  /* Success (emerald) */
  --cp-success: #10B981;
  --cp-success-50: #ECFDF5; --cp-success-100: #D1FAE5; --cp-success-200: #A7F3D0;
  --cp-success-300: #6EE7B7; --cp-success-400: #34D399; --cp-success-500: #10B981;
  --cp-success-600: #059669; --cp-success-700: #047857; --cp-success-800: #065F46;
  --cp-success-900: #064E3B;

  /* Info (blue) */
  --cp-info: #3B82F6;
  --cp-info-50: #EFF6FF; --cp-info-100: #DBEAFE; --cp-info-200: #BFDBFE;
  --cp-info-300: #93C5FD; --cp-info-400: #60A5FA; --cp-info-500: #3B82F6;
  --cp-info-600: #2563EB; --cp-info-700: #1D4ED8; --cp-info-800: #1E40AF;
  --cp-info-900: #1E3A8A;

  /* Danger (red) */
  --cp-danger: #EF4444;
  --cp-danger-50: #FEF2F2; --cp-danger-100: #FEE2E2; --cp-danger-200: #FECACA;
  --cp-danger-300: #FCA5A5; --cp-danger-400: #F87171; --cp-danger-500: #EF4444;
  --cp-danger-600: #DC2626; --cp-danger-700: #B91C1C; --cp-danger-800: #991B1B;
  --cp-danger-900: #7F1D1D;

  /* Bonus (pink) */
  --cp-bonus: #EC4899;
  --cp-bonus-50: #FDF2F8; --cp-bonus-100: #FCE7F3; --cp-bonus-200: #FBCFE8;
  --cp-bonus-300: #F9A8D4; --cp-bonus-400: #F472B6; --cp-bonus-500: #EC4899;
  --cp-bonus-600: #DB2777; --cp-bonus-700: #BE185D; --cp-bonus-800: #9D174D;
  --cp-bonus-900: #831843;

  /* Level (cyan) */
  --cp-level: #06B6D4;
  --cp-level-50: #ECFEFF; --cp-level-100: #CFFAFE; --cp-level-200: #A5F3FC;
  --cp-level-300: #67E8F9; --cp-level-400: #22D3EE; --cp-level-500: #06B6D4;
  --cp-level-600: #0891B2; --cp-level-700: #0E7490; --cp-level-800: #155E75;
  --cp-level-900: #164E63;
}
```

---

## 2. Tipografia

### 2.1 Font Families

```css
:root {
  --cp-font-family: 'Nunito', sans-serif;
  --cp-font-mono: 'JetBrains Mono', 'Fira Code', monospace;
}
```

Google Fonts import: `Nunito:wght@400;600;700;800;900` e `JetBrains+Mono:wght@400;700`

### 2.2 Escala Tipográfica

| Token | Tamanho | Line-height | Uso |
|---|---|---|---|
| `--cp-text-xs` | `12px` / `0.75rem` | 1.5 | Captions, labels pequenos |
| `--cp-text-sm` | `14px` / `0.875rem` | 1.5 | Texto auxiliar, badges, metadata |
| `--cp-text-base` | `16px` / `1rem` | 1.6 | Corpo de texto, parágrafos |
| `--cp-text-lg` | `18px` / `1.125rem` | 1.5 | Subtítulos, nomes de módulo |
| `--cp-text-xl` | `20px` / `1.25rem` | 1.4 | Títulos de card |
| `--cp-text-2xl` | `24px` / `1.5rem` | 1.3 | Títulos de página |
| `--cp-text-3xl` | `30px` / `1.875rem` | 1.2 | Headers principais |
| `--cp-text-4xl` | `36px` / `2.25rem` | 1.1 | Números de destaque |
| `--cp-text-display` | `48px` / `3rem` | 1.0 | Hero, números de conquista |

### 2.3 Pesos

Nunito não tem peso 500 (Medium). O peso 600 é SemiBold na fonte.

| Token | Valor | Nome na fonte | Uso |
|---|---|---|---|
| `--cp-font-regular` | `400` | Regular | Corpo de texto |
| `--cp-font-semibold` | `600` | SemiBold | Ênfase leve, labels |
| `--cp-font-bold` | `700` | Bold | Títulos, botões, badges |
| `--cp-font-extra` | `800` | ExtraBold | Números de XP, displays |
| `--cp-font-black` | `900` | Black | Conquistas, hero numbers |

---

## 3. Espaçamento

Escala baseada em múltiplos de 4px.

```css
:root {
  --cp-space-1: 4px;
  --cp-space-2: 8px;
  --cp-space-3: 12px;
  --cp-space-4: 16px;
  --cp-space-5: 20px;
  --cp-space-6: 24px;
  --cp-space-8: 32px;
  --cp-space-10: 40px;
  --cp-space-12: 48px;
  --cp-space-16: 64px;
  --cp-space-20: 80px;
}
```

---

## 4. Border Radius

Moderado (8-12px) como padrão, mais arredondado para badges e pills.

```css
:root {
  --cp-radius-sm: 6px;
  --cp-radius-md: 8px;
  --cp-radius-lg: 12px;
  --cp-radius-xl: 16px;
  --cp-radius-pill: 9999px;
  --cp-radius-circle: 50%;
}
```

| Uso | Token |
|---|---|
| Inputs, pequenos elementos | `--cp-radius-sm` |
| Cards, containers | `--cp-radius-md` a `--cp-radius-lg` |
| Modais, seções grandes | `--cp-radius-xl` |
| Badges, tags, botões pill | `--cp-radius-pill` |
| Avatares, ícones circulares | `--cp-radius-circle` |

---

## 5. Sombras

```css
:root {
  --cp-shadow-sm: 0 1px 2px var(--cp-shadow-color);
  --cp-shadow-md: 0 4px 6px var(--cp-shadow-color);
  --cp-shadow-lg: 0 10px 25px var(--cp-shadow-color);
  --cp-shadow-xl: 0 20px 40px var(--cp-shadow-color);
  --cp-shadow-3d: 0 4px 0px;  /* Combinado com cor específica */
  --cp-shadow-glow: 0 0 20px;  /* Combinado com cor para efeito glow */
}
```

---

## 6. Componentes

### 6.0 Focus Global (Acessibilidade)

Todos os elementos interativos (botões, links, inputs, cards clicáveis, toggles, sidebar items) devem ter estilos de foco visíveis para navegação por teclado.

```css
/* Focus ring padrão para todos os elementos interativos */
:focus-visible {
  outline: 2px solid var(--cp-primary-600);
  outline-offset: 2px;
}

/* Focus ring para elementos sobre fundos escuros */
[data-theme="dark"] :focus-visible {
  outline-color: var(--cp-primary-400);
}

/* Remove outline padrão (substitui pelo focus-visible acima) */
:focus:not(:focus-visible) {
  outline: none;
}
```

### 6.1 Botões

Todos os botões compartilham propriedades base via `.cp-btn`:

```css
.cp-btn {
  font-family: var(--cp-font-family);
  font-size: var(--cp-text-base);
  padding: var(--cp-space-3) var(--cp-space-6);
  border: none;
  border-radius: var(--cp-radius-md);
  cursor: pointer;
  user-select: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--cp-space-2);
  text-decoration: none;
  line-height: 1;
}
.cp-btn[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
  transform: none !important;
  box-shadow: none !important;
}
.cp-btn--sm {
  padding: var(--cp-space-2) var(--cp-space-4);
  font-size: var(--cp-text-sm);
}
.cp-btn--lg {
  padding: var(--cp-space-4) var(--cp-space-8);
  font-size: var(--cp-text-lg);
}
```

**Primário (3D — para CTAs):**
```css
.cp-btn-primary {
  background: var(--cp-primary-600);
  color: #FFFFFF;
  font-weight: var(--cp-font-bold);
  box-shadow: 0 4px 0 var(--cp-primary-700);
  transition: transform 0.1s ease, box-shadow 0.1s ease;
}
.cp-btn-primary:hover {
  background: var(--cp-primary-500);
  transform: translateY(-1px);
  box-shadow: 0 5px 0 var(--cp-primary-700);
}
.cp-btn-primary:active {
  transform: translateY(3px);
  box-shadow: 0 1px 0 var(--cp-primary-700);
}
```

**Secundário (flat):**
```css
.cp-btn-secondary {
  background: transparent;
  color: var(--cp-primary-600);
  font-weight: var(--cp-font-bold);
  border: 2px solid var(--cp-primary-600);
  transition: background 0.2s ease, color 0.2s ease;
}
.cp-btn-secondary:hover {
  background: var(--cp-primary-100);
  color: var(--cp-primary-700);
}
[data-theme="dark"] .cp-btn-secondary:hover {
  background: rgba(124, 58, 237, 0.15);
  color: var(--cp-primary-400);
}
```

**Ghost (terciário):**
```css
.cp-btn-ghost {
  background: transparent;
  color: var(--cp-text-secondary);
  font-weight: var(--cp-font-semibold);
  font-size: var(--cp-text-sm);
  padding: var(--cp-space-2) var(--cp-space-4);
  transition: background 0.2s ease, color 0.2s ease;
}
.cp-btn-ghost:hover {
  background: var(--cp-bg-tertiary);
  color: var(--cp-text-primary);
}
```

**Botão de Sucesso (3D — para ações de conclusão):**
```css
.cp-btn-success {
  background: var(--cp-success);
  color: #FFFFFF;
  font-weight: var(--cp-font-bold);
  box-shadow: 0 4px 0 var(--cp-success-700);
  transition: transform 0.1s ease, box-shadow 0.1s ease;
}
.cp-btn-success:hover {
  background: var(--cp-success-400);
  transform: translateY(-1px);
  box-shadow: 0 5px 0 var(--cp-success-700);
}
.cp-btn-success:active {
  transform: translateY(3px);
  box-shadow: 0 1px 0 var(--cp-success-700);
}
```

**Botão de Perigo (3D):**
```css
.cp-btn-danger {
  background: var(--cp-danger);
  color: #FFFFFF;
  font-weight: var(--cp-font-bold);
  box-shadow: 0 4px 0 var(--cp-danger-700);
  transition: transform 0.1s ease, box-shadow 0.1s ease;
}
.cp-btn-danger:hover {
  background: var(--cp-danger-400);
  transform: translateY(-1px);
  box-shadow: 0 5px 0 var(--cp-danger-700);
}
.cp-btn-danger:active {
  transform: translateY(3px);
  box-shadow: 0 1px 0 var(--cp-danger-700);
}
```

### 6.2 Formulários

**Input de texto:**
```css
.cp-input {
  background: var(--cp-bg-tertiary);
  color: var(--cp-text-primary);
  font-family: var(--cp-font-family);
  font-size: var(--cp-text-base);
  padding: var(--cp-space-3) var(--cp-space-4);
  border: 2px solid var(--cp-border);
  border-radius: var(--cp-radius-md);
  outline: none;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
  width: 100%;
}
.cp-input:focus {
  border-color: var(--cp-primary-600);
  box-shadow: 0 0 0 3px rgba(124, 58, 237, 0.15);
}
.cp-input::placeholder {
  color: var(--cp-text-muted);
}
.cp-input--error {
  border-color: var(--cp-danger);
}
.cp-input--error:focus {
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.15);
}
```

**Label:**
```css
.cp-label {
  font-family: var(--cp-font-family);
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-bold);
  color: var(--cp-text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: var(--cp-space-2);
  display: block;
}
```

**Select:**
```css
.cp-select {
  background: var(--cp-bg-tertiary);
  color: var(--cp-text-primary);
  font-family: var(--cp-font-family);
  font-size: var(--cp-text-base);
  padding: var(--cp-space-3) var(--cp-space-4);
  padding-right: var(--cp-space-10);
  border: 2px solid var(--cp-border);
  border-radius: var(--cp-radius-md);
  appearance: none;
  outline: none;
  transition: border-color 0.2s ease;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%237A6895' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: right 12px center;
  background-size: 16px;
}
.cp-select:focus {
  border-color: var(--cp-primary-600);
  box-shadow: 0 0 0 3px rgba(124, 58, 237, 0.15);
}
```

**Textarea:**

Aplicar classes `.cp-input .cp-textarea` juntas no elemento `<textarea>`. A classe `.cp-input` fornece os estilos base, `.cp-textarea` adiciona os específicos:

```css
.cp-textarea {
  min-height: 120px;
  resize: vertical;
}
```

**Toggle:**

O toggle deve ser implementado sobre um `<input type="checkbox">` com `role="switch"` e `aria-checked` para acessibilidade. A estrutura HTML recomendada:

```html
<label class="cp-toggle">
  <input type="checkbox" role="switch" aria-checked="false">
  <span class="cp-toggle__track"></span>
</label>
```

```css
.cp-toggle {
  display: inline-flex;
  cursor: pointer;
}
.cp-toggle input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}
.cp-toggle__track {
  width: 48px;
  height: 26px;
  background: var(--cp-bg-tertiary);
  border: 2px solid var(--cp-border);
  border-radius: var(--cp-radius-pill);
  position: relative;
  transition: background 0.2s ease, border-color 0.2s ease;
}
.cp-toggle__track::after {
  content: '';
  width: 18px;
  height: 18px;
  background: var(--cp-text-muted);
  border-radius: var(--cp-radius-circle);
  position: absolute;
  top: 2px;
  left: 2px;
  transition: transform 0.2s ease, background 0.2s ease;
}
.cp-toggle input:checked + .cp-toggle__track {
  background: var(--cp-primary-600);
  border-color: var(--cp-primary-600);
}
.cp-toggle input:checked + .cp-toggle__track::after {
  background: #FFFFFF;
  transform: translateX(22px);
}
.cp-toggle input:focus-visible + .cp-toggle__track {
  outline: 2px solid var(--cp-primary-600);
  outline-offset: 2px;
}
```

### 6.3 Cards

**Card padrão:**
```css
.cp-card {
  background: var(--cp-bg-secondary);
  border: 1px solid var(--cp-border-subtle);
  border-radius: var(--cp-radius-lg);
  padding: var(--cp-space-6);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.cp-card:hover {
  transform: translateY(-2px);
  box-shadow: var(--cp-shadow-lg);
}
```

**Card de curso/módulo:**
```css
.cp-card-course {
  background: var(--cp-bg-secondary);
  border: 1px solid var(--cp-border-subtle);
  border-radius: var(--cp-radius-lg);
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.cp-card-course__image {
  width: 100%;
  height: 180px;
  object-fit: cover;
}
.cp-card-course__body {
  padding: var(--cp-space-5);
}
.cp-card-course__title {
  font-size: var(--cp-text-xl);
  font-weight: var(--cp-font-bold);
  color: var(--cp-text-primary);
  margin-bottom: var(--cp-space-2);
}
.cp-card-course__meta {
  font-size: var(--cp-text-sm);
  color: var(--cp-text-secondary);
}
.cp-card-course__progress {
  margin-top: var(--cp-space-4);
}
```

**Card de aula (dentro de um módulo):**
```css
.cp-card-lesson {
  background: var(--cp-bg-secondary);
  border: 1px solid var(--cp-border-subtle);
  border-radius: var(--cp-radius-md);
  padding: var(--cp-space-4);
  display: flex;
  align-items: center;
  gap: var(--cp-space-4);
  cursor: pointer;
  transition: background 0.2s ease, transform 0.1s ease;
}
.cp-card-lesson:hover {
  background: var(--cp-bg-tertiary);
  transform: translateX(4px);
}
.cp-card-lesson--completed {
  border-left: 3px solid var(--cp-success);
}
.cp-card-lesson--locked {
  opacity: 0.5;
  cursor: not-allowed;
}
```

**Card elevado (para conteúdo destacado):**
```css
.cp-card-elevated {
  background: var(--cp-bg-elevated);
  border-radius: var(--cp-radius-xl);
  padding: var(--cp-space-8);
  box-shadow: var(--cp-shadow-xl);
}
```

### 6.4 Badges e Tags

**Badge de XP:**
```css
.cp-badge-xp {
  display: inline-flex;
  align-items: center;
  gap: var(--cp-space-1);
  background: var(--cp-xp);
  color: var(--cp-xp-900);
  font-family: var(--cp-font-family);
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-extra);
  padding: var(--cp-space-1) var(--cp-space-3);
  border-radius: var(--cp-radius-pill);
}
```

**Badge de streak:**
```css
.cp-badge-streak {
  display: inline-flex;
  align-items: center;
  gap: var(--cp-space-1);
  background: var(--cp-streak);
  color: #FFFFFF;
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-extra);
  padding: var(--cp-space-1) var(--cp-space-3);
  border-radius: var(--cp-radius-pill);
}
```

**Badge de nível:**
```css
.cp-badge-level {
  display: inline-flex;
  align-items: center;
  gap: var(--cp-space-1);
  background: var(--cp-level);
  color: #FFFFFF;
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-extra);
  padding: var(--cp-space-1) var(--cp-space-3);
  border-radius: var(--cp-radius-pill);
}
```

**Tag genérica:**
```css
.cp-tag {
  display: inline-flex;
  align-items: center;
  font-size: var(--cp-text-xs);
  font-weight: var(--cp-font-bold);
  padding: var(--cp-space-1) var(--cp-space-2);
  border-radius: var(--cp-radius-pill);
  background: var(--cp-bg-tertiary);
  color: var(--cp-text-secondary);
}
```

### 6.5 Barra de Progresso

```css
.cp-progress {
  width: 100%;
  height: 8px;
  background: var(--cp-bg-tertiary);
  border-radius: var(--cp-radius-pill);
  overflow: hidden;
}
.cp-progress__fill {
  height: 100%;
  border-radius: var(--cp-radius-pill);
  background: linear-gradient(90deg, var(--cp-primary-600), var(--cp-streak));
  transition: width 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}
/* Variantes */
.cp-progress--success .cp-progress__fill {
  background: linear-gradient(90deg, var(--cp-success), var(--cp-success-300));
}
.cp-progress--xp .cp-progress__fill {
  background: linear-gradient(90deg, var(--cp-xp), var(--cp-streak));
}
.cp-progress--lg {
  height: 12px;
}
```

### 6.6 Avatar

```css
.cp-avatar {
  width: 40px;
  height: 40px;
  border-radius: var(--cp-radius-circle);
  object-fit: cover;
  border: 2px solid var(--cp-border);
}
.cp-avatar--sm { width: 32px; height: 32px; }
.cp-avatar--lg { width: 56px; height: 56px; }
.cp-avatar--xl { width: 80px; height: 80px; border-width: 3px; }
.cp-avatar--bordered {
  border-color: var(--cp-primary-600);
  box-shadow: 0 0 0 2px var(--cp-bg-primary), 0 0 0 4px var(--cp-primary-600);
}
```

### 6.7 Sidebar

A sidebar usa `position: fixed` e o conteúdo principal usa `margin-left` para compensar. Não é um layout flex — é fixed + offset.

```css
.cp-sidebar {
  width: 240px;
  background: var(--cp-bg-secondary);
  border-right: 1px solid var(--cp-border-subtle);
  padding: var(--cp-space-4) 0;
  display: flex;
  flex-direction: column;
  gap: var(--cp-space-1);
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: var(--cp-z-sticky);
  overflow-y: auto;
}
.cp-sidebar__item {
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
  padding: var(--cp-space-3) var(--cp-space-5);
  color: var(--cp-text-secondary);
  font-weight: var(--cp-font-semibold);
  font-size: var(--cp-text-base);
  border-radius: 0 var(--cp-radius-md) var(--cp-radius-md) 0;
  cursor: pointer;
  transition: background 0.2s ease, color 0.2s ease;
  text-decoration: none;
}
.cp-sidebar__item:hover {
  background: var(--cp-bg-tertiary);
  color: var(--cp-text-primary);
}
.cp-sidebar__item--active {
  background: var(--cp-primary-50);
  color: var(--cp-primary-600);
  font-weight: var(--cp-font-bold);
  border-left: 3px solid var(--cp-primary-600);
}
[data-theme="dark"] .cp-sidebar__item--active {
  background: rgba(124, 58, 237, 0.15);
}
```

### 6.8 Modal

```css
.cp-modal-overlay {
  position: fixed;
  inset: 0;
  background: var(--cp-overlay);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: var(--cp-z-modal);
  backdrop-filter: blur(4px);
}
.cp-modal {
  background: var(--cp-bg-elevated);
  border-radius: var(--cp-radius-xl);
  padding: var(--cp-space-8);
  max-width: 480px;
  width: 90%;
  box-shadow: var(--cp-shadow-xl);
  animation: cp-modal-in 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}
@keyframes cp-modal-in {
  from { opacity: 0; transform: scale(0.9) translateY(10px); }
  to { opacity: 1; transform: scale(1) translateY(0); }
}
```

### 6.9 Tooltip

```css
.cp-tooltip {
  position: relative;
}
.cp-tooltip__content {
  position: absolute;
  bottom: calc(100% + 8px);
  left: 50%;
  transform: translateX(-50%);
  background: var(--cp-bg-elevated);
  color: var(--cp-text-primary);
  font-size: var(--cp-text-sm);
  padding: var(--cp-space-2) var(--cp-space-3);
  border-radius: var(--cp-radius-sm);
  box-shadow: var(--cp-shadow-md);
  white-space: nowrap;
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.2s ease;
}
.cp-tooltip:hover .cp-tooltip__content {
  opacity: 1;
}
```

### 6.10 Toast / Notificação

```css
.cp-toast-container {
  position: fixed;
  top: var(--cp-space-6);
  right: var(--cp-space-6);
  z-index: var(--cp-z-toast);
  display: flex;
  flex-direction: column;
  gap: var(--cp-space-3);
  pointer-events: none;
}
.cp-toast {
  background: var(--cp-bg-elevated);
  border-radius: var(--cp-radius-md);
  padding: var(--cp-space-4) var(--cp-space-5);
  box-shadow: var(--cp-shadow-lg);
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
  min-width: 300px;
  max-width: 480px;
  pointer-events: auto;
  animation: cp-slide-up 0.3s ease-out;
  border-left: 4px solid var(--cp-info);
}
.cp-toast--success { border-left-color: var(--cp-success); }
.cp-toast--danger { border-left-color: var(--cp-danger); }
.cp-toast--xp { border-left-color: var(--cp-xp); }
.cp-toast__message {
  flex: 1;
  font-size: var(--cp-text-sm);
  color: var(--cp-text-primary);
}
.cp-toast__close {
  background: none;
  border: none;
  color: var(--cp-text-muted);
  cursor: pointer;
  padding: var(--cp-space-1);
}
```

### 6.11 Spinner / Loading

```css
.cp-spinner {
  width: 24px;
  height: 24px;
  border: 3px solid var(--cp-border);
  border-top-color: var(--cp-primary-600);
  border-radius: var(--cp-radius-circle);
  animation: cp-spin 0.8s linear infinite;
}
.cp-spinner--sm { width: 16px; height: 16px; border-width: 2px; }
.cp-spinner--lg { width: 40px; height: 40px; border-width: 4px; }
```

**Skeleton (placeholder de carregamento):**
```css
.cp-skeleton {
  background: var(--cp-bg-tertiary);
  border-radius: var(--cp-radius-md);
  animation: cp-skeleton-pulse 1.5s ease-in-out infinite;
}
.cp-skeleton--text {
  height: 16px;
  margin-bottom: var(--cp-space-2);
}
.cp-skeleton--title {
  height: 24px;
  width: 60%;
  margin-bottom: var(--cp-space-3);
}
.cp-skeleton--avatar {
  width: 40px;
  height: 40px;
  border-radius: var(--cp-radius-circle);
}
.cp-skeleton--card {
  height: 200px;
}
@keyframes cp-skeleton-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}
```

---

## 7. Elementos de Gamificação

### 7.1 Painel de XP

```css
.cp-xp-panel {
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
  background: var(--cp-bg-secondary);
  border-radius: var(--cp-radius-lg);
  padding: var(--cp-space-4);
}
.cp-xp-panel__number {
  font-size: var(--cp-text-4xl);
  font-weight: var(--cp-font-black);
  color: var(--cp-xp);
}
.cp-xp-panel__label {
  font-size: var(--cp-text-sm);
  color: var(--cp-text-muted);
  text-transform: uppercase;
  letter-spacing: 1px;
}
```

### 7.2 Streak Counter

```css
.cp-streak-counter {
  display: flex;
  align-items: center;
  gap: var(--cp-space-2);
  padding: var(--cp-space-3) var(--cp-space-4);
  background: linear-gradient(135deg, var(--cp-streak), var(--cp-streak-400));
  border-radius: var(--cp-radius-lg);
  color: #FFFFFF;
}
.cp-streak-counter__number {
  font-size: var(--cp-text-3xl);
  font-weight: var(--cp-font-black);
}
.cp-streak-counter__label {
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-bold);
  opacity: 0.9;
}
```

### 7.3 Badge de Conquista

```css
.cp-achievement {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--cp-space-2);
}
.cp-achievement__icon {
  width: 64px;
  height: 64px;
  border-radius: var(--cp-radius-circle);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
  box-shadow: var(--cp-shadow-md);
}
.cp-achievement__icon--bronze {
  background: linear-gradient(135deg, #CD7F32, #E8A862);
}
.cp-achievement__icon--silver {
  background: linear-gradient(135deg, #B0B0B0, #D4D4D4);
}
.cp-achievement__icon--gold {
  background: linear-gradient(135deg, var(--cp-xp), var(--cp-xp-300));
}
.cp-achievement__icon--diamond {
  background: linear-gradient(135deg, var(--cp-level), var(--cp-level-300));
}
.cp-achievement__icon--locked {
  background: var(--cp-bg-tertiary);
  opacity: 0.4;
  filter: grayscale(1);
}
.cp-achievement__title {
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-bold);
  color: var(--cp-text-primary);
}
.cp-achievement__description {
  font-size: var(--cp-text-xs);
  color: var(--cp-text-muted);
}
```

### 7.4 Leaderboard / Ranking

```css
.cp-leaderboard {
  background: var(--cp-bg-secondary);
  border-radius: var(--cp-radius-lg);
  overflow: hidden;
}
.cp-leaderboard__item {
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
  padding: var(--cp-space-3) var(--cp-space-4);
  border-bottom: 1px solid var(--cp-border-subtle);
  transition: background 0.2s ease;
}
.cp-leaderboard__item:hover {
  background: var(--cp-bg-tertiary);
}
.cp-leaderboard__rank {
  font-size: var(--cp-text-lg);
  font-weight: var(--cp-font-extra);
  color: var(--cp-text-muted);
  width: 32px;
  text-align: center;
}
.cp-leaderboard__rank--1 { color: var(--cp-xp); }
.cp-leaderboard__rank--2 { color: #B0B0B0; }
.cp-leaderboard__rank--3 { color: #CD7F32; }
.cp-leaderboard__xp {
  font-weight: var(--cp-font-bold);
  color: var(--cp-xp);
  margin-left: auto;
}
.cp-leaderboard__item--me {
  background: rgba(124, 58, 237, 0.1);
  border-left: 3px solid var(--cp-primary-600);
}
```

### 7.5 Missões Diárias

```css
.cp-mission {
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
  padding: var(--cp-space-3) var(--cp-space-4);
  background: var(--cp-bg-secondary);
  border-radius: var(--cp-radius-md);
}
.cp-mission__icon {
  width: 40px;
  height: 40px;
  border-radius: var(--cp-radius-circle);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
}
.cp-mission__icon--xp { background: var(--cp-xp-100); }
.cp-mission__icon--time { background: var(--cp-level-100); }
.cp-mission__icon--lesson { background: var(--cp-primary-100); }
[data-theme="dark"] .cp-mission__icon--xp { background: rgba(245, 158, 11, 0.15); }
[data-theme="dark"] .cp-mission__icon--time { background: rgba(6, 182, 212, 0.15); }
[data-theme="dark"] .cp-mission__icon--lesson { background: rgba(124, 58, 237, 0.15); }
.cp-mission__info {
  flex: 1;
}
.cp-mission__title {
  font-size: var(--cp-text-sm);
  font-weight: var(--cp-font-bold);
  color: var(--cp-text-primary);
}
.cp-mission__progress-bar {
  margin-top: var(--cp-space-1);
  height: 6px;
  background: var(--cp-bg-tertiary);
  border-radius: var(--cp-radius-pill);
  overflow: hidden;
}
.cp-mission__progress-fill {
  height: 100%;
  border-radius: var(--cp-radius-pill);
  background: var(--cp-success);
  transition: width 0.4s ease;
}
.cp-mission__reward {
  font-size: var(--cp-text-xs);
  font-weight: var(--cp-font-bold);
  color: var(--cp-xp);
}
.cp-mission--completed {
  opacity: 0.6;
}
.cp-mission--completed .cp-mission__progress-fill {
  background: var(--cp-success);
  width: 100%;
}
```

### 7.6 Nível / Level Up

```css
.cp-level-indicator {
  display: flex;
  align-items: center;
  gap: var(--cp-space-3);
}
.cp-level-indicator__badge {
  width: 48px;
  height: 48px;
  border-radius: var(--cp-radius-circle);
  background: linear-gradient(135deg, var(--cp-primary-600), var(--cp-level));
  display: flex;
  align-items: center;
  justify-content: center;
  color: #FFFFFF;
  font-size: var(--cp-text-xl);
  font-weight: var(--cp-font-black);
  box-shadow: 0 0 20px rgba(124, 58, 237, 0.3);
}
.cp-level-indicator__xp-to-next {
  font-size: var(--cp-text-sm);
  color: var(--cp-text-muted);
}
```

---

## 8. Animações e Micro-interações

### 8.1 Transições Base

```css
:root {
  --cp-transition-fast: 0.1s ease;
  --cp-transition-base: 0.2s ease;
  --cp-transition-slow: 0.3s ease;
  --cp-transition-bounce: 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  --cp-transition-spring: 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

### 8.2 Keyframes

```css
/* Bounce in — para badges, conquistas, modais */
@keyframes cp-bounce-in {
  0% { opacity: 0; transform: scale(0.3); }
  50% { transform: scale(1.1); }
  70% { transform: scale(0.95); }
  100% { opacity: 1; transform: scale(1); }
}

/* Slide up — para toasts, notificações */
@keyframes cp-slide-up {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Pulse — para elementos que pedem atenção */
@keyframes cp-pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

/* Shake — para erros */
@keyframes cp-shake {
  0%, 100% { transform: translateX(0); }
  20% { transform: translateX(-8px); }
  40% { transform: translateX(8px); }
  60% { transform: translateX(-4px); }
  80% { transform: translateX(4px); }
}

/* Glow pulse — para items especiais */
@keyframes cp-glow {
  0%, 100% { box-shadow: 0 0 5px rgba(124, 58, 237, 0.3); }
  50% { box-shadow: 0 0 20px rgba(124, 58, 237, 0.6); }
}

/* Count up number — aplicado via JS */
@keyframes cp-count-up {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Confetti burst — partículas via JS, mas o container */
@keyframes cp-confetti-fade {
  0% { opacity: 1; }
  100% { opacity: 0; transform: translateY(-20px); }
}

/* Spin — para loading */
@keyframes cp-spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* Float — para items flutuantes decorativos */
@keyframes cp-float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-6px); }
}

/* XP gain flyup */
@keyframes cp-xp-flyup {
  0% { opacity: 1; transform: translateY(0) scale(1); }
  50% { opacity: 1; transform: translateY(-30px) scale(1.2); }
  100% { opacity: 0; transform: translateY(-60px) scale(0.8); }
}

/* Progress bar fill with overshoot */
@keyframes cp-progress-fill {
  0% { width: 0%; }
  80% { width: calc(var(--target-width) + 2%); }
  100% { width: var(--target-width); }
}

/* Star burst — para conquistas especiais */
@keyframes cp-star-burst {
  0% { opacity: 0; transform: scale(0) rotate(0deg); }
  50% { opacity: 1; transform: scale(1.3) rotate(180deg); }
  100% { opacity: 1; transform: scale(1) rotate(360deg); }
}
```

### 8.3 Classes Utilitárias de Animação

```css
.cp-animate-bounce-in { animation: cp-bounce-in 0.5s cubic-bezier(0.34, 1.56, 0.64, 1); }
.cp-animate-slide-up { animation: cp-slide-up 0.3s ease-out; }
.cp-animate-pulse { animation: cp-pulse 2s ease-in-out infinite; }
.cp-animate-shake { animation: cp-shake 0.5s ease; }
.cp-animate-glow { animation: cp-glow 2s ease-in-out infinite; }
.cp-animate-spin { animation: cp-spin 1s linear infinite; }
.cp-animate-float { animation: cp-float 3s ease-in-out infinite; }
.cp-animate-xp-flyup { animation: cp-xp-flyup 1s ease-out forwards; }
.cp-animate-star-burst { animation: cp-star-burst 0.8s cubic-bezier(0.34, 1.56, 0.64, 1); }
```

### 8.4 Comportamento de Animação por Contexto

| Evento | Animação | Duração |
|---|---|---|
| Ganhar XP | Número fly-up + badge pulse | 1s |
| Completar aula | Barra progresso com overshoot + confetti | 1.5s |
| Completar módulo | Confetti burst + badge bounce-in + glow | 2s |
| Subir de nível | Star burst + shake na tela + modal bounce-in | 2.5s |
| Streak mantido | Badge streak pulse + número count-up | 1s |
| Erro/resposta errada | Input shake + flash vermelho | 0.5s |
| Conquista desbloqueada | Badge bounce-in + glow + confetti | 2s |
| Missão completa | Progress bar fill + badge pulse | 1s |
| Hover em card | Translate Y(-2px) + shadow increase | 0.2s |
| Click em botão 3D | Translate Y(3px) + shadow decrease | 0.1s |
| Novo item no ranking | Slide up + highlight flash | 0.8s |

### 8.5 Confetti (requer JS helper)

O design system define a interface CSS, a implementação JS fica no consumer:

```css
.cp-confetti-container {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: var(--cp-z-confetti);
  overflow: hidden;
}
.cp-confetti-particle {
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 2px;
  animation: cp-confetti-fade 1.5s ease-out forwards;
}
```

Cores das partículas do confetti: usar as 7 cores funcionais de gamificação.

### 8.6 Preferência de Movimento Reduzido

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 9. Layout e Grid

### 9.1 Container

```css
.cp-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--cp-space-4);
}
.cp-container--narrow {
  max-width: 800px;
}
.cp-container--wide {
  max-width: 1400px;
}
```

### 9.2 Layout Principal (sidebar fixa + conteúdo)

A sidebar é `position: fixed`. O conteúdo principal usa `margin-left` para compensar.

```css
.cp-layout {
  min-height: 100vh;
}
.cp-layout__main {
  margin-left: 240px;  /* largura da sidebar */
  padding: var(--cp-space-8);
}
.cp-layout__content {
  max-width: 1200px;
}
.cp-layout__aside {
  width: 320px;
  position: fixed;
  right: 0;
  top: 0;
  height: 100vh;
  overflow-y: auto;
  padding: var(--cp-space-6);
  border-left: 1px solid var(--cp-border-subtle);
}
/* Quando aside está presente, main compensa ambos os lados */
.cp-layout--with-aside .cp-layout__main {
  margin-right: 320px;
}
```

### 9.3 Breakpoints

Valores de referência (CSS custom properties não funcionam em `@media` queries — usar os valores diretamente nas media queries ou via preprocessador):

| Token (referência) | Valor | Uso |
|---|---|---|
| `sm` | `640px` | Mobile landscape |
| `md` | `768px` | Tablet |
| `lg` | `1024px` | Desktop pequeno |
| `xl` | `1280px` | Desktop |
| `2xl` | `1536px` | Desktop grande |

### 9.4 Comportamento Responsivo

```css
/* Tablet e menor: sidebar vira drawer */
@media (max-width: 1023px) {
  .cp-sidebar {
    transform: translateX(-100%);
    transition: transform 0.3s ease;
    z-index: var(--cp-z-overlay);
  }
  .cp-sidebar--open {
    transform: translateX(0);
  }
  .cp-layout__main {
    margin-left: 0;
  }
  .cp-layout__aside {
    display: none;  /* aside fica em modal ou abaixo do conteúdo no mobile */
  }
  .cp-layout--with-aside .cp-layout__main {
    margin-right: 0;
  }
}

/* Mobile: ajustes de espaçamento */
@media (max-width: 767px) {
  .cp-layout__main {
    padding: var(--cp-space-4);
  }
  .cp-card-course__image {
    height: 140px;
  }
  .cp-modal {
    width: 95%;
    padding: var(--cp-space-5);
  }
  .cp-modal .cp-xp-panel__number,
  .cp-modal .cp-level-indicator__badge {
    font-size: var(--cp-text-3xl);
  }
}

/* Hamburger button (visível apenas quando sidebar é drawer) */
.cp-sidebar-toggle {
  display: none;
}
@media (max-width: 1023px) {
  .cp-sidebar-toggle {
    display: flex;
    position: fixed;
    top: var(--cp-space-4);
    left: var(--cp-space-4);
    z-index: var(--cp-z-overlay);
    background: var(--cp-bg-elevated);
    border: 1px solid var(--cp-border);
    border-radius: var(--cp-radius-md);
    padding: var(--cp-space-2);
    cursor: pointer;
    box-shadow: var(--cp-shadow-md);
  }
}
```

---

## 10. Ícones

O design system não impõe uma library de ícones específica. Recomendação: **Lucide Icons** (open source, consistente, boa cobertura).

Convenções:
- Tamanho padrão: 20px
- Stroke width: 2px
- Cor: herda via `currentColor`
- Ícones de gamificação podem usar emoji como fallback (🔥 streak, ⚡ XP, 🏆 conquista, ⭐ favorito)

---

## 11. Imagens e Fundos

### 11.1 Gradientes de Background

```css
/* Header/hero gradient - dark */
.cp-gradient-hero-dark {
  background: linear-gradient(135deg, #0F0A1A 0%, #1A1128 50%, #2D1F42 100%);
}
/* Header/hero gradient - light */
.cp-gradient-hero-light {
  background: linear-gradient(135deg, #FAF5FF 0%, #F3E8FF 50%, #E9D5FF 100%);
}
/* Card premium/destaque */
.cp-gradient-premium {
  background: linear-gradient(135deg, var(--cp-primary-600), var(--cp-level));
}
/* Streak ativo */
.cp-gradient-streak {
  background: linear-gradient(135deg, var(--cp-streak), var(--cp-streak-400));
}
/* XP reward */
.cp-gradient-xp {
  background: linear-gradient(135deg, var(--cp-xp), var(--cp-xp-300));
}
/* Level up celebration */
.cp-gradient-levelup {
  background: linear-gradient(135deg, var(--cp-primary-600), var(--cp-bonus), var(--cp-xp));
}
```

### 11.2 Padrões Decorativos

Para backgrounds de seções, usar padrões sutis com opacidade baixa:

```css
/* Dot pattern */
.cp-pattern-dots {
  background-image: radial-gradient(var(--cp-border) 1px, transparent 1px);
  background-size: 20px 20px;
}
/* Grid pattern */
.cp-pattern-grid {
  background-image:
    linear-gradient(var(--cp-border-subtle) 1px, transparent 1px),
    linear-gradient(90deg, var(--cp-border-subtle) 1px, transparent 1px);
  background-size: 40px 40px;
}
```

### 11.3 Thumbnails de Curso

Proporção recomendada: **16:9** (1280x720).
Border radius: `var(--cp-radius-lg)`.
Fallback: gradiente primário com ícone do curso centralizado.

---

## 12. Tokens Z-Index

```css
:root {
  --cp-z-base: 0;
  --cp-z-dropdown: 100;
  --cp-z-sticky: 200;
  --cp-z-overlay: 300;
  --cp-z-modal: 400;
  --cp-z-toast: 500;
  --cp-z-confetti: 600;
}
```

---

## 13. Estrutura da Página de Documentação

A página HTML do design system terá:

1. **Header** com logo Classplay, toggle dark/light, botão download markdown
2. **Sidebar de navegação** com links âncora para cada seção
3. **Seções:**
   - Cores (swatches interativos com cópia de valor ao clicar)
   - Tipografia (preview de cada tamanho/peso)
   - Espaçamento (visualização da escala)
   - Border Radius (preview visual)
   - Sombras (preview visual)
   - Botões (todos os estados: default, hover, active, disabled)
   - Formulários (inputs, selects, toggles)
   - Cards (todas as variantes)
   - Badges e Tags
   - Gamificação (XP, streaks, achievements, leaderboard, missions, levels)
   - Animações (demos interativas)
   - Loading states (spinner, skeletons)
   - Toasts / Notificações
   - Layout e Grid
   - Gradientes e Fundos
4. **Botão de download** que gera o markdown completo do design system

A página é autocontida — um único arquivo HTML sem dependências externas (exceto Google Fonts).

---

## 14. Resumo de Decisões

| Decisão | Escolha |
|---|---|
| Público | Adultos 35-45, tech/IA |
| Inspiração | Duolingo, mas maduro e profissional |
| Cor primária | Roxo #7C3AED |
| Paleta | Multi-cor com funções específicas (7 cores + escalas completas) |
| Tipografia | Nunito (display) + JetBrains Mono (code) |
| Botões | 3D para CTAs, flat para secundários |
| Border radius | Moderado (8-12px) |
| Animações | Ricas (confetti, bounce, shake, count-up) |
| Gamificação | Pacote completo (XP, streaks, níveis, badges, ranking, missões) |
| Temas | Dark + Light via CSS custom properties |
| Framework | Agnóstico (CSS vars puras) |
| Acessibilidade | Focus visible, reduced motion, semantic HTML |
| Responsivo | Mobile-first com sidebar drawer em telas < 1024px |
| Entregável | Página HTML única + markdown para download |
