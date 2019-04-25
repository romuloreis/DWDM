Notas

Atualmente nossa página está _top_ em telas de computadores...

mas também queremos que funcione em telas de outros dispositivos... telas com diferentes tamanhos e formatos...

*Lembrando que criamos todo o site usando Fluid Grid.

*Add screenshot de como as páginas vão ficar!


![Image of media_queries_blog](https://github.com/romuloreis/DWDM/blob/master/assets/media-queries-blog.jpg)
Crédito da foto: [solodev.com](https://www.solodev.com/core/fileparse.php/131/urlt/media-queries-blog.jpg)

 - Exemplo de váririas organizações de conteúdos em diferentes telas [mediaqueri.es](https://mediaqueri.es/)
 - [Introdução à Media Queries](https://tableless.com.br/introducao-sobre-media-queries/)
 - [Resoluções e Media Queries](https://www.chiefofdesign.com.br/media-queries-css-introducao-a-diferentes-resolucoes-de-tela/)
 - [Como Definir seus breakpoints](http://gs.statcounter.com/#desktop+mobile+tablet-resolution-ww-monthly-201608-201610-bar)
 - [Exemplo de css modelo](https://www.onlinedesignteacher.com/2015/01/css3-media-queries-for-responsive_81.html)
 - [Melhores práticas](https://www.solodev.com/blog/web-design/media-queries-and-mobile-css-best-practices.stml)
 - [Super Dica - Testes](https://codepen.io/ericrasch/pen/HzoEx)

Menos didáticos
 - [Usando Media Queries](https://developer.mozilla.org/pt-BR/docs/Web/Guide/CSS/CSS_Media_queries)
 - [W3CSchool - Media Querie](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)
 
 Avançado
- [Recomendo a leitura](http://bradfrost.com/blog/post/7-habits-of-highly-effective-media-queries/)
- [Introduction mobile first media queries](https://www.sitepoint.com/introduction-mobile-first-media-queries/)

Revisão de tudo: 
https://www.w3schools.com/css/css_rwd_intro.asp

http://483eclass.com/spring17/build_1/Rubi/Pages/Page3.html


Mais notas:
Criar queries.css na pasta css

Definindo os breakpoints e declarando as queries

```css
@media only screen and (max-width: max-width: 1200px){
/*Deve ser o mesmo valor da classe ROW que definimos no style.css*/
/*Big Tablets*/
}

@media only screen and (max-width: max-width: 1023px){
/*small tablets to big tablets*/

}

@media only screen and (max-width: max-width: 767px){
	/*lass or equal 767 (menores que ipad) - small phones to small tablets (from 481px to 767px)*/

}

@media only screen and (max-width: max-width: 480px){
	/*lass or equal 480 - small phones*/

}

```

Agora temos que importar o arquivo queries.css no nosso documento html, adicionando o seguinte código dentro do elemento _head_

Vamos aproveitar também para adicionar a meta tag para viewpor, importante quando trabalhamos com responsividade. Trataremos dessa tag nas próximas aulas.

```html
    <!-- Meta tag viewport, que é importante quando desenvolvemos sites responsivos, 
        pois previne que os smartphones dêem zoom out na página, ou seja, 
        sempre iniciar com escala 1.0 --> 
    <meta name="viewport" content="with=device-width, initial-scale=1.0">

    <!-- Importação do nossa folha de estilo de media queries -->
    <link rel="stylesheet" type="text/css" href="resources/css/queries.css">

```

Como utilizamos a abordagem de desenvolvimento Desktop First, vamos ter que ir testando e ajustando. =/

