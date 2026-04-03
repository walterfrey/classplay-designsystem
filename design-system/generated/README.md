# nxz. Design System

Sistema de design para a plataforma **NXZ** — SaaS de governanca, operacao e performance para redes de alimentacao.

**Live:** [nxz-design-system.netlify.app](https://nxz-design-system.netlify.app)

---

## Visao Geral

O NXZ Design System documenta todos os tokens visuais, componentes e padroes de layout utilizados no site institucional e na plataforma NXZ. Arquivo unico (`index.html`), sem dependencias, sem build tools.

### Principios

- **Clareza** — Tipografia serifada para headlines, sans-serif para corpo
- **Espacamento generoso** — Whitespace ao estilo Google Antigravity
- **Consistencia** — Tokens centralizados com prefixo `--nxz-*`

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

### Fontes

| Familia | Uso | Token |
|---------|-----|-------|
| DM Serif Display | Headlines, logo | `--nxz-font-heading` |
| Plus Jakarta Sans | Body, UI | `--nxz-font-body` |
| JetBrains Mono | Numeros, codigo | `--nxz-font-mono` |

### Paleta de Cores

| Token | Valor | Uso |
|-------|-------|-----|
| `--nxz-primary` | `#7430e8` | Cor principal |
| `--nxz-primary-end` | `#b34de6` | Fim do gradient |
| `--nxz-background` | `#fafaf9` | Fundo principal |
| `--nxz-foreground` | `#000000` | Texto principal |
| `--nxz-muted-foreground` | `#707070` | Texto secundario |
| `--nxz-warm-gray` | `#f6f5f4` | Fundo alternado |
| `--nxz-pastel-purple` | `#f9f1ec` | Secoes de destaque |
| `--nxz-destructive` | `#dc2828` | Erros |
| `--nxz-success` | `#2bab6f` | Sucesso |
| `--nxz-warning` | `#f59f0a` | Alertas |

---

## Componentes

### Fundamentos
- Cores (principais, superficies, semanticas, pasteis)
- Tipografia (escala de xs a 7xl)
- Espacamento (escala visual 4px-160px)
- Bordas & Radius
- Sombras
- Motion & Transicoes

### Componentes de UI
- **Botoes** — 5 variantes (Primary gradient, Secondary, Ghost, Dark, Outline Light), 3 tamanhos
- **Cards** — Product, Service e Case
- **Navegacao** — Header com logo serif, links, CTA pill
- **Hero Sections** — Light e dark, com overline + headline serif + CTAs
- **CTA Banner** — Fundo escuro com gradient buttons
- **Proof Bar** — Metricas com numeros mono
- **Testimonial** — Card pastel com quote serifada
- **FAQ Accordion** — Expand/collapse animado
- **Formularios** — Input, Textarea, Select, Label, validacao
- **Badges** — 6 variantes
- **Feedback** — Toast e Modal

### Secoes de Pagina
- **Steps** — Passos numerados (01, 02, 03)
- **Alternancia de Fundo** — Padrao de backgrounds alternados
- **Footer** — Grid 4 colunas, fundo preto
- **Link Arrow** — Link com seta animada

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
├── tokens.md           # Tokens em formato Markdown
├── patterns.md         # Patterns de UI
├── layers.md           # Regras por camada
└── learnings/          # Aprendizados do projeto
```

---

## Referencia

- **Site real:** [nxz-brain-wayiwkigxq-uc.a.run.app](https://nxz-brain-wayiwkigxq-uc.a.run.app/)
- **Design System live:** [nxz-design-system.netlify.app](https://nxz-design-system.netlify.app)

---

NXZ &copy; 2026. Todos os direitos reservados.
