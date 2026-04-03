# Patterns

> Patterns escolhidos para o projeto e referencias.

---

## Projeto

| Campo | Valor |
|-------|-------|
| Nome | NXZ |
| Recipe base | **Square** (serif headlines, pill CTAs, warm grays, alternating sections, editorial feel) + **Google Antigravity** (respiro generoso, whitespace extremo) |

---

## Patterns Selecionados

### Navegacao

| Pattern | Usar | Referencia |
|---------|------|------------|
| Sidebar | [ ] | -- |
| Tab Bar | [ ] | -- |
| App Bar | [x] | Apple, Stripe -- top bar sticky com logo, mega menu, CTA |
| Drawer | [x] | Mobile -- hamburger abre drawer lateral com navegacao completa |
| Breadcrumb | [x] | Subpaginas de produto e servico (/para-restaurantes/pdv, /servicos/diagnostico) |
| Tabs | [x] | Pagina de Planos (tab Franqueadores / tab Lojas), secoes com alternancia |
| Command Palette | [ ] | -- |

### Layout

| Pattern | Usar | Referencia |
|---------|------|------------|
| Feed | [x] | Blog -- lista de artigos com paginacao |
| Kanban | [ ] | -- |
| Master-Detail | [x] | Mega menu de Solucoes (categorias + itens), Cases (grid + detalhe) |
| Grid Gallery | [x] | Cards de produtos (PDV, KDS, Delivery), cards de servicos, cases |
| Dashboard | [ ] | -- |
| Split View | [x] | Hero com split (texto + imagem), secao "Para quem" (Franqueador vs Loja) |
| Canvas | [ ] | -- |

### Interacao

| Pattern | Usar | Referencia |
|---------|------|------------|
| Infinite Scroll | [ ] | -- |
| Pull to Refresh | [ ] | -- |
| Drag and Drop | [ ] | -- |
| Swipe Actions | [ ] | -- |

### Feedback

| Pattern | Usar | Referencia |
|---------|------|------------|
| Modal | [x] | Confirmacao de envio de formulario (fallback), avisos importantes |
| Toast | [x] | Feedback principal -- formulario enviado, erros, notificacoes (auto-dismiss) |
| Tooltip | [x] | Explicacoes em planos, funcionalidades, icones de ajuda |
| Accordion | [x] | FAQ em /planos, /servicos, paginas de produto |

### Conteudo

| Pattern | Usar | Referencia |
|---------|------|------------|
| Chat | [ ] | -- (WhatsApp e widget externo, nao nativo) |
| Rich Text | [x] | Blog posts (MDX), paginas de servico com conteudo longo |
| Pagination | [x] | Blog, cases -- paginacao de listagens |

### Data Entry

| Pattern | Usar | Referencia |
|---------|------|------------|
| Search + Filters | [x] | Blog (por categoria), Cases (por tipo: Franqueador/Loja/Segmento) |
| Multi-step Form | [x] | Formulario de contato com segmentacao por persona (radio button + campos contextuais) |

### Sistema

| Pattern | Usar | Referencia |
|---------|------|------------|
| Offline Mode | [ ] | -- |
| Realtime | [ ] | -- |

---

## Layout Principal

**Estrutura escolhida**:

```
[x] Top Bar + Content
```

**Esboco Desktop**:

```
+--------------------------------------------------+
| Logo   Solucoes v  Servicos  Planos  Cases  Blog  [Fale Conosco] |  <- Top Bar (sticky)
+--------------------------------------------------+
|                                                    |
|                   Hero Section                     |
|              (headline + CTA + imagem)             |
|                                                    |
+--------------------------------------------------+
|                                                    |
|              Secao de conteudo 1                   |
|           (fundo pastel alternado)                 |
|                                                    |
+--------------------------------------------------+
|                                                    |
|              Secao de conteudo 2                   |
|             (fundo branco/neutro)                  |
|                                                    |
+--------------------------------------------------+
|                                                    |
|                 CTA Banner Final                   |
|                                                    |
+--------------------------------------------------+
|                     Footer                         |
|        (links, contato, redes sociais, legal)      |
+--------------------------------------------------+
```

**Esboco Mobile**:

```
+---------------------+
| Logo    [Hamburger]  |  <- Top Bar (sticky)
+---------------------+
|                      |
|    Hero Section      |
|   (stack vertical)   |
|                      |
+---------------------+
|                      |
|   Secao conteudo 1   |
|   (fundo pastel)     |
|                      |
+---------------------+
|                      |
|   CTA Banner Final   |
|                      |
+---------------------+
|       Footer         |
+---------------------+
|  [WhatsApp FAB]      |  <- Flutuante canto inferior direito
+---------------------+
```

---

## Navegacao

| Breakpoint | Componente |
|------------|------------|
| Mobile | Top bar sticky (logo + hamburger) -> Drawer lateral com menu completo |
| Tablet | Top bar sticky (logo + menu horizontal simplificado + CTA) |
| Desktop | Top bar sticky (logo + mega menu Solucoes + links + CTA "Fale Conosco") |

### Mega Menu (Solucoes) -- Desktop

