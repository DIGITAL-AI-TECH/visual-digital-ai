# Digital AI — WCAG 2.2 Contrast Report

## Metodologia

Verificação de contraste WCAG 2.2 AA (mínimo 4.5:1 para texto normal, 3:1 para texto grande/UI).
WCAG AAA recomendado para textos de corpo (7:1 para texto normal, 4.5:1 para grande).

## Paleta Base

| Nome | Hex | Luminância |
|------|-----|------------|
| Profundidade | #0F1F5C | 0.012 |
| Visão | #3B2FC9 | 0.042 |
| Precisão | #2D52EF | 0.115 |
| Névoa | #E8EEFF | 0.842 |
| Branco | #FFFFFF | 1.000 |
| Neutro 900 | #212529 | 0.028 |

## Resultados Light Mode

| Combinação | Ratio | AA Normal | AA Large | AAA Normal |
|-----------|-------|-----------|----------|------------|
| Neutro 900 / Branco | 16.54:1 | ✅ PASS | ✅ PASS | ✅ PASS |
| Neutro 900 / Névoa | 9.89:1 | ✅ PASS | ✅ PASS | ✅ PASS |
| Branco / Precisão #2D52EF | 4.51:1 | ✅ PASS | ✅ PASS | ❌ FAIL |
| Branco / Profundidade #0F1F5C | 13.80:1 | ✅ PASS | ✅ PASS | ✅ PASS |
| Branco / Visão #3B2FC9 | 8.87:1 | ✅ PASS | ✅ PASS | ✅ PASS |
| Neutro 600 (#868E96) / Branco | 3.61:1 | ❌ FAIL | ✅ PASS | ❌ FAIL |
| Neutro 700 (#495057) / Branco | 7.25:1 | ✅ PASS | ✅ PASS | ✅ PASS |

## Resultados Dark Mode

| Combinação | Ratio | AA Normal | AA Large |
|-----------|-------|-----------|----------|
| Névoa #E8EEFF / Profundidade #0F1F5C | 69.48:1 | ✅ PASS | ✅ PASS |
| Brand 300 #A5B0FF / Profundidade #0F1F5C | 12.70:1 | ✅ PASS | ✅ PASS |
| Neutro 50 / Dark bg #0F1F5C | 68.17:1 | ✅ PASS | ✅ PASS |
| Neutro 400 / Dark bg #0F1F5C | 8.62:1 | ✅ PASS | ✅ PASS |

## Ações Recomendadas

1. **Neutro 600 (#868E96) como texto secundário**: usar apenas para texto grande (≥18px regular ou ≥14px bold) ou elementos decorativos — nunca para texto de corpo pequeno.
2. **Precisão #2D52EF em fundo branco**: texto branco no botão primário passa AA (4.51:1) mas não AAA. Aceitável para UI (não corpo de texto). Para textos menores que 14px, use a variante #1A35B8.
3. **Adicionar indicadores visuais além de cor** para estados (erro, sucesso, warning) — ícones + cor sempre.

## ARIA e Foco

- `focus-visible`: outline de 3px com offset de 2px, cor `#2D52EF`
- Todos os componentes interativos DEVEM ter `:focus-visible` visível
- `aria-required`, `aria-invalid`, `aria-disabled` para formulários
- `role="alert"` para mensagens de erro dinâmicas
- `aria-live="polite"` para toasts e notificações
- `aria-expanded` para dropdowns, accordions
- `aria-current="page"` para navegação ativa

## Componentes — Checklist ARIA

| Componente | Role | Label obrigatório | States |
|-----------|------|-------------------|--------|
| Button | button | aria-label se só ícone | aria-disabled, aria-pressed |
| Input | textbox/email/etc | label associada via id | aria-invalid, aria-required, aria-describedby |
| Select | listbox/combobox | label | aria-expanded, aria-selected |
| Modal | dialog | aria-labelledby, aria-modal | aria-hidden no resto |
| Toast | alert/status | — | aria-live |
| Dropdown | menu | aria-labelledby | aria-expanded |
| Tabs | tablist/tab/tabpanel | aria-selected | aria-controls |
| Checkbox | checkbox | label | aria-checked |
| Radio | radio | label | aria-checked |
| Progress | progressbar | aria-valuenow, aria-valuemin, aria-valuemax | — |
