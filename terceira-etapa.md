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

Vamos incluir o título e o paragráfo principal desta seção, de acordo com seu documento versão 2. No caso da página da saúde no prato, vou usar [caracteres especiais do html](https://www.w3schools.com/html/html_entities.asp), pois quero usar um híven mais comprido (mdash) entre as duas frases do título. 

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

Vamos criar uma _div_ com classe _row_ e dentro dela vamos criar uma _div_ para cada coluna. Cada coluna vai ser da classe _col_ que é definida pelo grid.css. Tabmém vamos definir a classe _span-x-of-z_ para cada coluna. Como temos 4 colunas, firaca _span-1-of-4_

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
                <h3>100% organico</h3>
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

## Icones

Precisamos encontrar um icone para cada feature. Há varios sites [como ionicons.com](https://ionicons.com/) que disponibilizam icones sob diferentes licenças.