```
+------------------------------------------+
| PARA FRANQUEADORES      PARA LOJAS       |
| BI Executivo            PDV              |
| Governanca              KDS              |
| Servicos Estrategicos   Delivery         |
| Pacotes de Rede         Autoatendimento  |
|                         Estoque          |
| -----------------------------------      |
| BI & Dados (para todos)                  |
+------------------------------------------+
```

---

## Extensions shadcn

| Extension | Pattern | Instalar |
|-----------|---------|----------|
| cmdk | Command Palette | [ ] |
| vaul | Drawer, Bottom Sheet | [x] |
| sonner | Toasts | [x] |
| embla | Carousel | [x] |
| react-day-picker | Date Picker | [ ] |
| recharts | Charts | [ ] |
| react-resizable-panels | Split View | [ ] |
| @dnd-kit | Drag and Drop | [ ] |
| @tanstack/virtual | Virtualizacao | [ ] |
| @tanstack/table | Tabelas | [ ] |
| tiptap | Rich Text | [ ] |

### Bibliotecas adicionais recomendadas

| Biblioteca | Pattern | Instalar |
|------------|---------|----------|
| framer-motion | Animacoes fade-in, scroll reveal | [x] |
| next-mdx-remote ou @next/mdx | Blog posts em MDX | [x] |
| react-intersection-observer | Scroll-triggered animations | [x] |
| lucide-react | Iconografia | [x] |

---

## Combinacao (Recipe)

**Tipo de app mais proximo**: Site institucional SaaS premium (Square + Google Antigravity)

| Recipe | Patterns Core |
|--------|---------------|
| **NXZ Site** | **top-bar, mega-menu, hero-sections, card-grid, split-view, accordion, toast, drawer-mobile, tabs, search-filters, multi-step-form, testimonial-sections, pill-ctas** |
| **Square** (ref principal) | top-bar, serif-headlines, pill-ctas, card-tiles, accordion, split-view, alternating-bg, testimonial-gradient |
| **Google Antigravity** (ref respiro) | extreme-whitespace, pill-ctas, large-typography, fade-in-scroll |
| Linear | sidebar, kanban, command, master-detail |
| Notion | sidebar, rich-text, master-detail, command |

---

## Densidade por Area

> Espacamento segue o padrao Square/Antigravity: MUITO respiro entre secoes.

| Area | Densidade | Notas (ref Square) |
|------|-----------|-------------------|
| Navegacao (top bar) | Default | 72px altura, items bem espacados, padding 18px 10px |
| Hero sections | Extra-comfortable | padding-y 80-140px, headline serif 64-90px, CTAs pill generosos |
| Cards de produto/servico | Comfortable | padding 30px, gap 40px entre cards, border-radius 10px |
| Secoes de conteudo | Extra-comfortable | padding-y 100-120px (Square padrao), margin-y 160px entre secoes |
| Proof Bar (numeros) | Default | numeros em font-mono destacados |
| Testimonial/Depoimentos | Extra-comfortable | fundo gradiente pastel, citacao em font-serif grande, padding 60px |
| FAQ Accordion | Comfortable | items com padding 20px, borda separadora 1px, icone +/- |
| Formularios | Comfortable | inputs 48px, labels claros, espacamento generoso |
| Footer | Default | compacto mas legivel, links organizados em colunas |
| Blog feed | Comfortable | cards com imagem + texto, border-radius 10px, gap 20-30px |

---

## Estados Globais

### Loading

| Contexto | Tratamento |
|----------|------------|
| Pagina inteira | Skeleton -- placeholders cinza mimetizando layout da pagina |
| Secao/widget | Skeleton -- retangulos animados no tamanho dos cards/elementos |
| Botao/acao | Spinner inline no botao + texto "Enviando..." + disabled |
| Lista/feed | Skeleton -- 3-4 card placeholders com shimmer pulse |

### Empty

| Contexto | Tratamento |
|----------|------------|
| Lista vazia | Ilustracao + texto explicativo + CTA para acao |
| Busca sem resultado | Ilustracao + "Nenhum resultado encontrado" + sugestao de busca alternativa |
| Primeiro uso | Ilustracao de boas-vindas + texto de orientacao + CTA principal |

### Error

| Contexto | Tratamento |
|----------|------------|
| Erro de rede | Toast com mensagem + botao "Tentar novamente" |
| Erro de validacao | Inline abaixo do campo com texto vermelho + icone |
| Erro fatal | Pagina de erro dedicada (404/500) com ilustracao + link para Home |

---

## Componentes Reutilizaveis do Site

Baseado na arquitetura de informacao (doc 18) + estilos do Square:

