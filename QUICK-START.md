# ⚡ Quick Start - SASS no Projeto

## 🚀 Comandos Essenciais

```bash
# 1. Instalar dependências (primeira vez)
npm install

# 2. Desenvolvimento (watch mode)
npm run dev

# 3. Build para produção
npm run build
```

---

## 📂 Estrutura Básica

```
scss/
├── _variaveis.scss    # Cores, espaçamentos, etc
├── _mixins.scss       # Código reutilizável
├── _base.scss         # Reset e estilos base
├── _componentes.scss  # Botões, cards, forms
├── _layout.scss       # Header, sections, footer
└── estilos.scss       # Importa tudo

css/
└── estilos.css        # ← CSS compilado (não edite!)
```

---

## ✏️ Como Editar Estilos

### ❌ NÃO edite `css/estilos.css` diretamente!

### ✅ Edite os arquivos `.scss` em `scss/`

**Exemplo:**

1. Abra `scss/_variaveis.scss`
2. Altere uma cor:
```scss
$color-primary: #ff6b6b; // Nova cor
```
3. Salve o arquivo
4. CSS compila automaticamente (se `npm run dev` está rodando)

---

## 🎨 Onde Editar O Quê

| O que você quer mudar | Arquivo |
|----------------------|---------|
| Cores, espaçamentos | `_variaveis.scss` |
| Criar mixin novo | `_mixins.scss` |
| Estilos globais | `_base.scss` |
| Botões, cards, forms | `_componentes.scss` |
| Header, sections | `_layout.scss` |

---

## 💡 Exemplos Rápidos

### Mudar Cor Primária
```scss
// Em _variaveis.scss
$color-primary: #ff6b6b; // Altere aqui
```

### Criar Novo Botão
```scss
// Em _componentes.scss
.btn-special {
    @include button-base;
    background: $color-primary;
    color: white;
}
```

### Adicionar Breakpoint
```scss
.elemento {
    font-size: 2rem;
    
    @include respond-to(mobile) {
        font-size: 1rem;
    }
}
```

---

## 🐛 Troubleshooting

### CSS não atualiza?
```bash
# Pare o watch (Ctrl+C) e rode:
npm run build
```

### Erro ao compilar?
- Verifique sintaxe SASS
- Todas chaves `{}` fechadas?
- Variáveis existem?

### Estilos não aparecem?
- HTML aponta para `css/estilos.css`?
- Limpe cache do navegador (Ctrl+F5)

---

## 📱 Abrir Projeto

1. Abra terminal na pasta do projeto
2. Execute: `npm run dev`
3. Abra `index.html` no navegador
4. Edite arquivos `.scss`
5. Salve e atualize navegador

---

## 🎯 Fluxo de Trabalho

```
1. Edite .scss → 2. Salve → 3. SASS compila → 4. Atualize browser
```

**Dica:** Mantenha o terminal com `npm run dev` aberto enquanto desenvolve!

---

## 📚 Documentação Completa

- `README.md` - Visão geral completa
- `GUIA-SASS.md` - Tutorial detalhado de SASS
- `COMPARACAO-CSS-SASS.md` - Antes vs Depois

---

**🚀 Pronto para começar!**
