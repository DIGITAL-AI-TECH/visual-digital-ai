# Digital AI Design System — Referência para Desenvolvimento

> Use este arquivo como referência para qualquer trabalho de código, design ou IA na Digital AI.
> Última atualização automática pelo Design System Engine.

## Tokens Essenciais

### Cores Primárias

```css
--color-brand-500: #2D52EF;   /* Precisão — primary actions, links */
--color-brand-800: #3B2FC9;   /* Visão — secondary, gradients */
--color-brand-900: #0F1F5C;   /* Profundidade — dark bg, headers */
--color-accent-100: #E8EEFF;  /* Névoa — subtle bg, highlights */
```

### Cores Semânticas (use estas, não as primitivas)

```css
/* Texto */
--text-primary: #212529;         /* Corpo principal */
--text-secondary: #868E96;       /* Suporte, metadata */
--text-on-action: #FFFFFF;       /* Sobre botões coloridos */
--text-brand: #2D52EF;           /* Links, emphasis */

/* Background */
--bg-page: #F8F9FA;              /* Fundo da página */
--bg-primary: #FFFFFF;           /* Cards, modais */
--bg-brand: #0F1F5C;             /* Hero sections */

/* Ações */
--action-primary: #2D52EF;       /* Botão primário bg */
--action-primary-hover: #2344D4; /* Hover */
--border-focus: #2D52EF;         /* Focus ring */
```

### Tipografia

```css
font-family: 'Plus Jakarta Sans', sans-serif; /* Headings */
font-family: 'DM Sans', sans-serif;           /* Body */
```

**Escala de peso**: 400 (regular), 500 (medium), 600 (semibold), 700 (bold), 800 (extrabold)

### Espaçamento

Base: 4px. Multiplicadores: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96

```css
--spacing-4x: 16px;   /* padding padrão */
--spacing-6x: 24px;   /* padding cards */
--spacing-8x: 32px;   /* seções */
```

### Border Radius

```css
--border-radius-sm: 4px;    /* tags, badges pequenos */
--border-radius-md: 8px;    /* botões, inputs */
--border-radius-lg: 12px;   /* cards */
--border-radius-xl: 16px;   /* modais */
--border-radius-full: 9999px; /* pills, avatars */
```

### Shadows

```css
--shadow-sm: 0px 1px 3px 0px rgba(15,31,92,0.10), ...;  /* cards rest */
--shadow-md: 0px 4px 6px -1px rgba(15,31,92,0.10), ...; /* hover, float */
--shadow-brand: 0px 4px 20px -2px rgba(45,82,239,0.30); /* brand glow */
```

## Componentes

### Botão Primário

```html
<button class="btn btn-primary btn-md">Criar automação</button>
```

```css
/* Essência do botão primário */
.btn-primary {
  background: var(--action-primary);    /* #2D52EF */
  color: var(--text-on-action);          /* #FFFFFF */
  border-radius: var(--border-radius-md); /* 8px */
  font-weight: var(--font-semibold);     /* 600 */
  transition: all var(--duration-fast) var(--easing-default);
}
.btn-primary:hover {
  background: var(--action-primary-hover); /* #2344D4 */
  box-shadow: var(--shadow-brand);
}
```

### Input

```html
<div class="form-field">
  <label for="email">Email</label>
  <input id="email" type="email" placeholder="ex: joao@empresa.com" />
  <span class="form-hint">Usaremos para enviar relatórios</span>
</div>
```

### Card

```html
<div class="card">
  <div class="card-header">
    <h3>Automação Ativa</h3>
  </div>
  <div class="card-body">
    Conteúdo do card
  </div>
</div>
```

## Acessibilidade

- **Contraste mínimo**: 4.5:1 para texto normal, 3:1 para texto grande
- **Focus visible**: sempre visível, outline 3px brand-500
- **ARIA**: labelledby em modais, live regions em alerts
- **Reduced motion**: respeitar `prefers-reduced-motion`
- **Keyboard nav**: Tab, Shift+Tab, Enter, Escape, Arrow keys

## Dark Mode

Ativar via `[data-theme="dark"]` no `<html>`. Todos os tokens semânticos mudam automaticamente.

```js
document.documentElement.setAttribute('data-theme', 'dark');
```

## Arquivos do Design System

- `tokens/design-tokens.css` — CSS Custom Properties (importe este)
- `tokens/tokens-primitive.json` — W3C DTCG tokens primitivos
- `tokens/tokens-semantic.json` — Tokens semânticos
- `tokens/tokens-dark.json` — Overrides dark mode
- `tokens/tokens-components.json` — Tokens de componente
- `layout/grid.css` — Sistema de grid
- `layout/fluid-typography.css` — Tipografia fluida
- `motion/motion-system.css` — Animações e transições
- `docs/component-library.html` — Showcase interativo
- `docs/tokens-reference.html` — Referência visual de tokens
- `accessibility/contrast-report.md` — Relatório WCAG 2.2
- `content/content-style-guide.md` — Voice & Tone

## Importação Rápida

```html
<link rel="stylesheet" href="tokens/design-tokens.css">
<link rel="stylesheet" href="layout/grid.css">
<link rel="stylesheet" href="layout/fluid-typography.css">
<link rel="stylesheet" href="motion/motion-system.css">
```