| Componente | Onde aparece | Descricao | Estilo Square |
|------------|-------------|-----------|---------------|
| **HeroSection** | Todas as paginas | Headline serif grande + subtitulo sans + 2 CTAs pill + imagem. Variantes: split (texto+imagem), centralizado, fundo dark | Headline em font-serif 64-90px, peso 400, letter-spacing negativo. CTAs pill side-by-side (primary + outline) |
| **ProductCard** | Home, Para Franqueadores, Para Restaurantes | Imagem + titulo + descricao curta + link. Grid responsivo | border-radius 10px, padding 30px, fundo warm-gray ou pastel-blue, sem sombra (Square usa fundos em vez de sombras) |
| **ServiceCard** | Home, Servicos, Para Franqueadores | Headline + para quem + ticket + CTA pill | Mesmo estilo dos tiles do Square: imagem arredondada + texto abaixo |
| **PricingTable** | Planos, Pacotes | Colunas com destaque no plano recomendado. SEM precos, apenas features e CTA pill | Font-sans para features, font-serif para nome do plano, CTA pill em cada coluna |
| **CaseCard** | Home, Cases | Logo + segmento + resultado (font-mono) + link | border-radius 10px, tile com imagem, estilo resource card do Square |
| **CTABanner** | Rodape (antes do footer) | Headline serif + botao CTA pill. Fundo preto ou gradiente pastel | Square: secao escura com headline branca serif + CTA pill azul. NXZ: fundo preto ou primary com CTAs brancos |
| **TestimonialSection** | Home, Cases, Produto | Citacao grande em font-serif + autor + empresa. Fundo gradiente pastel | Square: fundo gradiente pastel (verde/amarelo), citacao serif 40-56px, weight 400 |
| **FAQAccordion** | Planos, Servicos, Produto | Perguntas expansiveis, icone +/-, borda separadora | Square: texto font-sans, titulo bold, bordas 1px entre items, icone +/- rotaciona |
| **ProofBar** | Home, Para Franqueadores | Numeros de impacto em font-mono (unidades, redes, NPS) | Numeros grandes font-mono, labels menores font-sans em muted-foreground |
| **NavHeader** | Global | Logo + menu font-sans + CTA pill "Fale Conosco". Sticky, 72px | Square: nav transparente sobre hero, depois bg branca ao scroll. Sub-nav sticky para paginas de produto |
| **Footer** | Global | Links por coluna, contato, redes sociais, legal | Font-sans, texto muted-foreground, links com underline on hover |
| **WhatsAppFAB** | Global | Botao flutuante canto inferior direito | Pill shape, sombra-lg, z-[100] |
| **PersonaSegment** | Home, Contato | Secao split para direcionar por persona (Franqueador / Loja) | Duas colunas com imagem + headline serif + CTA pill cada |

---

## Acessibilidade

| Regra | Valor |
|-------|-------|
| Contraste minimo texto | 4.5:1 |
| Contraste minimo UI | 3:1 |
| Touch target minimo | 44px |
| Focus ring | `ring-2 ring-ring ring-offset-2` |
| Reduced motion | Respeitar `prefers-reduced-motion` |
| Skip to content | Link oculto no topo para pular navegacao |
| Aria labels | Todos os botoes de icone, hamburger, links de navegacao |
| Semantica HTML | Uso correto de header, nav, main, section, article, footer |
| Alt text | Todas as imagens e ilustracoes com descricao |

---

## Notas de Implementacao

### Tipografia Editorial (Square Model)
- **Headlines de secao (H1, H2):** SEMPRE usar `font-serif` (DM Serif Display), peso 400, letter-spacing negativo
- **Subtitulos (H3, H4):** Usar `font-sans` (Plus Jakarta Sans), peso 500
- **Corpo, botoes, nav:** Usar `font-sans`, peso 400-500
- **Dados e metricas:** Usar `font-mono` (JetBrains Mono)
- **Citacoes grandes (testimonials):** Usar `font-serif`, tamanho 40-56px

### Botoes Pill (Square Model)
Todos os CTAs usam `border-radius: 9999px` (pill shape). Dois estilos principais:
- **Primary:** fundo roxo, texto branco, sem borda
- **Outline:** fundo transparente, texto roxo, borda 2px roxo
Ambos com padding `12px 24px`, font-size 18px, font-weight 500.

### Secoes Alternadas (Square Model)
Secoes alternam entre: branco (`--card`) → cinza quente (`--warm-gray`) → pastel tematico → preto (para CTAs de impacto). Square usa secoes escuras para testimonials e CTAs finais. Separacao visual e feita por **mudanca de fundo**, nao por bordas.

### Respiro Generoso (Google Antigravity)
Padding vertical de secoes deve ser **100-140px** no desktop (Square padrao). Heroes podem chegar a 160px. No mobile, reduzir para 60-80px. O espaco vazio e intencional e parte da identidade premium.

### Duas Personas, Uma Experiencia
O site bifurca a jornada a partir da Home ("Sou Franqueador" / "Tenho uma Loja"), mas mantem uma identidade visual unica. As paginas de persona usam os mesmos componentes com conteudo diferente.

### Mobile-First
60%+ do trafego vem de celular. Todos os componentes devem ser projetados mobile-first e expandir para desktop. Touch targets de 44px minimo. Drawer para navegacao mobile.

### WhatsApp Widget
Botao flutuante (FAB) pill shape no canto inferior direito em todas as paginas. Usar cor do WhatsApp (verde) ou primary da NXZ. Z-index alto (z-[100]).
