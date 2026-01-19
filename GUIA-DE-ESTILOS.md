# 🎨 Guia de Estilos - Agência Criativa Web

## 📐 Nomenclatura BEM

### Estrutura:
```
.bloco
.bloco__elemento
.bloco--modificador
.bloco__elemento--modificador
```

### Regras:
1. **Blocos** - Componentes independentes (ex: `.card`, `.btn`, `.header`)
2. **Elementos** - Partes do bloco (ex: `.card__title`, `.btn__icon`)
3. **Modificadores** - Variações do bloco ou elemento (ex: `.btn--primary`, `.card--centered`)

---

## 🎨 Paleta de Cores

### Cores Principais
```css
--color-primary: #6366f1    /* Azul Índigo */
--color-secondary: #8b5cf6  /* Roxo */
--color-accent: #ec4899     /* Rosa */
```

### Cores de Texto
```css
--color-text-primary: #1f2937    /* Cinza Escuro */
--color-text-secondary: #6b7280  /* Cinza Médio */
```

### Cores de Fundo
```css
--color-bg-primary: #ffffff      /* Branco */
--color-bg-secondary: #f9fafb    /* Cinza Claro */
--color-bg-dark: #111827         /* Cinza Muito Escuro */
```

---

## 📏 Espaçamentos

```css
--spacing-xs: 0.5rem  /* 8px */
--spacing-sm: 1rem    /* 16px */
--spacing-md: 2rem    /* 32px */
--spacing-lg: 4rem    /* 64px */
--spacing-xl: 6rem    /* 96px */
```

### Uso Recomendado:
- **xs**: Gaps pequenos, padding de ícones
- **sm**: Padding de elementos, gaps de lista
- **md**: Margem entre elementos, padding de cards
- **lg**: Espaçamento entre seções
- **xl**: Padding de seções principais

---

## 🔤 Tipografia

### Família
```css
--font-family-base: 'Poppins', sans-serif;
```

### Pesos
```css
--font-weight-light: 300      /* Leve */
--font-weight-regular: 400    /* Regular */
--font-weight-medium: 500     /* Médio */
--font-weight-semibold: 600   /* Semi-negrito */
--font-weight-bold: 700       /* Negrito */
```

### Altura de Linha
```css
--line-height-base: 1.6      /* Texto normal */
--line-height-tight: 1.2     /* Títulos */
--line-height-relaxed: 1.8   /* Texto longo */
```

### Escalas de Tamanho (usando clamp)
```css
/* Título Principal */
font-size: clamp(2rem, 5vw, 3.5rem);

/* Título de Seção */
font-size: clamp(2rem, 4vw, 3rem);

/* Subtítulo */
font-size: clamp(1rem, 2.5vw, 1.5rem);

/* Texto Base */
font-size: 1rem (16px);
```

---

## 🔲 Bordas

```css
--border-radius-sm: 8px      /* Inputs, small cards */
--border-radius-md: 15px     /* Cards, containers */
--border-radius-lg: 50px     /* Buttons */
--border-radius-full: 50%    /* Avatars, círculos */
```

---

## ⏱️ Transições

```css
--transition-fast: 0.15s ease   /* Hover rápido */
--transition-base: 0.3s ease    /* Padrão */
--transition-slow: 0.5s ease    /* Animações longas */
```

### Uso Recomendado:
```css
/* Hover em links/botões */
transition: color var(--transition-fast);

/* Transform e opacity */
transition: transform var(--transition-base), 
            opacity var(--transition-base);

/* Múltiplas propriedades */
transition: all var(--transition-base);
```

---

## 🌑 Sombras

```css
--shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.12)        /* Leve */
--shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1)         /* Média */
--shadow-lg: 0 10px 30px rgba(0, 0, 0, 0.15)      /* Forte */
--shadow-focus: 0 0 0 3px rgba(99, 102, 241, 0.1) /* Focus */
```

### Uso:
- **sm**: Cards em repouso
- **md**: Buttons, headers
- **lg**: Cards em hover, modais
- **focus**: Estados de foco em inputs

---

## 📱 Breakpoints

```css
/* Mobile First Approach */

/* Mobile: até 480px (padrão) */

/* Tablet: 481px - 768px */
@media (max-width: 768px) { ... }

/* Desktop: 769px+ (padrão) */

/* Desktop Grande: 1400px+ */
@media (min-width: 1400px) { ... }

/* Mobile Pequeno */
@media (max-width: 480px) { ... }
```

---

## 🎯 Z-Index Scale

