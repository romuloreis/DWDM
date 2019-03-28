# Página de Features (características/recursos/funcionalidades)
Após construir o hero header, vamos construir uma página para apresentar as principais características, recursos ou funcionalidades do nosso cliente ou do seu produto.

**Conteúdo que iremos abordar:**

  - Adicionar conteúdo direto do css com a pseudo classe _:after_
  - Fluid Grid na prática 
  - Icones
## Criando uma Section

No arquivo **index.html**, vamos adicionar uma _section_, logo após o fechamento da tag _header_. Vamos criar a classe "_section-features_" para essa seção.

```html
 <section class="section-features"></section>
```

Como queremos nosso conteúdo centralizado, vamos criar uma _div_ com a classe _row_ dentro desta seção. 

```html
  <section class="section-features">
      <div class="row">

      </div>
  </section>
```

Vamos incluir o título e o paragráfo principal desta seção, de acordo com seu documento versão 2. No caso da página da saúde no prato, vou usar [caracteres especiais do html](https://www.w3schools.com/html/html_entities.asp), pois quero usar um hífen mais comprido (mdash) entre as duas frases do título. 

```html
  <section class="section-features">
      <div class="row">
          <h2>Solução rápida e saúdavel &mdash; não apenas solução rápida.</h2>
          <p class="long-copy">
            Nós da saúde no prato queremos prover a você uma experiência incrivelmente deliciosa e saudável. 
            Pois entendemos que nem todo mundo tem tempo suficiente ou interesse em cozinhar, mas não é por 
            isso que as pessoas devem deixar de se alimentar bem.
          </p>
      </div>
  </section>
```

## Fluid Grid na prática

Terminado a parte superior da nossa seção de features, vamos inciar a parte inferior da seção, que será composto por 4 colunas. Primeiramente, vamos criar uma _div_ e definir a classe desta _div_ como _row_. Agora, dentro da _div_ _row_ vamos criar uma _div_ para cada coluna. Cada coluna (_div_) vai ser da classe _col_ que é definida pelo grid.css. Tabmém vamos definir a classe _span-x-of-z_ para cada coluna. Como temos 4 colunas, o nome da classe ficaria _span-1-of-4_.

```html
    <section class="section-features">
        <div class="row">
            <h2>Solução rápida e saúdavel &mdash; não apenas solução rápida.</h2>
            <p class="long-copy">
                Nós da saúde no prato queremos prover a você uma experiência incrivelmente deliciosa e saudável. Pois entendemos que nem todo mundo tem tempo suficiente ou interesse em cozinhar, mas não é por isso que as pessoas devem deixar de se alimentar bem.
            </p>
        </div>
        <div class="row">
            <div class="col span-1-of-4">
                <!-- Primeira coluna-->
            </div>            
            <div class="col span-1-of-4">
                <!-- Segunda coluna-->
            </div>
            <div class="col span-1-of-4">
                <!-- Terceira coluna-->
            </div>            
            <div class="col span-1-of-4">
                <!-- Quarta coluna-->
            </div>
        </div>
    </section>
```
Agora vamos colocar o conteúdo em cada coluna.


```html
        <div class="row">
            <div class="col span-1-of-4">
                <h3>Aberto 365 dias</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>Pronto em 15 min.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>100% orgânico</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>Produtos frescos</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
        </div>
```

## Ícones

Precisamos encontrar um ícone que melhor represente cada feature. Há varios sites que disponibilizam icones sob diferentes licenças. Para esse projeto vou utilizar os ícones disponibilizados no [ionicons.com](https://ionicons.com/). Para poder usá-los, basta incluir a linha de código abaixo no final do documento HTML, logo após o fechamento da tag HTML.

```html
    <!--todo o código da minha página está acima-->
  </body>
</html>
<script src="https://unpkg.com/ionicons@4.2.2/dist/ionicons.js"></script>
```

Está na hora de incluirmos nossos 4 íncones

```html
<div class="row">
    <div class="col span-1-of-4">
        <ion-icon name="infinite"></ion-icon>
        <h3>Aberto 365 dias</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="stopwatch"></ion-icon>
        <h3>Pronto em 15 min.</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="nutrition"></ion-icon>
        <h3>100% organico</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="card"></ion-icon>
        <h3>Aceitamos cartões</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
 </div>
```

## Definindo espaçamento entre as seções da nossa one-page web.

No arquivo _style.css_ vamos colocar um espaçamento entre as seções da página.

```css
section {
  padding: 80px 0;
}
```

Ainda no arquivo _style.css_, vamos agrupar as propriedades que os elementos h_n_ tem em comum e configurar o estilo de h2.

```css
h1, h2 {
    font-weight: 300;
    text-transform: uppercase;
    letter-spacing: 1px;
}

h1 {
    margin-top: 0;
    margin-bottom: 20px;
    color: #fff;
    font-size: 240%;
    word-spacing: 4px;
}

h2 {
    font-size: 180%;
    word-spacing: 2px;
    text-align: center; /*Centralizando o texto*/
    margin-bottom: 30px;
}
```

Agora vamos colocar uma pequena linha amarela entre o conteúdo de h2 e o texto abaixo dele. Para isso, usaremos a pseudo classe _:after_, a qual indica que será colocado algo após a tag em que a pseudo classe está atribuída (ex. h2:after - ocorre após a tag h2). Ao usar _:after_ é necessário colocar um valor para a propriedade _content_, neste caso, não queremos nenhum texto, então basta colocar um espaço como valor.



> Entrnda mais sobre pseudo classes [aqui](https://www.w3schools.com/css/css_pseudo_classes.asp)
> Entrnda mais sobre pseudo elementos [aqui](https://www.w3schools.com/css/css_pseudo_elements.asp)
