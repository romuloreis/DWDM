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

Baixar jquery.waypoints.min.js

Exemplo:

```js

    var waypoints = $('#handler-first').waypoint(function(direction) {
      notify(this.element.id + ' hit 25% from top of window') 
    }, {
      offset: '25%'
    })

```

