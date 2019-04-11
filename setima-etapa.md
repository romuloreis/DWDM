# Página Testemunhos/Depoimentos/Relatos

Nesta seção iremos apresentar o depoimento de algumas pessoas atendidas pelo Saúde no Prato, 
juntamente com uma linda foto de fundo e uma de rosto para cada testemunho.

![Image_of_testemunials](https://github.com/romuloreis/DWDM/blob/master/assets/cities.png)
Imagem de como é a seção depoimentos da nossa página.

**Conteúdo que iremos abordar:**

  - Revisão do conteúdo abordado até o momento.

## Criando a Seção Testemunho (_section-testimonials_)

Primeiramente vamos criar uma nova seção com a classe (_section-testimonials_), logo após a seção _section-cities_ 

```html
    <!--Abrindo a seção testemunhos -->
    <section class="section-testimonials">

    <!--Fechando a seção testemunhos -->
    </section>
```

Agora vamos organizar a estrutura dessa seção. Teremos duas _div_ da classe _row_, sendo uma abaixo da outra
(não é uma dentro da outra), conforme ilustrado no trecho de código abaixo.

```html
    <section class="section-testimonials">
        <div class="row">
            <!-- Aqui irá o título da primeira div -->
        </div>
        <div class="row">
            <!-- Aqui irá o conteúdo da segunda div -->
        </div>
    </section>
```

Vamos começar pela primeira _div_ da classe _row_, onde iremos incluir o título da seção.

```html
    <section class="section-testimonials">
        <div class="row">
           <!-- Aqui irá o título da primeira div -->
           <h2>Melhorando a qualidade de vida das pessoas</h2>
        </div>
        <div class="row">
            <!-- Aqui irá o conteúdo da segunda div -->
        </div>
    </section>
```

Após inserir o título da seção na primeira _div_ da classe _row_, nós vamos começar a incluir o conteúdo da segunda _div_ da mesma
classe. Como ilustrado na imagem do topo desta página, o conteúdo da segunda _div_ será organizado em 3 colunas, sendo assim, vamos 
adicionar essas colunas. Para isso, basta adicionar 3 containers _div_ com a classe _col_ _span-1-of-3_ _box_, sendo que os dois 
primeiros nomes de classe são definidos no arquivo grid.css, já o terceiro nome de classe nós adicionamos, para poder criar uma 
regra/seletor em CSS, que impacte apenas nas colunas desta seção.

```html
        <div class="row">
            <!-- Aqui irá o conteúdo da segunda div, organizado em 3 colunas -->
            <div class="col span-1-of-3 box">
               <!--Primeira coluna -->
            </div>
            <div class="col span-1-of-3 box">
               <!--Segunda coluna -->
            </div>
            <div class="col span-1-of-3 box">
               <!--Terceira coluna -->
            </div>
        </div>
```
