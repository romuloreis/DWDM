# Sticky Navigation

Sempre que sair da primeira seção, o menu deve desaparecer e outro tomar lugar.

Para testar, vamos atribuir a classe sticky ao elemento nav

```html

<nav class="sticky">

```

Agora vamos definir sua posição. Atribuindo o valor fixed à propriedade position. Ou seja, o elemento terá a 

```css

.sticky{
  /*Posição FIXA*/
  position: fixed;
  /*Grudado no topo*/
  top:0;
  /*Grudado na esquerda*/
  left:0;
  /*Ocupando largura total do VH*/
  width:100%;
  /*Um pouquinho de transparência*/
  background-color: rgba(255, 255,255, 0.95);
}

.sticky .main-nav li a:link,
.sticky .main-nav li a:visited {
    padding: 8px 0;
    color: #555;
}

```

```css

.sticky .main-nav {
    margin-top: 18px; /*colocar um espaçamento acima da lista para baixar ela*/
}

.sticky .logo {
    height: 50px;
    width: auto;
    float: left;
    margin: 5px 0;}

.sticky .main-nav li a:link,
.sticky .main-nav li a:visited {
    padding: 16px 0;
    color: #555;
}
```

```css
.sticky{
  /*Posição FIXA*/
  position: fixed;
  /*Grudado no topo*/
  top:0;
  /*Grudado na esquerda*/
  left:0;
  /*Ocupando largura total do VH*/
  width:100%;
  /*Um pouquinho de transparência*/
  background-color: rgba(255, 255,255, 0.95);
  box-shadow: 0 2px 2px #efefef; /*Adicionar essa linha para efeito de sombra*/
}
```


## Etapa da programação

Vamos usar [Waypoint](http://imakewebthings.com/waypoints/) para ativar um gatilho ao usar scroll e alcançar um elemento.

Baixar projeto e mover o arquivo jquery.waypoints.min.js para o diretório vendor/js

Incluir o js no documento html.


```js
/*arquivo script.js*/

/*
    var waypoints = $('#handler-first').waypoint(function(direction) {
      notify(this.element.id + ' hit 25% from top of window') 
    }, {
      offset: '25%'
    })
    
 */

```

Vamos programar que quando o scroll chegar na seção _section-features_. Primeiramente, vamos criar uma classe para usar de refência de forma exclusiva para isso, assim se o projeto sofrer alterações no futuro, o script não será afetado.

Na seção de classe _section-features_, vamos criar e adicionar mais uma classe ao elemento, seguinto o formato de nomeclatura _js--section-features_.

```html
<section class="section-features js--section-features">
```

No arquivo script.js, vamos programar 

```js
/*arquivo script.js*/

$(document).ready(function(){
  $('.js--section-features').waypoint(function(direction){
    /*direction indica a direção do scrolling: para cima, para baixo */
    /*Se estiver indo para baixao*/
    if(direction=="down"){
       /*Adicionar a classe _sticky_ ao elemento _nav_*/
       $('nav').addClass('sticky');
    }else{
        /*Se tiver indo para cima*/
       /*Remover a classe _sticky_ do elemento _nav_*/
       $('nav').removeClass('sticky');
    }
    
  });


});

/*
    var waypoints = $('#handler-first').waypoint(function(direction) {
      notify(this.element.id + ' hit 25% from top of window') 
    }, {
      offset: '25%'
    })
    
 */

```

Agora já podemos apagar a classe _sticky_ do elemento _nav_

Ainda não está perfeito, pois queremos que o menu surja um pouco antes de chegarmos à seção de features. Para isso, no arquivo script.js, vamos programar o seguinte:

```js
/*arquivo script.js*/

$(document).ready(function(){
  $('.js--section-features').waypoint(function(direction){
    /*direction indica a direção do scrolling: para cima, para baixo */
    /*Se estiver indo para baixao*/
    if(direction=="down"){
       /*Adicionar a classe _sticky_ ao elemento _nav_*/
       $('nav').addClass('sticky');
    }else{
        /*Se tiver indo para cima*/
       /*Remover a classe _sticky_ do elemento _nav_*/
       $('nav').removeClass('sticky');
    }
    
  }, {
      /*Define que o gatilho será ativado 60px antes de chegar na seção features*/
     offset: '60px;'
  });


});

/*
    var waypoints = $('#handler-first').waypoint(function(direction) {
      notify(this.element.id + ' hit 25% from top of window') 
    }, {
      offset: '25%'
    })
    
 */

```

Note que o menu de navegação está atrás da galeria. Para solucionar isso, basta usar a propriedade z-index e colocar o elemento da classe _sticky_ na frente.


```css
.sticky{
  /*Posição FIXA*/
  position: fixed;
  /*Grudado no topo*/
  top:0;
  /*Grudado na esquerda*/
  left:0;
  /*Ocupando largura total do VH*/
  width:100%;
  /*Um pouquinho de transparência*/
  background-color: rgba(255, 255,255, 0.95);
  box-shadow: 0 2px 2px #efefef; /*Adicionar essa linha para efeito de sombra*/
  z-index: 9999; /*Prioriedade máxima*/
}
```

## Suavizando o Scrolling - Botões do Hero Header

Vamos suavizar o scrolling para a seção desejada. Vamos começar pelos botões do hero header. 
Primeiramente, vamos criar classes para o uso exclusivo das funções js, tanto para os botões, quanto para as seções que iremos ser redirecionados.

```html
<a class="btn tbn-full js--scroll-to-photos" href="#">bla</a>

<a class="btn tbn-ghost js--scroll-to-testimonials" href="#">bla</a>

```

```html
<section class="section-photos js--section-photos">

```


No nosso arquivo js, vamos programar o comportamento.

```js
/*arquivo script.js*/

/*Navegaçãqo Sticky*/
$(document).ready(function(){
  $('.js--section-features').waypoint(function(direction){
    /*direction indica a direção do scrolling: para cima, para baixo */
    /*Se estiver indo para baixao*/
    if(direction=="down"){
       /*Adicionar a classe _sticky_ ao elemento _nav_*/
       $('nav').addClass('sticky');
    }else{
        /*Se tiver indo para cima*/
       /*Remover a classe _sticky_ do elemento _nav_*/
       $('nav').removeClass('sticky');
    }
    
  }, {
      /*Define que o gatilho será ativado 60px antes de chegar na seção features*/
     offset: '60px;'
  });

/*Suavização do scrolling*/

  /*Ao clicar no elemento classe js--scroll-to-testimonials,
  seleciona os elementos html e body, então chama animação de scrolling para a seção js--section-photo com velocidade de 1000ms ou seja 1s*/
   $('.js--scroll-to-testimonials').click(function(){
      $('html, body').animate({scrollTop: $('.js--section-photo').offset().top}, 1000);
   
   });

/*Agora aplique o efeito para os demais botões do hero header*/

});

```

## Suavizando o Scrolling - Botões do menu de navegação

Para suavizar o scrolling para a seção desejada, vamos usar uma dessas formas [aqui](https://css-tricks.com/snippets/jquery/smooth-scrolling/).

Se optar pela opção do JQuery, basta incluir ids nas seções  e usar ancoras como links.

$function(){}



