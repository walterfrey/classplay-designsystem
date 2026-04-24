# Tokens

> Variaveis CSS do projeto. Gerado a partir do briefing.

---

## Projeto

| Campo | Valor |
|-------|-------|
| Nome | NXZ |
| Tipo | Site institucional/comercial (SaaS de gestao de franquias food service) |
| Plataforma | Web (Next.js + Tailwind CSS), mobile-first |

---

## Cores

> Inspirado na paleta do Square: fundo quente, texto preto puro, pasteis suaves.

### Base

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--background` | hsl(40, 10%, 98%) | hsl(40, 6%, 9%) | Fundo principal (off-white quente em light, warm near-black em dark) |
| `--foreground` | hsl(0, 0%, 0%) | hsl(40, 10%, 96%) | Texto principal |
| `--muted` | hsl(40, 10%, 96%) | hsl(40, 5%, 13%) | Fundos secundarios (layer-01) |
| `--muted-foreground` | hsl(0, 0%, 44%) | hsl(40, 6%, 64%) | Texto secundario |
| `--disabled-foreground` | hsl(0, 0%, 64%) | hsl(40, 5%, 40%) | Texto/icones em elementos disabled |

### Acoes

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--primary` | hsl(262, 80%, 55%) | hsl(262, 80%, 55%) | Acoes principais. **Preservado em dark** (approach Radix) — marca mantem equity |
| `--primary-foreground` | hsl(0, 0%, 100%) | hsl(0, 0%, 100%) | Texto sobre primary (branco em ambos) |
| `--secondary` | hsl(262, 30%, 94%) | hsl(262, 25%, 18%) | Acoes secundarias (roxo pastel em light, roxo sombrio em dark) |
| `--secondary-foreground` | hsl(262, 60%, 35%) | hsl(262, 70%, 82%) | Texto sobre secondary (Radix step 11 em dark) |
| `--accent` | hsl(40, 10%, 96%) | hsl(40, 5%, 13%) | Destaques, hover |
| `--accent-foreground` | hsl(0, 0%, 0%) | hsl(40, 10%, 96%) | Texto sobre accent |

### Estados

> Semanticos deslocam ~10-15% lighter, ~10% menos saturado em dark (padrao IBM Carbon / MD3).

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--destructive` | hsl(0, 72%, 51%) | hsl(0, 75%, 64%) | Erros, acoes destrutivas |
| `--destructive-foreground` | hsl(0, 0%, 100%) | hsl(0, 0%, 100%) | Texto sobre destructive |
| `--success` | hsl(152, 60%, 42%) | hsl(152, 55%, 55%) | Sucesso, confirmacoes |
| `--success-foreground` | hsl(0, 0%, 100%) | hsl(0, 0%, 100%) | Texto sobre success |
| `--warning` | hsl(38, 92%, 50%) | hsl(38, 92%, 55%) | Alertas (pouca mudanca — amarelo ja e luminante) |
| `--warning-foreground` | hsl(38, 50%, 10%) | hsl(38, 50%, 10%) | Texto sobre warning (permanece escuro) |

### Superficies

> Modelo **Carbon-flat**: camadas lisas de cinza em dark (sem tonal overlay estilo MD3). Elevacao vem da mudanca de cor de fundo, nao de sombras.

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--card` | hsl(0, 0%, 100%) | hsl(40, 5%, 16%) | Cards (layer-02) |
| `--card-foreground` | hsl(0, 0%, 0%) | hsl(40, 10%, 96%) | Texto em cards |
| `--popover` | hsl(0, 0%, 100%) | hsl(40, 5%, 19%) | Popovers/dropdowns (layer-03, mais elevado) |
| `--popover-foreground` | hsl(0, 0%, 0%) | hsl(40, 10%, 96%) | Texto em popovers |

