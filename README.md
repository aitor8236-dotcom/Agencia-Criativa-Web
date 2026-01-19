# 🎨 Projeto Agência Criativa Web - SASS

## 📋 Sobre o Projeto

Website responsivo e moderno da Agência Criativa Web, desenvolvido com **HTML5**, **SASS/SCSS** e **JavaScript**, seguindo a metodologia **BEM** para nomenclatura de classes.

## 🚀 Tecnologias Utilizadas

- **HTML5** - Estrutura semântica
- **SASS/SCSS** - Pré-processador CSS com arquitetura modular
- **JavaScript** - Interatividade
- **Metodologia BEM** - Block, Element, Modifier
- **Node.js** - Compilação SASS
- **Grid & Flexbox** - Layouts responsivos

## 📁 Estrutura do Projeto

```
agencia-criativa-web/
├── scss/                      # Arquivos SASS (fonte)
│   ├── _variaveis.scss       # Variáveis e Design Tokens
│   ├── _mixins.scss          # Mixins reutilizáveis
│   ├── _base.scss            # Reset e estilos base
│   ├── _componentes.scss     # Componentes (botões, cards, forms)
│   ├── _layout.scss          # Layout (header, hero, sections, footer)
│   └── estilos.scss          # Arquivo principal (importa todos)
├── css/                       # CSS compilado (gerado)
│   └── estilos.css           # CSS final compilado do SASS
├── index.html                 # Página principal
├── package.json               # Configurações Node.js
└── README.md                  # Esta documentação
```

## 🛠️ Instalação e Configuração

### Pré-requisitos

- **Node.js** (versão 14 ou superior)
- **npm** (gerenciador de pacotes)

### Passos de Instalação

1. **Clone ou baixe o projeto**

2. **Instale as dependências:**
```bash
npm install
```

## 🎯 Scripts Disponíveis

### Desenvolvimento

```bash
# Compilar SASS uma vez
npm run sass

# Watch mode - Compila automaticamente ao salvar
npm run sass:watch

# Modo desenvolvimento (expanded)
npm run dev
```

### Produção

```bash
# Build otimizado (minificado)
npm run build
```

## 📝 Uso dos Comandos

### Para Desenvolvimento:
```bash
npm run dev
```
Este comando:
- Monitora alterações nos arquivos `.scss`
- Compila automaticamente para `css/estilos.css`
- Mantém código legível (expanded)

### Para Produção:
```bash
npm run build
```
Este comando:
- Compila e minifica o CSS
- Remove source maps
- Otimiza para deploy

## 🎨 Arquitetura SASS

### 1. **_variaveis.scss**
Contém todas as variáveis do projeto:
- Cores (primária, secundária, accent, texto, fundo)
- Tipografia (fontes, tamanhos, pesos)
- Espaçamentos (xs, sm, md, lg, xl)
- Bordas (radius)
- Transições
- Sombras
- Z-index
- Breakpoints

### 2. **_mixins.scss**
Mixins reutilizáveis:
- `flex-center` - Centralização com flexbox
- `button-base` - Botão base
- `card-base` - Card base
- `section-padding` - Padding de seções
- `section-title` - Título de seção
- `text-gradient` - Gradiente em texto
- `smooth-transition` - Transições suaves
- `responsive-grid` - Grid responsivo
- `respond-to` - Media queries
- E mais...

### 3. **_base.scss**
Estilos base e reset:
- Reset CSS
- Estilos globais (body, html)
- Classes utilitárias
- Container

### 4. **_componentes.scss**
Componentes reutilizáveis:
- `.btn` - Botões
- `.card` - Cards
- `.form` - Formulários
- `.testimonial` - Depoimentos
- `.contact-item` - Itens de contato

### 5. **_layout.scss**
Estrutura de layout:
- `.header` - Cabeçalho
- `.hero` - Banner principal
- `.about` - Sobre nós
- `.services` - Serviços
- `.testimonials` - Depoimentos
- `.contact` - Contato
- `.footer` - Rodapé

## 🎯 Metodologia BEM

### Estrutura de Nomenclatura:

```scss
// Bloco
.card { }

// Elemento (parte do bloco)
.card__title { }
.card__description { }

// Modificador (variação do bloco)
.card--centered { }
.card--glass { }
```

### Exemplos de Uso:

```html
<!-- Botão Primário -->
<button class="btn btn--primary">Clique</button>

<!-- Card Centralizado -->
<article class="card card--centered">
    <div class="card__icon">🎨</div>
    <h3 class="card__title">Título</h3>
    <p class="card__description">Descrição</p>
</article>
```

## 🔧 Variáveis SASS

### Cores:
```scss
$color-primary: #6366f1;
$color-secondary: #8b5cf6;
$color-accent: #ec4899;
```

### Espaçamentos:
```scss
$spacing-xs: 0.5rem;  // 8px
$spacing-sm: 1rem;    // 16px
$spacing-md: 2rem;    // 32px
$spacing-lg: 4rem;    // 64px
$spacing-xl: 6rem;    // 96px
```

### Breakpoints:
```scss
$breakpoint-mobile: 480px;
$breakpoint-tablet: 768px;
$breakpoint-desktop: 1024px;
$breakpoint-desktop-xl: 1400px;
```

## 💡 Exemplos de Mixins

### Usando Flexbox Center:
```scss
.elemento {
    @include flex-center(row, center, center);
}
```

### Criando Botão Customizado:
```scss
.meu-botao {
    @include button-base(1rem 2rem, 8px);
    background: $color-primary;
}
```

### Responsividade com Mixin:
```scss
.elemento {
    font-size: 1.5rem;
    
    @include respond-to(mobile) {
        font-size: 1rem;
    }
}
```

## 📱 Responsividade

O projeto é **mobile-first** e totalmente responsivo:

- **Mobile**: ≤ 480px
- **Tablet**: 481px - 768px
- **Desktop**: 769px - 1399px
- **Desktop XL**: ≥ 1400px

## ✅ Funcionalidades

- ✅ Design 100% responsivo
- ✅ Menu hambúrguer mobile
- ✅ Scroll suave entre seções
- ✅ Formulário de contato funcional
- ✅ Animações e transições suaves
- ✅ Otimizado para performance
- ✅ Código modular e escalável
- ✅ Acessibilidade (prefers-reduced-motion)

## 🚀 Deploy

Para fazer deploy do projeto:

1. Compile o CSS para produção:
```bash
npm run build
```

2. Faça upload dos seguintes arquivos:
   - `index.html`
   - `css/estilos.css`
   - Arquivos de imagem (se houver)

**Nota:** Não é necessário enviar a pasta `scss/` para produção, apenas o CSS compilado.

## 🔄 Workflow de Desenvolvimento

1. **Inicie o watch mode:**
```bash
npm run dev
```

2. **Edite os arquivos `.scss` na pasta `scss/`**

3. **O SASS compila automaticamente para `css/estilos.css`**

4. **Visualize as mudanças no navegador**

5. **Antes do deploy, execute:**
```bash
npm run build
```

## 📚 Recursos Adicionais

- [Documentação SASS](https://sass-lang.com/)
- [Metodologia BEM](http://getbem.com/)
- [CSS Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

## 👨‍💻 Autor

**Agência Criativa Web**  
Design Digital e Desenvolvimento Web de Excelência

## 📄 Licença

Este projeto está sob a licença MIT.

---

**Desenvolvido com 💜 usando SASS**
