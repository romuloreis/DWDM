# Menu de navegação Responsivo

Quando o viewport tiver uma largura menor, o menu será substituído por um ícone. 
Ao clicar neste ícone, será mostrado um menu vertical e o ícone será alterado por outro.

## Estilizando o novo menu
Vamos seguir um fluxo de passos similar aos passos executados para deixar o menu sticky
Primeiramente vamos criar uma classe e atribuir ela de forma estática ao menu _nav_, assim podemos
estilizar nosso menu, deixando ele com a aparencia desejada. Após isso, vamos 

Vamos utilizar media query para aplicar a aparencia desejada (conjunto de regras desejada) somente 
quando o viewport estiver menor. Ou seja, em telas menores. Depois vamos utilizar JQuery para alterar o ícone.

No documento html, vamos criar um link logo após fechar o elemento _ul_, que é a lista não ordenada que utilizamos para o menu.

 ```html
    <ul>
      <!--itens do menu menus-->
    </ul>

    <a class="mobile-nav-icon js--nav-icon" href="#" ><ion-icon name="menu" class="ion-navicon-round"></ion-icon></a>

  <!--Fechamento do elemento div de classe row que está dentro do elemento nav-->
  </div>
```


No nosso arquivo de folha de estilo padrão style.css vamos criar a regra  _mobile-nav-icon_ antes 
do conjunto de regras do menu _sticky_. 
Ao não declarar o atributo _href_ no elemento _a_, o navegador será tratado como um elemento gráfico qualquer, sem alterar 
o ponteiro do mouse quando o mesmo passar por cima desse elemento no navegador. Para resolver isso, 
vamos definir o valor da propriedade [_cursor_](https://www.w3schools.com/cssref/pr_class_cursor.asp) como _pointer_.


```css
/*Mobile Nav*/
.mobile-nav-icon{
  float:right;
  margin-top: 30px;
  /*altera o cursor do mouse*/
  cursor:pointer; 
}

```

Teste e verifique nosso pequeno container. Como nosso projeto seguiu a abordagem Desktop-First, 
vamos definir que por padrão (que é tela grande), não será mostrado esse menu.


```css
/*Mobile Nav*/
.mobile-nav-icon{
  float:right;
  margin-top: 30px;
  /*altera o cursor do mouse*/
  cursor:pointer; 
  /*Não mostra o conteúdo html deste seletor*/
  display:none;
}

```

Agora vamos ajustar o estilo do ícone deste menu

```css
.mobile-nav-icon i{
  font-size: 200%;
  color: #fff;
}

```

No nossa folha de estilho das media queries, vamos **comentar o seletor _.main-nav_ que esconde o menu**. Após isso, vamos criar 
um seletor para mostrar o menu responsivo

```css
@media only screen and (max-width: 767px){
  
  /*Seletores criados anteriormente ou já existentes*/

  /*Comentar a seguinte regra desta media query*/
  /*.main-nav{
    /*Não mostra o conteúdo html deste seletor*/
    display:none;
  }*/
  
  /*Mostra o menu responsivo, que antes estava escondido/oculto*/
  .mobile-nav-icon{
    display:inline-block;
  }
  
}
```

Verifique no navegador como está ficando a interface.
Na mesma query, vamos jogar esse menu para a esquerda e deixar o menu na vertical.
Além disso, vamos definir a borda como 0, afinal, em dispositivos móveis não tem como ativar o hover.

```css
@media only screen and (max-width: 767px){
   
   /*Seletores criados anteriormente ou já existentes*/
  
  /*Mostra o menu responsivo, que antes estava escondido/oculto*/
  .mobile-nav-icon{
    display:inline-block;
  }
  
  .main-nav{
    float:left;
  }
  
  .main-nav li{
    /*um item por linha*/
    display:block;
  }
  
  .main-nav li a:visited,
  .main-nav li a:link{
    /*um item por linha*/
    display:block;
    border: 0;
  }
  
}
```

Verifique no navegador como está ficando a interface.
Tanto o menu está muito afastado da margem superior quanto seus elementos estão muito afastados uns dos outros. Sendo assim, vamos ajustar as próximidades desses elementos por meio das propriedades _margin_ e _padding_. Além disso, vamos aumentar a fonte.



```css
@media only screen and (max-width: 767px){

  /*Seletores criados anteriormente ou já existentes*/
  
  .main-nav{
    float:left;
    margin-top: 25px;/*no style.css está como 55px*/
    margin-left: 35px;
  }
   
  .main-nav li a:visited,
  .main-nav li a:link{
    /*um item por linha*/
    display:block;
    border: 0;
    padding: 10px 0; /*top, bottom, left, right*/
    font-size: 100%
  }
  
}

```

Verifique no navegador como está ficando a interface e acesse as demais seções. Vamos ajustar agora o menu de navegação sticky, incluindo a alteração da cor do ícone.

```css
@media only screen and (max-width: 767px){

  /*Seletores criados anteriormente ou já existentes*/
  
  .sticky .main-nav { margin-top: 10px; }

  .sticky .main-nav li a:link,
  .sticky .main-nav li a:visited {
      padding: 10px 0;
  }

  .sticky .mobile-nav-icon i {
    margin-top: 10px;
  }

  .sticky .mobile-nav-icon i {
    color: #555;
  }

}
```

Concluída a formatação, vamos para o JQuery. Primeiramente, seguindo as boas práticas, no arquivo html, 
vamos criar uma classe apenas para interação com código JavaScript, conforme o trecho de código a seguir:

```html
    <ul class="main-nav js--main-nav">
        <!--Elementos da lista do menu-->
    </ul>
    <a class="mobile-nav-icon js--nav-icon" href="#" ><ion-icon name="menu" class="ion-navicon-round"></ion-icon></a>
```

No arquivo de scripts, vamos usar variáveis do tipo _var_ para armazenar seleções que iremos reutilizar. Evitando repetição de código.
O método _slideToggle(tempo_duração_ms)_ serve para abrir e fechar boxes.

Como os ícones são modificados pelo nome da classe, basta mudar o nome da mesma para alterar o ícone.


```js
/* Mobile navigation */
    $('.js--nav-icon').click(function() {
        var nav = $('.js--main-nav');
        var icon = $('.js--nav-icon i');
        
        nav.slideToggle(200);
        
        if (icon.hasClass('ion-navicon-round')) {
            icon.addClass('ion-close-round');
            icon.removeClass('ion-navicon-round');
        } else {
            icon.addClass('ion-navicon-round');
            icon.removeClass('ion-close-round');
        }        
    });

```