### Bordas e Focus

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--border` | hsl(0, 0%, 80%) | hsl(40, 4%, 23%) | Bordas gerais |
| `--input` | hsl(0, 0%, 80%) | hsl(40, 4%, 23%) | Borda de inputs |
| `--ring` | hsl(262, 80%, 55%) | hsl(262, 80%, 55%) | Focus ring (roxo primary em ambos) |

### Cores Adicionais (Secoes e pasteis)

> **Decisao D1**: pasteis **sombrios** em dark (nao abandonados). Preservam o ritmo visual de secoes alternadas do padrao Square.

| Token | Light | Dark | Uso |
|-------|-------|------|-----|
| `--warm-gray` | hsl(40, 10%, 96%) | hsl(40, 5%, 13%) | Fundo de secoes alternadas |
| `--pastel-purple` | hsl(270, 40%, 95%) | hsl(270, 25%, 16%) | Fundo de secoes com identidade NXZ |
| `--pastel-blue` | hsl(206, 50%, 87%) | hsl(206, 25%, 18%) | Fundo de cards/secoes |
| `--pastel-green` | hsl(72, 60%, 88%) | hsl(120, 20%, 15%) | Fundo de testimonials/depoimentos |
| `--pastel-amber` | hsl(38, 45%, 95%) | hsl(38, 22%, 16%) | Destaques de atencao/numeros |

### Chart Palette

> Paleta de dados para dashboard (barras, series, KPIs multi-categoria). Light usa step 9 da Radix; dark usa Radix dark step 9.

| Token | Light | Dark | Hue (Radix) |
|-------|-------|------|-------------|
| `--chart-1` | #7430e8 | #8e4ec6 | purple |
| `--chart-2` | #0d74ce | #0091ff | blue |
| `--chart-3` | #29a383 | #12a594 | teal |
| `--chart-4` | #e5484d | #e5484d | red |
| `--chart-5` | #f76b15 | #f76b15 | orange |

---

## Tipografia

> Inspirado no Square: serif para headings (editorial/premium), sans arredondada para corpo.

### Familias

| Token | Valor | Uso |
|-------|-------|-----|
| `--font-serif` | "DM Serif Display", Georgia, "Times New Roman", serif | Headlines hero, titulos H1/H2, citacoes grandes (equivalente ao "Exact Block" do Square) |
| `--font-sans` | "Plus Jakarta Sans", system-ui, sans-serif | Interface, corpo, nav, botoes, subtitulos (equivalente ao "Cash Sans" do Square - arredondada e amigavel) |
| `--font-mono` | "JetBrains Mono", ui-monospace, monospace | Numeros, metricas, dados, KPIs |

### Tamanhos

| Token | Valor | Line-height | Uso |
|-------|-------|-------------|-----|
| `--text-xs` | 0.75rem (12px) | 1rem (16px) | Labels pequenos, badges |
| `--text-sm` | 0.875rem (14px) | 1.25rem (20px) | Texto secundario, captions |
| `--text-base` | 1rem (16px) | 1.5rem (24px) | Texto padrao, paragrafos (Square body = 16px/24px) |
| `--text-lg` | 1.125rem (18px) | 1.625rem (26px) | Subtitulos, lead text, botoes CTA (Square CTA = 18px) |
| `--text-xl` | 1.25rem (20px) | 1.75rem (28px) | Titulos de secao menores |
| `--text-2xl` | 1.5rem (24px) | 1.8rem (28.8px) | Titulos de card/secao (Square card headings = 24px) |
| `--text-3xl` | 1.75rem (28px) | 2.375rem (38px) | Subtitulos de secao (Square H3 = 28px/38px) |
| `--text-4xl` | 2.5rem (40px) | 2.8rem (45px) | Titulos de secao H2 (Square H2 = 40px/45px) |
| `--text-5xl` | 2.75rem (44px) | 3.25rem (52px) | Hero headlines mobile (Square H2 large = 44px/52px) |
| `--text-6xl` | 4rem (64px) | 1.1 | Hero headlines desktop (Square H1 = 64px) |
| `--text-7xl` | 5.625rem (90px) | 1 | Hero headlines impacto (Square product hero = 90px/90px) |

### Pesos

| Token | Valor | Uso |
|-------|-------|-----|
| `--font-normal` | 400 | Texto corrido, paragrafos, headings serif (Square usa 400 para headings) |
| `--font-medium` | 500 | Enfase leve, botoes, nav items (Square CTA = 500) |
| `--font-semibold` | 600 | Labels, badges, destaques |
| `--font-bold` | 700 | Subtitulos sans-serif que precisam de enfase |

> **NOTA:** Os headings serif (font-serif) usam peso 400 — o proprio desenho da serif ja transmite peso visual. NAO usar bold em headings serif (este e o padrao do Square).

### Letter Spacing

| Token | Valor | Uso |
|-------|-------|-----|
| `--tracking-tighter` | -0.04em | Hero headlines (Square H1 = -3.6px em 90px ≈ -0.04em) |
| `--tracking-tight` | -0.02em | Headings H2 serif (Square H2 = -0.8px em 40px = -0.02em) |
| `--tracking-normal` | 0em | Texto padrao, paragrafos |
| `--tracking-wide` | 0.05em | Labels uppercase, overlines, badges |

---

## Espacamento

> Respiro generoso inspirado no Google Antigravity (120px entre secoes) e Square (100-160px padding).

| Token | Valor | Uso |
|-------|-------|-----|
| `--space-1` | 0.25rem (4px) | Micro gaps (entre icone e label) |
| `--space-2` | 0.5rem (8px) | Padding interno pequeno |
| `--space-3` | 0.75rem (12px) | Gap medio |
| `--space-4` | 1rem (16px) | Gap padrao entre elementos |
| `--space-5` | 1.25rem (20px) | Gap entre items de card (Square gap = 20px) |
| `--space-6` | 1.5rem (24px) | Espacamento entre blocos |
| `--space-8` | 2rem (32px) | Padding interno de cards (Square card padding = 30px) |
| `--space-10` | 2.5rem (40px) | Gap entre cards em grid (Square gap = 40px) |
| `--space-12` | 3rem (48px) | Espacamento grande entre blocos |
| `--space-16` | 4rem (64px) | Espacamento entre secoes (mobile) |
| `--space-20` | 5rem (80px) | Espacamento entre secoes (tablet) |
| `--space-24` | 6rem (96px) | Padding vertical de secoes (desktop, Square = 100px) |
| `--space-30` | 7.5rem (120px) | Padding vertical de secoes grandes (Google Antigravity = 120px) |
| `--space-36` | 9rem (144px) | Padding de hero sections (Square hero = 140px) |
| `--space-40` | 10rem (160px) | Margem entre secoes principais (Square section margin = 160px) |

---

## Bordas

### Radius

> Botoes CTA usam formato pill (full). Cards usam 10px. Inputs usam 6px.

| Token | Valor | Uso |
|-------|-------|-------|
| `--radius-xs` | 0.25rem (4px) | Elementos pequenos, badges (Square nav items = 4px) |
| `--radius-sm` | 0.375rem (6px) | Inputs, campos de formulario |
| `--radius-md` | 0.625rem (10px) | Cards, tiles, secoes com fundo (Square padrao = 10px) |
| `--radius-lg` | 1rem (16px) | Cards grandes, secoes featured (Square testimonial card = 16px) |
| `--radius-full` | 9999px | Botoes CTA, tags, pills (Square CTA = 10000px, pill shape) |

### Border Width

| Token | Valor | Uso |
|-------|-------|-----|
| `--border-width` | 1px | Padrao (inputs, divisores, bordas de separacao como Square) |
| `--border-width-2` | 2px | Enfase (tabs ativas, focus ring, botoes outline como Square) |

---

## Sombras

| Token | Valor | Uso |
|-------|-------|-----|
| `--shadow-sm` | 0 1px 2px 0 rgba(0, 0, 0, 0.05) | Cards, elementos em repouso |
| `--shadow-md` | 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -2px rgba(0, 0, 0, 0.05) | Popovers, dropdowns, mega menu |
| `--shadow-lg` | 0 10px 15px -3px rgba(0, 0, 0, 0.08), 0 4px 6px -4px rgba(0, 0, 0, 0.04) | Modais, drawer mobile |

---

## Motion

### Duracoes

| Token | Valor | Uso |
|-------|-------|-----|
| `--duration-fast` | 150ms | Hover, focus, micro-interacoes |
| `--duration-normal` | 300ms | Transicoes de pagina, fade-in de conteudo |
| `--duration-slow` | 500ms | Drawer abrindo/fechando, modais, animacoes de entrada |

### Easing

| Token | Valor | Uso |
|-------|-------|-----|
| `--ease-default` | cubic-bezier(0.4, 0, 0.2, 1) | Padrao para a maioria das transicoes |
| `--ease-in` | cubic-bezier(0.4, 0, 1, 1) | Saida de elementos (fade out) |
| `--ease-out` | cubic-bezier(0, 0, 0.2, 1) | Entrada de elementos (fade in, slide in) |
| `--ease-in-out` | cubic-bezier(0.4, 0, 0.2, 1) | Movimento continuo, transicoes de pagina |

### Transicao de Pagina

| Propriedade | Valor |
|-------------|-------|
| Tipo | fade |
| Duracao | `--duration-normal` (300ms) |
| Easing | `--ease-out` |

---

## Opacidade

| Token | Valor | Uso |
|-------|-------|-----|
| `--opacity-disabled` | 0.5 | Elementos disabled |
| `--opacity-overlay` | 0.6 | Backdrops (drawer mobile, modais) |
| `--opacity-hover` | 0.8 | Hover em imagens e cards |

---

## Container

| Token | Valor | Uso |
|-------|-------|-----|
| `--container-sm` | 640px | Formularios, modais pequenos |
| `--container-md` | 768px | Conteudo de texto (blog, servicos) |
| `--container-lg` | 1024px | Conteudo padrao (cards, grids) |
| `--container-xl` | 1280px | Full width controlado (hero, secoes largas) |

---

## Densidade

**Modo escolhido**: `comfortable`

| Elemento | Compact | Default | **Comfortable** |
|----------|---------|---------|-----------------|
| Button height | 32px | 40px | **48px** |
| Input height | 32px | 40px | **48px** |
| Avatar | 24px | 32px | **40px** |
| Gap padrao | space-2 | space-3 | **space-4** |
| Nav height | 56px | 64px | **72px** |

Notas sobre densidade:
- Nav header tem **72px** de altura (Square nav = 72px)
- Secoes de pagina usam `--space-24` a `--space-36` entre si (estilo Square/Antigravity, MUITO espaco)
- Cards usam `--space-8` (32px) de padding interno (Square card = 30px)
- Botoes CTA: padding `12px 24px` (Square = `10px 20px`, NXZ um pouco mais generoso)
- Botoes CTA em hero sections usam height 56px
- Gap entre cards em grid: `--space-10` (40px, Square = 40px)

---

## Breakpoints

| Token | Valor | Uso |
|-------|-------|-----|
| `sm` | 640px | Mobile landscape |
| `md` | 768px | Tablet |
| `lg` | 1024px | Desktop |
| `xl` | 1280px | Desktop grande |

---

## Iconografia

| Propriedade | Valor |
|-------------|-------|
| Biblioteca | Lucide React |
| Tamanho padrao | 20px |
| Tamanho small | 16px |
| Tamanho large | 24px |
| Stroke width | 1.5 |
| Estilo | Outline / linha fina (estilo Apple/Stripe) |

---

## Botoes

> Estilo Square: botoes CTA com formato pill, sem borda visivel no primario, borda no secundario.

### Variantes

| Variante | Background | Texto | Borda | Radius | Padding | Font |
|----------|-----------|-------|-------|--------|---------|------|
| **Primary** | `--primary` (roxo) | branco | none | `--radius-full` (pill) | 12px 24px | font-sans, 18px, medium (500) |
| **Secondary (outline)** | transparent | `--primary` (roxo) | 2px solid `--primary` | `--radius-full` (pill) | 12px 24px | font-sans, 18px, medium (500) |
| **Ghost** | transparent | `--foreground` (preto) | none | `--radius-full` (pill) | 12px 24px | font-sans, 18px, medium (500) |
| **Dark** | `--foreground` (preto) | branco | none | `--radius-full` (pill) | 12px 24px | font-sans, 18px, medium (500) |

### Estados de botao

| Estado | Tratamento |
|--------|------------|
| Hover | Leve escurecimento (opacity 0.9) ou sutil scale(1.02) |
| Disabled | opacity 0.5, cursor not-allowed |
| Loading | Spinner inline + texto "Enviando..." |
| Focus | ring-2 ring-ring ring-offset-2 |

---

## Notas Adicionais

### Inspiracao Visual: Square + Google Antigravity
O Design System combina a tipografia editorial do Square (serif para headlines, sans arredondada para corpo) com o respiro generoso do Google Antigravity. Botoes CTA seguem o formato pill do Square.

### Paleta e Secoes Alternadas
Fundos alternados entre branco (`--card`), cinza quente (`--warm-gray` / `--muted`), e pasteis tematicos. Secoes escuras (fundo preto) podem ser usadas para depoimentos e CTAs de impacto, como o Square faz. O roxo forte (primary) aparece apenas em CTAs, links e destaques.

### Hierarquia Tipografica (Square Model)
- **font-serif** (DM Serif Display): APENAS para H1, H2, e citacoes grandes. Peso 400. Letter-spacing negativo.
- **font-sans** (Plus Jakarta Sans): Tudo mais — corpo, nav, botoes, H3, subtitulos, labels.
- **font-mono** (JetBrains Mono): Numeros de impacto (Proof Bar), metricas de cases, dados.

### Dark Mode (v2.1)

Tema claro/escuro implementado via `[data-theme="dark"]` no `<html>`. Fontes de referencia: IBM Carbon (superficies flat layered), Radix Colors (preservacao de brand em dark), Material Design 3 (regras de contraste semantico), Nielsen Norman Group (diretrizes de UX).

**Decisoes fundamentais:**
- **Base:** `hsl(40, 6%, 9%)` (warm near-black) — espelha o off-white quente do light. Nao usamos `#000` puro (gera halation contra imagens, MD3).
- **Superficies:** modelo Carbon-flat com camadas explicitas (`background` → `muted` → `card` → `popover` em luminosidades crescentes). Sem tonal overlay.
- **Brand:** roxo `#7430e8` **preservado** em dark (approach Radix, nao a desaturacao do MD3). Equity de marca vale mais que a teoria de "saturados vibram".
- **Hierarquia de texto:** tokens nomeados com hex explicito (nao opacity-on-white). Mais claro de implementar e nao vaza entre camadas de superficie.
- **Semanticos:** deslocam ~10-15% lighter em dark. Warning fica (amarelo alto ja e luminante).
- **Pasteis:** versao sombria em dark (nao abandonados). Preservam o ritmo de secoes alternadas.

**Comportamento do toggle:**
- Default segue `prefers-color-scheme` do SO
- Toggle manual no header persiste em `localStorage['nxz-theme']`
- Script inline no `<head>` evita FOUC
- Listener em `matchMedia` sincroniza com mudancas do SO quando usuario ainda nao fez override manual

**Classes invertidas:**
- `.nxz-section-bg--inverted` (antes `--dark` em v2.0) — inverte contraste contra o tema vigente. Usada em testimonial/CTA/footer (padrao Square).

### Pagina de Planos
A pagina /planos exibe tiers e funcionalidades incluidas, mas NAO exibe precos. CTAs direcionam para contato comercial.