```css
--z-content: 1      /* Conteúdo padrão */
--z-overlay: 2      /* Overlays, modais */
--z-header: 1000    /* Header fixo */
```

---

## 🧩 Componentes Reutilizáveis

### 🔘 Botão
```html
<!-- Primário -->
<button class="btn btn--primary">Clique</button>

<!-- Largura Total -->
<button class="btn btn--primary btn--full-width">Enviar</button>
```

### 🃏 Card
```html
<!-- Card Centralizado -->
<article class="card card--centered">
    <div class="card__icon">🎨</div>
    <h3 class="card__title">Título</h3>
    <p class="card__description">Descrição...</p>
</article>

<!-- Card Glass (Transparente) -->
<article class="card card--glass">
    <!-- conteúdo -->
</article>
```

### 📝 Formulário
```html
<form class="form">
    <div class="form__group">
        <label class="form__label" for="campo">Label</label>
        <input class="form__input" type="text" id="campo">
    </div>
    <div class="form__group">
        <label class="form__label" for="texto">Mensagem</label>
        <textarea class="form__textarea" id="texto"></textarea>
    </div>
</form>
```

### 📰 Seção
```html
<!-- Seção Padrão -->
<section class="section">
    <div class="container">
        <h2 class="section-title">Título</h2>
        <p class="section-subtitle">Subtítulo</p>
        <!-- conteúdo -->
    </div>
</section>

<!-- Seção com Fundo Alternativo -->
<section class="section section--alt-bg">
    <!-- conteúdo -->
</section>

<!-- Título Claro (para fundos escuros) -->
<h2 class="section-title section-title--light">Título</h2>
```

---

## ✨ Efeitos e Estados

### Hover em Cards
```css
.card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-lg);
}
```

### Hover em Botões
```css
.btn--primary:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-lg);
}
```

### Focus em Inputs
```css
.form__input:focus {
    border-color: var(--color-primary);
    box-shadow: var(--shadow-focus);
}
```

---

## 📋 Checklist de Novo Componente

Ao criar um novo componente, certifique-se de:

- [ ] Usar nomenclatura BEM
- [ ] Utilizar design tokens (variáveis CSS)
- [ ] Adicionar estados de hover/focus/active
- [ ] Garantir responsividade
- [ ] Testar em todos os breakpoints
- [ ] Adicionar comentários descritivos
- [ ] Documentar no guia de estilos
- [ ] Verificar acessibilidade
- [ ] Usar transições suaves
- [ ] Manter especificidade baixa

---

## 🚫 Evitar

❌ **NÃO** usar IDs para estilos
```css
/* Evite */
#meu-elemento { ... }
```

❌ **NÃO** criar seletores muito específicos
```css
/* Evite */
.header .nav ul li a { ... }
```

❌ **NÃO** usar valores mágicos (hardcoded)
```css
/* Evite */
margin: 23px;
color: #abc123;

/* Use */
margin: var(--spacing-md);
color: var(--color-primary);
```

❌ **NÃO** usar `!important` desnecessariamente

---

## ✅ Boas Práticas

✅ Use classes BEM semânticas
✅ Utilize design tokens
✅ Mantenha especificidade baixa
✅ Agrupe propriedades relacionadas
✅ Comente seções complexas
✅ Mobile-first approach
✅ Use unidades relativas (rem, em, %, vw, vh)
✅ Otimize para performance
✅ Pense em reutilização
✅ Teste acessibilidade

---

## 📖 Exemplos Práticos

### Criando Nova Seção
```html
<section class="servicos-premium section">
    <div class="container">
        <h2 class="section-title">Serviços Premium</h2>
        <p class="section-subtitle">Os melhores serviços</p>
        <div class="servicos-premium__grid">
            <article class="card card--centered">
                <!-- conteúdo -->
            </article>
        </div>
    </div>
</section>
```

```css
.servicos-premium__grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-md);
}
```

### Modificando Componente Existente
```css
/* Variação de botão secundário */
.btn--secondary {
    background: var(--color-secondary);
    color: var(--color-bg-primary);
}

/* Variação de card com borda */
.card--outlined {
    border: 2px solid var(--color-primary);
    box-shadow: none;
}
```

---

## 🎓 Recursos para Aprendizado

- [BEM Methodology](http://getbem.com/)
- [CSS Custom Properties](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Using_CSS_custom_properties)
- [Modern CSS Solutions](https://moderncss.dev/)
- [CSS Tricks](https://css-tricks.com/)

---

**Última atualização:** Janeiro 2026  
**Mantido por:** Equipe de Desenvolvimento
