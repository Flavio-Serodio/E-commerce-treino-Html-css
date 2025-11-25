# E-commerce-treino-Html-css

Projeto de treino de HTML/CSS: loja online (template) chamada SyntaxWear.

**Descrição**:
- Projeto estático contendo um layout de e‑commerce com header fixo, hero, seções de categorias e cards de produtos.

**Como abrir**:
- Abra `index.html` no navegador (duplo clique ou via servidor local). Exemplo com Python (Windows PowerShell):

```

**Estrutura de pastas (resumo)**:
- `index.html` : página principal.
- `src/style/` : arquivos CSS
  - `reset.css`, `header.css`, `hero.css`, `product-category.css`, `images-product.css`, `footer.css`
- `src/images/` : imagens e ícones (subpastas `icons/` e `products/`).

**Pontos importantes / notas de desenvolvimento**:
- O `header` está com `position: fixed` para ficar flutuante sobre a página.
- Em `src/style/header.css` existem regras que podem causar espaçamento indesejado no layout do header:
  - `.nav-container` tem `margin-left: 10rem` e `width: 100%` — essas regras podem empurrar elementos e impedir que itens (ex.: inputs ou ícones) alcancem a extremidade do header.
  - `.menu-icon` tem `width: 100%` (quando escondida) — pode ocupar largura indesejada quando visível em telas menores.

Sugestões rápidas para corrigir o espaçamento do header:
- Remover `margin-left: 10rem` de `.nav-container` e usar `flex: 1` para que o nav ocupe só o espaço restante.
- Ajustar `.menu-icon { width: auto; }` para evitar que o ícone ocupe 100%.
- Garantir `box-sizing: border-box;` (pode ser global no `reset.css`) para previsibilidade de padding/width.

Exemplo mínimo (em `src/style/header.css`):

```css
.nav-container{
  display: flex;
  flex: 1; /* ocupa espaço restante sem forçar overflow */
  justify-content: space-between;
  align-items: center;
  margin-left: 0; /* remover margin fixa */
}
.menu-icon{ width: auto; }
.nav-center{ flex: 1; }
.nav-center input{ width: 100%; box-sizing: border-box; }
```

**Testes e verificação**:
- Use DevTools (F12) para inspecionar o `header` e ver quais elementos ocupam espaço (Box model).
- Recarregue com `Ctrl+F5` ao alterar CSS.

**Contribuição**:
- Faça um fork / branch, edite e abra um PR com descrição clara das mudanças.

**Licença**:
- Arquivos de exemplo — use conforme sua necessidade.

--
Arquivo gerado automaticamente pelo assistente para documentar o projeto.
