# Dicas para suportar multiplos navegadores

![Image of browsers](https://github.com/romuloreis/DWDM/blob/master/assets/browsers.png)

## Ah, Navegaodres...

Em um mundo ideal, todos os navegadores interpretam os códigos HTML e CSS da mesma forma.
Porém, **mudo ideal != mundo real.**
Na prática, todos os navegadores interpretam os códigos HTML e CSS de forma SIMILAR (diferente), ou seja, 
seu site vai parecer diferente dependendo do navegador usado.

## CSS browser Prefixes (Sistema de Prefixo do CSS)
Para o CSS3 funcionar em diferentes navegadores de forma correta, é necessário pré-fixar algumas propriedades do CSS3. 
Esses prefixos dão aos navegadores uma forma de suportar novas propriedades do CSS, normalmente usados para período de testes.
Para saber mais sobre esse assunto, clique [aqui](https://developer.mozilla.org/pt-BR/docs/Glossario/Prefixos_vendor)

### Prefixos

![Image of css_browsers_prefixes](https://github.com/romuloreis/DWDM/blob/master/assets/cssbrowsersprefixes.png)
 
 
 **Em texto para facilitar o copy & paste**
 
-webkit- (Chrome, Safari, versões mais recentes do Opera.)

-moz- (Firefox)

-o- (Versões antigas do Opera)

-ms- (Internet Explorer)



## Bora adicionar na mão?

Em quais propriedades usar? [Can I use?](https://caniuse.com/)

[Sublime Autoprefixer](https://github.com/sindresorhus/sublime-autoprefixer)

## E os velinhos?

Para os navegadores antigos entender/suportarem Media Query https://www.jsdelivr.com/package/npm/respond.js?path=cross-domain

```html
<script src="https://cdn.jsdelivr.net/npm/respond.js@1.4.2/cross-domain/respond.proxy.min.js"></script>
```

Suporte à HTML5 sectioning tags para navegadores existentes antes do HTML5 (Internet Explorer 6-9, Safari 4.x (iPhone 3.x), e Firefox 3.x.)  https://www.jsdelivr.com/package/npm/html5shiv

```html
<script src="https://cdn.jsdelivr.net/npm/html5shiv@3.7.3/dist/html5shiv.min.js"></script>
```

 Emula pseudo-classes (ex. lastchild) do CSS3 no IE 6-8 https://www.jsdelivr.com/package/npm/selectivizr2

```html
<script src="https://cdn.jsdelivr.net/npm/selectivizr2@1.0.9/selectivizr2.min.js"></script>
```

Baixe e referêncie após fechar a tag body... ou antes de fechar a tag body (neste casso carrega toda a página para depois os plugins)

## JQuery = biblioteca JavaScript

[Sempre disponível](https://developers.google.com/speed/libraries/#jquery)

**Plugins**

[Magnific Popup](https://dimsemenov.com/plugins/magnific-popup/) is a responsive lightbox & dialog script with focus on performance and providing best experience for user with any device
(for jQuery or Zepto.js).

[Tool Tipster](https://iamceege.github.io/tooltipster/) is a flexible and extensible jQuery plugin for modern tooltips.
Simple enough for everyone, powerful enough for everything.

Google Maps easy [First](https://github.com/danielemoraschi/maplace.js/) [Second](https://www.npmjs.com/package/maplace-js)

[Typerjs](https://steven.codes/typerjs/)

[One Page Design](http://www.thepetedesign.com/demos/onepage_scroll_demo.html)


myscript.js

```js
$(document).ready(function(){
  $('h1').click(function(){
    $(this).css('background-color','black');
  })
});

```

```html
<script src="js/myscript.js"></script>
```

