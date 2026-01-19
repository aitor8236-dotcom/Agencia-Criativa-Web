# 📘 Guia de Uso do SASS - Agência Criativa Web

## 🎯 Sobre Este Guia

Este documento explica como trabalhar com SASS no projeto da Agência Criativa Web, incluindo estrutura de arquivos, uso de variáveis, mixins e boas práticas.

---

## 📂 Estrutura de Arquivos SASS

```
scss/
├── _variaveis.scss      # Design Tokens (cores, espaçamentos, fontes)
├── _mixins.scss         # Mixins reutilizáveis
├── _base.scss           # Reset e estilos base
├── _componentes.scss    # Componentes (botões, cards, forms)
├── _layout.scss         # Layout (header, hero, sections)
└── estilos.scss         # Arquivo principal (importa tudo)
```

### 📋 Convenções de Nomenclatura

- **Partials**: Começam com `_` (underscore) - Ex: `_variaveis.scss`
- **Arquivo Principal**: Sem underscore - Ex: `estilos.scss`
- **Classes**: Metodologia BEM - Ex: `.card__title--primary`

---

## 🎨 1. Trabalhando com Variáveis

### Definindo Variáveis (em `_variaveis.scss`)

```scss
// Cores
$color-primary: #6366f1;
$color-secondary: #8b5cf6;
$color-accent: #ec4899;

// Espaçamentos
$spacing-sm: 1rem;
$spacing-md: 2rem;
$spacing-lg: 4rem;

// Bordas
$border-radius-md: 15px;
```

### Usando Variáveis

```scss
.meu-elemento {
    color: $color-primary;
    padding: $spacing-md;
    border-radius: $border-radius-md;
}
```

### ✅ Vantagens

- **Consistência**: Mesmas cores/espaçamentos em todo o site
- **Manutenção**: Alterar em um lugar atualiza tudo
- **Legibilidade**: Nomes descritivos ao invés de valores mágicos

---

## 🔧 2. Mixins - Código Reutilizável

### Mixins Disponíveis

#### `@mixin flex-center`
Centralização com flexbox

```scss
// Uso
.elemento {
    @include flex-center(row, center, center);
}

// Parâmetros:
// $direction: row | column
// $justify: flex-start | center | flex-end | space-between
// $align: flex-start | center | flex-end
```

#### `@mixin button-base`
Base para criar botões

```scss
// Uso
.meu-botao {
    @include button-base(1rem 2.5rem, 50px);
    background: $color-primary;
    color: white;
}

// Parâmetros:
// $padding: padding do botão
// $radius: border-radius
```

#### `@mixin card-base`
Base para criar cards

```scss
// Uso
.meu-card {
    @include card-base($spacing-md, $border-radius-md);
}

// Parâmetros:
// $padding: padding interno
// $radius: border-radius
```

#### `@mixin section-padding`
Padding padrão de seções

```scss
// Uso
.minha-secao {
    @include section-padding($spacing-xl, $spacing-xl);
}

// Parâmetros:
// $top: padding-top
// $bottom: padding-bottom
```

#### `@mixin responsive-grid`
Grid responsivo automático

```scss
// Uso
.grid-container {
    @include responsive-grid(300px, $spacing-md);
}

// Gera:
// display: grid;
// grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
// gap: 2rem;
```

#### `@mixin respond-to`
Media queries simplificadas

```scss
// Uso
.elemento {
    font-size: 2rem;
    
    @include respond-to(tablet) {
        font-size: 1.5rem;
    }
    
    @include respond-to(mobile) {
        font-size: 1rem;
    }
}

// Breakpoints disponíveis:
// mobile: max-width 480px
// tablet: max-width 768px
// desktop: min-width 1024px
// desktop-xl: min-width 1400px
```

#### `@mixin smooth-transition`
Transições suaves em múltiplas propriedades

```scss
// Uso
.elemento {
    @include smooth-transition(transform, opacity, background-color);
}

// Gera:
// transition: transform 0.3s ease, opacity 0.3s ease, background-color 0.3s ease;
```

---

## 🎭 3. Aninhamento (Nesting)

### ✅ Bom Aninhamento (Até 3 níveis)

```scss
.card {
    padding: $spacing-md;
    
    &__title {
        font-size: 1.5rem;
        color: $color-primary;
    }
    
    &__description {
        color: $color-text-secondary;
    }
    
    &--centered {
        text-align: center;
    }
    
    &:hover {
        transform: translateY(-5px);
    }
}
```

### ❌ Evitar Aninhamento Excessivo

```scss
// NÃO FAÇA ISSO
.header {
    .nav {
        .nav-list {
            .nav-item {
                .nav-link {
                    color: blue; // 5 níveis - muito profundo!
                }
            }
        }
    }
}

// FAÇA ISSO
.nav__link {
    color: $color-primary;
}
```

---

## 🔢 4. Operadores SASS

### Operadores Aritméticos

```scss
$base-spacing: 1rem;

.elemento {
    // Multiplicação
    padding: $base-spacing * 2; // 2rem
    
    // Divisão (use math.div ou calc)
    margin: calc($base-spacing / 2); // 0.5rem
    
    // Adição
    width: 100px + 50px; // 150px
    
    // Subtração
    height: 200px - 50px; // 150px
}
```

### Interpolação

```scss
$side: left;

.elemento {
    margin-#{$side}: 10px; // margin-left: 10px
}
```

---

## 📦 5. Criando Novos Componentes

### Passo a Passo

#### 1. Adicione em `_componentes.scss`:

