# nxz. Design System

Sistema de design para a plataforma **NXZ** — SaaS de governanca, operacao e performance para redes de alimentacao.

**Versao atual:** `2.1` &nbsp;•&nbsp; **Live:** [nxz-design-system.netlify.app](https://nxz-design-system.netlify.app)

---

## Visao Geral

O NXZ Design System documenta todos os tokens visuais, componentes e padroes de layout utilizados no site institucional e na plataforma NXZ. Arquivo unico (`index.html`), sem dependencias, sem build tools.

### Principios

- **Clareza** — Tipografia serifada para headlines, sans-serif para corpo
- **Espacamento generoso** — Whitespace ao estilo Google Antigravity
- **Consistencia** — Tokens centralizados com prefixo `--nxz-*`
- **Acessibilidade** — Light + Dark com contraste verificado em ambos os temas

---

## Tokens

| Categoria | Prefixo | Exemplo |
|-----------|---------|---------|
| Cores | `--nxz-primary` | `#7430e8` (gradient ate `#b34de6`) |
| Tipografia | `--nxz-font-heading` | DM Serif Display |
| Espacamento | `--nxz-space-*` | Base 4px (4px a 160px) |
| Radius | `--nxz-radius-*` | 4px a 9999px (pill) |
| Sombras | `--nxz-shadow-*` | sm, md, lg |
| Motion | `--nxz-motion-*` | 150ms, 300ms, 500ms |
| Densidade | `--nxz-density-*` | Button 40px, Input 48px, Nav 72px |
| Chart | `--nxz-chart-1..5` | 5 hues Radix (light + dark) |

### Fontes

| Familia | Uso | Token |
|---------|-----|-------|
| DM Serif Display | Headlines, logo | `--nxz-font-heading` |
| Plus Jakarta Sans | Body, UI | `--nxz-font-body` |
| JetBrains Mono | Numeros, codigo | `--nxz-font-mono` |

### Paleta de Cores (light)

| Token | Valor | Uso |
|-------|-------|-----|
| `--nxz-primary` | `#7430e8` | Cor principal (preservada em dark) |
| `--nxz-primary-end` | `#b34de6` | Fim do gradient |
| `--nxz-background` | `#fafaf9` | Fundo principal |
| `--nxz-foreground` | `#000000` | Texto principal |
| `--nxz-muted-foreground` | `#707070` | Texto secundario |
| `--nxz-warm-gray` | `#f6f5f4` | Fundo alternado |
| `--nxz-pastel-purple` | `#f9f1ec` | Secoes de destaque |
| `--nxz-destructive` | `#dc2828` | Erros |
| `--nxz-success` | `#2bab6f` | Sucesso |
| `--nxz-warning` | `#f59f0a` | Alertas |

> Valores dark disponiveis em `tokens.md` (tabelas com colunas Light + Dark preenchidas).

---

## Componentes

### Fundamentos
- Cores (principais, superficies, semanticas, pasteis, chart palette)
- Tipografia (escala de xs a 7xl)
- Espacamento (escala visual 4px-160px)
- Bordas & Radius
- Sombras
- Motion & Transicoes

### Componentes de UI
- **Botoes** — 5 variantes (Primary gradient, Secondary, Ghost, Dark, Outline Light), 3 tamanhos
- **Cards** — Product, Service e Case
- **Navegacao** — Header com logo serif, links, CTA pill, toggle de tema
- **Hero Sections** — Light e invertida, com overline + headline serif + CTAs
- **CTA Banner** — Fundo invertido com gradient buttons
- **Proof Bar** — Metricas com numeros mono
- **Testimonial** — Card pastel com quote serifada
- **FAQ Accordion** — Expand/collapse animado
- **Formularios** — Input, Textarea, Select, Label, validacao
- **Badges** — 6 variantes
- **Feedback** — Toast e Modal

### Secoes de Pagina
- **Steps** — Passos numerados (01, 02, 03)
- **Alternancia de Fundo** — Padrao de backgrounds alternados
- **Footer** — Grid 4 colunas, fundo invertido
- **Link Arrow** — Link com seta animada

### Dashboard (v2.0)
- **Dashboard Shell** — Layout com sidebar, header e area de conteudo
- **Sidebar de navegacao** — Grupos, itens e estado ativo
- **Stat Cards** — Cartoes de metrica com icone, valor, variacao e comparativo
- **Chart Cards** — Containers de grafico com titulo e periodo
- **Bar Chart** — Grafico de barras com tooltip e rotulos
- **Ranked List** — Lista ranqueada com badges (padrao e primaria)

### Dark Mode (v2.1)
- **Tema claro/escuro** via `[data-theme]` no `<html>` com toggle no header
- **Respeita `prefers-color-scheme`** + override manual persistido em `localStorage`
- **Script inline anti-FOUC** no `<head>` (sem flash de tema errado)
- **Modelo Carbon-flat** com superficies em camadas explicitas
- **Brand purple preservado** em dark (approach Radix, nao MD3)
- **Pasteis sombrios** em dark para manter ritmo de secoes alternadas
- **Paleta de chart** dedicada (5 hues) com variantes light/dark

### Guias
- Icones (Lucide-style, 24x24, stroke 2)
- Acessibilidade (WCAG 2.1 AA)
- Densidade

---

## Rodar localmente

```bash
# Qualquer servidor HTTP simples
python3 -m http.server 8000
# ou
npx serve .
```

Abra `http://localhost:8000` no navegador.

---

## Estrutura

```
.
├── index.html          # Design system completo (single-file)
├── image.png           # Logo NXZ
├── tokens.md           # Tokens em formato Markdown (light + dark)
├── patterns.md         # Patterns de UI
├── layers.md           # Regras por camada
└── learnings/          # Aprendizados do projeto
```

---

## Referencia

- **Site real:** [nxz-brain-wayiwkigxq-uc.a.run.app](https://nxz-brain-wayiwkigxq-uc.a.run.app/)
- **Design System live:** [nxz-design-system.netlify.app](https://nxz-design-system.netlify.app)

---

## Historico de Versao

### v2.1 — 2026-04-23

Suporte completo a **Dark Mode**, fundamentado em pesquisa de sistemas de design e UX (Material Design 3, IBM Carbon, Radix Colors, Nielsen Norman Group, Apple HIG).

**Adicoes**
- Tema claro/escuro via atributo `[data-theme]` no elemento raiz
- Toggle manual no header (icone sol/lua) persistido em `localStorage['nxz-theme']`
- Padrao segue `prefers-color-scheme` do sistema; override manual sobrepoe
- Script inline anti-FOUC no `<head>` evita flash de tema errado
- Listener em `matchMedia` sincroniza com mudancas do SO quando nao ha override
- Bloco completo `[data-theme="dark"]` no CSS com overrides para todos os tokens
- Nova paleta `--nxz-chart-1..5` (5 hues Radix) com variantes light/dark
- Novo token `--nxz-disabled-foreground` (text hierarchy)

**Decisoes tecnicas**
- **Superficies:** modelo Carbon-flat (camadas lisas de cinza), sem tonal overlay do MD3
- **Base dark:** warm near-black `hsl(40,6%,9%)` espelhando o off-white quente do light (nao `#000` puro)
- **Brand:** roxo `#7430e8` preservado em dark (approach Radix — brand equity > teoria de "saturados vibram")
- **Hierarquia de texto:** tokens nomeados com hex explicito (nao opacity-on-white)
- **Semanticos:** deslocam ~10-15% lighter em dark; warning fica
- **Pasteis:** versao sombria em dark para manter ritmo de secoes alternadas

**Refactors**
- Renomeada `.nxz-section-bg--dark` → `.nxz-section-bg--inverted` (nome honesto: inverte contraste contra o tema vigente)
- Cores hardcoded em Footer, CTA Banner e botao Outline Light substituidas por `color-mix(in srgb, var(--nxz-background) X%, transparent)` para flip automatico
- Tooltip do bar chart usa `var(--nxz-background)` em vez de `--nxz-primary-foreground` (fixo em branco, quebrava em dark)

**Escopo**
- `generated/index.html`: 161 KB → ~170 KB
- `generated/tokens.md`: colunas "Dark" preenchidas em todas as tabelas; nova secao "Chart Palette"; nota "Sem Dark Mode" substituida por doc do sistema de tema

### v2.0 — 2026-04-23

Expansao do design system para cobrir a area logada da plataforma.

**Adicoes**
- Nova secao **Dashboard** com biblioteca de componentes para a aplicacao
- **Dashboard Shell** — layout base com sidebar, header e area de conteudo
- **Sidebar de navegacao** com grupos, itens e estado ativo (`nxz-dashboard-sidebar`)
- **Stat Cards** — metricas com icone, valor, variacao percentual e comparativo (`nxz-stat-card`)
- **Chart Cards** — containers de grafico com titulo e seletor de periodo (`nxz-chart-card`)
- **Bar Chart** — grafico de barras com tooltip no hover e rotulos inferiores (`nxz-bar-chart`)
- **Ranked List** — lista ranqueada com badges numericos (padrao e primaria) (`nxz-ranked-list`)
- Novo utilitario `ds-subsection-desc` para descricoes de subsecao

**Escopo**
- `generated/index.html`: 128 KB → 161 KB (+25%)

### v1.0 — 2026-04

Lancamento inicial do design system cobrindo o site institucional.

**Fundamentos**
- Tokens de cor, tipografia, espacamento, radius, sombras e motion com prefixo `--nxz-*`
- Fontes: DM Serif Display (headlines), Plus Jakarta Sans (body), JetBrains Mono (numeros/codigo)
- Paleta principal: `#7430e8` → `#b34de6` (gradient)

**Componentes de UI**
- Botoes (5 variantes), Cards (Product, Service, Case), Navegacao, Hero Sections (light/dark)
- CTA Banner, Proof Bar, Testimonial, FAQ Accordion, Formularios, Badges, Toast, Modal

**Secoes de Pagina**
- Steps numerados, alternancia de fundos, Footer, Link Arrow

**Guias**
- Icones (Lucide-style), Acessibilidade (WCAG 2.1 AA), Densidade

---

NXZ &copy; 2026. Todos os direitos reservados.
