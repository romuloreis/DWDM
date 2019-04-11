# Página Testemunhos/Depoimentos/Relatos

Nesta seção iremos apresentar o depoimento de algumas pessoas atendidas pelo Saúde no Prato, 
juntamente com uma linda foto de fundo e uma de rosto para cada testemunho.

![Image_of_testemunials](https://github.com/romuloreis/DWDM/blob/master/assets/cities.png)
Imagem de como é a seção depoimentos da nossa página.

**Conteúdo que iremos abordar:**

  - Revisão do conteúdo abordado até o momento.
  - Revisar as tags _blockquote_, _cite_

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

Dentro de cada coluna, haverá o texto de depoimento de um cliente, como é uma citação direta (exatamente o que alguém falou), nós devemos por esse texto dentro da tag _blockquote_ e ainda dentro deste, usar a tag _cite_ para citar a autor/fonte do texto.

  > O Elemento HTML [*_blockquote_*](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/blockquote) (ou Elemento HTML de citação de bloco) indica que o texto incluído é uma longa citação. Normalmente, este é processado visualmente pelo recuo (ver Notas sobre como mudá-lo). A URL para a fonte da citação pode ser dada usando o ATRIBUTO cite, enquanto uma representação de texto da fonte pode ser dada usando o ELEMENTO *_cite_*.
  
  > O elemento HTML [*_cite_*](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/cite) representa uma referência a um trabalho artístico. Deve incluir o título do trabalho ou uma URL de referência, que pode ser em uma forma abreviada de acordo com as convenções usadas para a adição dos metadados de citação.


```html
<div class="row">
            <!-- Aqui irá o conteúdo da segunda div, organizado em 3 colunas -->
            <div class="col span-1-of-3 box">
                <!--Primeira coluna -->
                <blockquote>
                    Saúde no prato é incrível! Eu sou uma pessoa super ocupada, com pouco tempo para cuidar da 
                  minha alimentação, mas tudo mudou com a equipe da saúde no prato que assumiu essa função.
                    <cite>
                        Alberto Saltonetto
                    </cite>
                </blockquote>
            </div>
            <div class="col span-1-of-3 box">
                <!--Segunda coluna -->
                <blockquote>
                    Comida saúdavel rapidinho na porta da sua casa! A melhor opção para mim e para vc... 
                  principalmente para mim que odeio cozinhar e que já perdi três casas após incendia-las 
                  tentando cozinhar.
                    <cite>
                        Joicelaine Carneiro
                    </cite>
                </blockquote>
            </div>
            <div class="col span-1-of-3 box">
                <!--Terceira coluna -->
                <blockquote>
                    Eu estava procurando por uma alimentação saudável e que coubesse no meu bolso e encontrei... 
                  Saúde no Prato, melhor custo-benefício ever! Muito mais que alvace, eles tem rúcula e 
                  repolho também!
                    <cite>
                        Pedro Antunes
                    </cite>
                </blockquote>
            </div>
        </div>
```
Agora vamos acrescentar a imagem de rosto do autor do depoimento. Então, utilizando o elemento _img_ adicione uma imagem ao lado 
do nome do autor. Para evitar problemas, procure baixar imagens (ou editar) com o valor de largura e altura iguais, pois vamos 
transformar essa imagem em um circulo perfeito. Não esqueça que essas imagens devem ser copiadas para o diretório /resources/img/

```html
            <div class="col span-1-of-3 box">
                <!-- coluna de depoimento -->
                <blockquote>
                    Eu estava procurando por uma alimentação saudável e que coubesse no meu bolso e encontrei... 
                  Saúde no Prato, melhor custo-benefício ever! Muito mais que alvace, eles tem rúcula e 
                  repolho também!
                    <cite>
                        <img src="resources/img/customer-3.jpg"/>Pedro Antunes
                    </cite>
                </blockquote>
            </div>
```

## Hora de definirmos o estilo desta seção.

Antes de modificarmos nossa folha de estilo, vamos baixar uma imagem BEM GRANDE para utilizarmos como plano de fundo deesta seção. Por se tratar de uma imagem de plano de fundo, o arquivo desta imagem deve ser copiada para o diretório /resources/css/img/

Após baixar uma foto linda, maravilhosa e BEM GRANDE, abra o arquivo style.css no seu editor de texto ou IDE preferido. Vamos criar uma regra de css para adicionar uma imagem de fundo nesta seção. 

```css
/* ----------------------------------------------- */
/* Seção Testemunhos (Section Testimonials) */
/* ----------------------------------------------- */

/*Adicionando imagem de fundo na seção*/
.section-testimonials {
    background-image: url(img/background-customers.jpg);
    background-size: cover; /*preencher toda a largura da janela do navegador*/
}
```

Como você deve ter percebido, a imagem está muito clara... A seção está uma confusão por causa desse fundo chamativo. Vamos usar a mesma técnica utilizada no Hero Header. Já vamos aproveitar para modificar a cor da fonte do texto para branco, afinal o fundo ficará escuro.


```css
/*Adicionando imagem de fundo na seção*/
.section-testimonials {
    background-image: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), url(img/background-customers.jpg);
    background-size: cover; /*preencher toda a largura da janela do navegador*/
    color: #fff; /*cor da fonte*/
}
```