```scss
// ================================================================
// NOVO COMPONENTE (BEM: .alert)
// ================================================================
.alert {
    padding: $spacing-sm $spacing-md;
    border-radius: $border-radius-sm;
    border-left: 4px solid;
    
    &__title {
        font-weight: $font-weight-bold;
        margin-bottom: calc($spacing-xs / 2);
    }
    
    &__message {
        color: $color-text-secondary;
    }
    
    &--success {
        background: #d1fae5;
        border-color: #10b981;
    }
    
    &--error {
        background: #fee2e2;
        border-color: #ef4444;
    }
    
    &--warning {
        background: #fef3c7;
        border-color: #f59e0b;
    }
}
```

#### 2. Use no HTML:

```html
<!-- Alert de Sucesso -->
<div class="alert alert--success">
    <h4 class="alert__title">Sucesso!</h4>
    <p class="alert__message">Operação concluída com êxito.</p>
</div>

<!-- Alert de Erro -->
<div class="alert alert--error">
    <h4 class="alert__title">Erro!</h4>
    <p class="alert__message">Algo deu errado.</p>
</div>
```

---

## 🎨 6. Personalizando Cores

### Adicione Novas Cores em `_variaveis.scss`:

```scss
// Adicione suas cores personalizadas
$color-success: #10b981;
$color-error: #ef4444;
$color-warning: #f59e0b;
$color-info: #3b82f6;
```

### Use nos Componentes:

```scss
.botao-sucesso {
    @include button-base;
    background: $color-success;
    color: white;
}
```

---

## 🔄 7. Workflow de Desenvolvimento

### Modo Desenvolvimento

```bash
# Terminal 1: Watch mode (compila automaticamente)
npm run dev

# Ou alternativamente
npm run sass:watch
```

**O que acontece:**
- Ao salvar qualquer arquivo `.scss`
- SASS compila automaticamente
- Gera `css/estilos.css` atualizado
- Atualize o navegador para ver as mudanças

### Comandos Disponíveis

```bash
# Compilar uma vez
npm run sass

# Watch mode (expanded - legível)
npm run dev

# Build para produção (minificado)
npm run build
```

---

## 🎯 8. Boas Práticas

### ✅ FAÇA

1. **Use variáveis para valores repetidos**
```scss
// ✅ Correto
color: $color-primary;
padding: $spacing-md;
```

2. **Use mixins para padrões repetitivos**
```scss
// ✅ Correto
.meu-grid {
    @include responsive-grid(300px);
}
```

3. **Limite aninhamento a 3 níveis**
```scss
// ✅ Correto
.card {
    &__title {
        color: $color-primary;
    }
}
```

4. **Siga BEM para nomenclatura**
```scss
// ✅ Correto
.card { }
.card__title { }
.card--featured { }
```

### ❌ EVITE

1. **Valores hardcoded**
```scss
// ❌ Errado
color: #6366f1;
padding: 32px;

// ✅ Correto
color: $color-primary;
padding: $spacing-md;
```

2. **Aninhamento excessivo**
```scss
// ❌ Errado (5 níveis)
.header .nav .list .item .link { }

// ✅ Correto
.nav__link { }
```

3. **Seletores muito específicos**
```scss
// ❌ Errado
div.container > section#about > div.content { }

// ✅ Correto
.about__content { }
```

---

## 🐛 9. Troubleshooting

### Problema: CSS não atualiza

**Solução:**
```bash
# Limpe o cache e recompile
npm run build
```

### Problema: Erro de compilação

**Verifique:**
1. Sintaxe correta do SASS
2. Todas as variáveis estão definidas
3. Imports estão corretos
4. Fechamento de chaves `{}`

### Problema: Estilos não aparecem

**Verifique:**
1. HTML aponta para `css/estilos.css`
2. Arquivo CSS foi compilado
3. Cache do navegador (Ctrl + F5)

---

## 📚 10. Recursos Adicionais

### Documentação Oficial
- [SASS Documentation](https://sass-lang.com/documentation)
- [SASS Guidelines](https://sass-guidelin.es/)

### Tutoriais
- [SASS Basics](https://sass-lang.com/guide)
- [BEM Methodology](http://getbem.com/)

---

## 💡 11. Exemplos Práticos

### Exemplo 1: Criando Botão Customizado

```scss
// Em _componentes.scss
.btn-custom {
    @include button-base(1rem 2rem, 8px);
    background: linear-gradient(135deg, $color-primary, $color-secondary);
    color: white;
    font-size: 1rem;
    
    &:hover {
        transform: translateY(-3px) scale(1.05);
        box-shadow: $shadow-lg;
    }
    
    @include respond-to(mobile) {
        font-size: 0.875rem;
        padding: 0.75rem 1.5rem;
    }
}
```

### Exemplo 2: Card com Gradiente

```scss
// Em _componentes.scss
.card-premium {
    @include card-base;
    background: linear-gradient(135deg, $color-primary, $color-accent);
    color: white;
    
    .card__title {
        color: white;
    }
    
    &:hover {
        transform: translateY(-10px) rotate(2deg);
    }
}
```

### Exemplo 3: Seção com Fundo Animado

```scss
// Em _layout.scss
.secao-especial {
    @include section-padding;
    position: relative;
    overflow: hidden;
    
    &::before {
        content: '';
        position: absolute;
        inset: 0;
        background: linear-gradient(45deg, 
            rgba($color-primary, 0.1) 0%, 
            rgba($color-accent, 0.1) 100%);
        animation: gradient-shift 10s ease infinite;
    }
}

@keyframes gradient-shift {
    0%, 100% { transform: translateX(0); }
    50% { transform: translateX(20px); }
}
```

---

**Desenvolvido com 💜 usando SASS**  
**Última atualização:** Janeiro 2026
