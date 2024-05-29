# html-css-ecommerce-flexbox
Template responsivo de um ecommerce usando HTML semântico e CSS usando FlexBox.

1. **Estrutura do HTML**: Definiremos as seções principais do nosso layout: cabeçalho, navegação superior, barra de pesquisa, conteúdo principal com produtos e navegação lateral.
2. **Estilos CSS**: Utilizaremos Flexbox para organizar o layout e garantir que ele seja responsivo. Também aplicaremos as cores e o gradiente no cabeçalho para refletir a identidade visual do Mercado Livre.

### Estrutura HTML

Vamos construir uma estrutura HTML semântica que inclui um cabeçalho, navegação superior, barra de pesquisa, conteúdo principal com produtos e um menu de navegação lateral.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mercado Livre Template</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <div class="banner"></div>
        <nav class="top-nav">
            <ul>
                <li><a href="#">Eletrônicos</a></li>
                <li><a href="#">Moda</a></li>
                <li><a href="#">Casa</a></li>
                <li><a href="#">Esportes</a></li>
                <li><a href="#">Mais categorias</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <div class="search-bar">
            <input type="text" placeholder="Buscar produtos">
            <button>Buscar</button>
        </div>
        <div class="content">
            <aside class="side-nav">
                <h2>Outros Sites</h2>
                <ul>
                    <li><a href="#">Amazon</a></li>
                    <li><a href="#">eBay</a></li>
                    <li><a href="#">AliExpress</a></li>
                    <li><a href="#">Magazine Luiza</a></li>
                </ul>
                <h2>Tópicos Relacionados</h2>
                <ul>
                    <li><a href="#">Ofertas do Dia</a></li>
                    <li><a href="#">Lançamentos</a></li>
                    <li><a href="#">Mais Vendidos</a></li>
                </ul>
            </aside>
            <section class="products">
                <article class="product">
                    <img src="https://via.placeholder.com/150" alt="Produto 1">
                    <h3>Produto 1</h3>
                    <p>Descrição do produto 1.</p>
                </article>
                <article class="product">
                    <img src="https://via.placeholder.com/150" alt="Produto 2">
                    <h3>Produto 2</h3>
                    <p>Descrição do produto 2.</p>
                </article>
                <article class="product">
                    <img src="https://via.placeholder.com/150" alt="Produto 3">
                    <h3>Produto 3</h3>
                    <p>Descrição do produto 3.</p>
                </article>
            </section>
        </div>
    </main>
</body>
</html>
```

### Estilos CSS

O CSS será responsável por estilizar os elementos, garantindo que o layout seja responsivo e visualmente agradável.

```css
/* styles.css */

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: linear-gradient(to right, #FFD700, #FFEB3B);
    padding: 1rem;
    text-align: center;
    color: white;
}

.top-nav ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
}

.top-nav li {
    margin: 0 1rem;
}

.top-nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.search-bar {
    display: flex;
    justify-content: center;
    margin: 1rem 0;
}

.search-bar input {
    padding: 0.5rem;
    width: 50%;
    max-width: 300px;
}

.search-bar button {
    padding: 0.5rem;
    background-color: #FFD700;
    border: none;
    cursor: pointer;
}

.content {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 1rem;
}

.side-nav {
    flex: 1 1 20%;
    max-width: 300px;
    margin-right: 1rem;
}

.side-nav h2 {
    margin-top: 0;
}

.side-nav ul {
    list-style-type: none;
    padding: 0;
}

.side-nav li {
    margin-bottom: 0.5rem;
}

.side-nav a {
    text-decoration: none;
    color: #333;
}

.products {
    flex: 1 1 75%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.product {
    border: 1px solid #ddd;
    padding: 1rem;
    margin: 0.5rem;
    text-align: center;
    flex: 1 1 calc(33% - 2rem);
    box-sizing: border-box;
}

.product img {
    max-width: 100%;
    height: auto;
}

@media (max-width: 768px) {
    .products {
        flex-direction: column;
    }
    
    .product {
        flex: 1 1 100%;
    }
}
```

### Explicação do Código

1. **HTML**:
   - Utilizamos tags semânticas como `<header>`, `<nav>`, `<main>`, `<aside>`, `<section>`, `<article>`.
   - O `<header>` contém um banner com um gradiente e uma navegação superior com categorias de produtos.
   - O `<main>` inclui uma barra de pesquisa e a estrutura principal dividida em navegação lateral e seção de produtos.
   - A navegação lateral (`<aside>`) inclui links para outros sites e tópicos relacionados.
   - A seção de produtos (`<section>`) contém vários artigos representando produtos.

2. **CSS**:
   - Definimos um estilo básico para o corpo (`body`) com uma fonte padrão e sem margens.
   - O cabeçalho tem um fundo com gradiente nas cores do Mercado Livre.
   - A navegação superior (`.top-nav`) é um flex container que alinha os itens centralmente.
   - A barra de pesquisa (`.search-bar`) está centrada com flexbox.
   - A estrutura principal (`.content`) utiliza flexbox para layout responsivo.
   - A navegação lateral (`.side-nav`) ocupa 20% da largura, enquanto a seção de produtos (`.products`) ocupa 75%.
   - Utilizamos media queries para garantir que os produtos fiquem em uma única coluna em telas menores.

Essa abordagem garante um layout responsivo, que se adapta bem a diferentes tamanhos de tela, mantendo uma aparência moderna e funcional.