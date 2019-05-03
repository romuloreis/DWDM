# Tornando nosso site responsivo! Finalmente!

<details>
  <summary>Notas</summary>

Atualmente nossa página está _top_ em telas de computadores...

mas também queremos que funcione em telas de outros dispositivos... telas com diferentes tamanhos e formatos...

*Lembrando que criamos todo o site usando Fluid Grid.

*Add screenshot de como as páginas vão ficar!
Revisão de tudo: 
https://www.w3schools.com/css/css_rwd_intro.asp

http://483eclass.com/spring17/build_1/Rubi/Pages/Page3.html


**Como definir breakpoints?**

Como utilizamos a abordagem de desenvolvimento Desktop First, vamos ter que ir testando e ajustando. =/

Abra sua página original no navegador;

Vá redimensionando a janela devagar até o design parecer ruim -- se fez mobile-first, abra pequeno e vá aumentando a janela; senão, abra grande e vá diminuindo a janela;

Quando achar um ponto em que o design quebra, copie o tamanho da janela e crie uma media query com esse valor lá no seu CSS;

Recarregue a página, veja se as mudanças melhoraram o design, e continue redimensionando pra achar o próximo breakpoint.


</details>


![Image of media_queries_blog](https://github.com/romuloreis/DWDM/blob/master/assets/media-queries-blog.jpg)
Crédito da foto: [solodev.com](https://www.solodev.com/core/fileparse.php/131/urlt/media-queries-blog.jpg)



## Organizando a casa, digo... o projeto

**Criando uma nova folha de estilo e definindo breakpoints**

Por questões de organização, vamos criar uma nova folha de estilo separada, onde vamos concentrar regras dependente de media queries. 
Sendo assim, crie _queries.css_ no diretório resources\css do projeto.

**Importando a folha de estilho queries.css**

Agora temos que importar o arquivo queries.css no nosso documento html, adicionando o seguinte código dentro do elemento _head_

Vamos aproveitar também para adicionar a meta tag para viewport, importante quando trabalhamos com responsividade. Trataremos dessa tag nas próximas aulas.

```html
    <!-- Meta tag viewport, que é importante quando desenvolvemos sites responsivos, 
        pois previne que os smartphones dêem zoom out na página, ou seja, 
        sempre iniciar com escala 1.0 --> 
    <meta name="viewport" content="with=device-width, initial-scale=1.0">

    <!-- Importação do nossa folha de estilo de media queries -->
    <link rel="stylesheet" type="text/css" href="resources/css/queries.css">

```

**Definindo os breakpoints e declarando as queries**
*incluir o pq desses valores com demonstração do google dev tool - gif

Vamos definir nossos break points no arquivo _queries.css_, conforme definido abaixo. **Lembrando** que esses valores talvez não sejam adequados para a tela da sua estação de trabalho, pois dependem do tamanho, formato, resolução, etc do equipamento usado para desenvolver. 

```css
/*O valor dessa query de ser o mesmo valor da propriedade de largura máxima (width) 
da classe ROW que definimos no style.css.*/
/*Lembrando que a esse valor deveria ter sido definido com base na tela da sua estação de trabalho (workstation)*/
@media only screen and (max-width: 1200px){
	/*Telas grandes de até 1200px de largura*/
}

@media only screen and (max-width: max-width: 1023px){
	/*Pequenos e grandes tablets: largura entre 768px e 1023px*/
}

@media only screen and (max-width: max-width: 767px){
	/*Pequenos telefones até pequenos tablets: largura entre 481px e 767px*/
}

@media only screen and (max-width: max-width: 480px){
	/*Pequenos celulares: largura entre 0px e 480px*/
}

```

## Começando pelos grandes (max-width: 1200px)


Vamos começar ajustando o texto de chamada do hero header. Vamos sobre escrever a propriedade width do seletor _.hero-text-box_ do arquivo style.css, adicionando essa regra dentro da query de 1200px do arquivo queries.css. Vamos usar o valor 1200, pois foi o mesmo valor definido para a classe _row_ em style.css. Lembrando que dependendo do da tela do seu workstation, esse valor pode ter sido alterado, afinal deveria ser de um tamanho em que o todo o conteúdo do header estivese em harmonia, onde o texto de chamada não tivesse enconstando em margens (turma da noite com a resolução estranho teve que mudar e o pessoal da manhã com IMAC também). 

No seletor _.hero-text-box_ vamos definir que o texto vai ocupar toda a largura do viewport, mas com um espaçamento mínimo de 2% das bordas laterais do navegador.

```css
/*Arquivo style.css*/
.hero-text-box {
    position: absolute;
    width: 1140px; /*note o tamanho fixo da largura!/*
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

```css
/*Arquivo queries.css*/
@media only screen and (max-width: 1200px){
	.hero-text-box {
	    /*vamos sobrescrever o valor dessa propriedade*/
	    /*Não queremos mais um valor fixo, queremos que seja 100% da largura da linha (_row_) definido anteriormente*/
	    width: 100%; 
	   /*vamos colocar um espaçamento mínimo entre o texto e a borda do navegador*/
	   padding: 0 2%; /*topo e bottom = 0 | right e left = 2%*/
	}

}
```

Agora verifique que o logomarca da canto superior esquerdo do hero header fica "grudado" à lateral do navegador quando o mesmo é menor.
Para isso, vamos definir a propriedade padding da classe _row_ (linha), assim, sempre que eu tiver um container de classe _row_, ele nunca vai encostar nas bordas do viewport. Para isso, adicione a seguinte regra dentro da media query de 1200px 


```css
/*Arquivo queries.css*/
@media only screen and (max-width: 1200px){
	
	/*Regras definidas no passo anterior devem permanecer aqui...*/
	
	.row{
		/*vamos colocar um espaçamento mínimo entre as laterais da linha (row) e a borda do navegador*/
		padding: 0 2%;/*topo e bottom = 0 | right e left = 2%*/
	}

}
```

Note que todas as linhas vão ser afetadas.


## Seguindo para os Tablets (max-width: 1023px)

Agora vamos configurar a media query para displays de tablets. Usando as ferramentas do desenvolvedor, é possível diminuir a largura do navegador e verificar o que fica estranho na página neste tamanho de tela. A primeira coisa é o tamanho da fonte que não diminuiu. 

No inicío do projeto, definimos o tamanho da fonte default para 20px, por meio da propriedade font-size do seletor _body_ do arquivo style.css. Como durante o projeto nós definimos os demais font-size com valores usando porcentagem (com base nesse _font-size_ da regra _body_), basta definir um novo valor padrão de tamanho de fonte para o body para tablets. Sendo assim, vamos adicionar a regra _body_ na media query para tamanho de tela de tablets no arquivo queries.css

Como estamos em um tela com menos espaço em um dispositivo de menor porte. Também vamos diminuir o espaçamento entre as seções.

```css
@media only screen and (max-width: 1023px){
	body{font-size: 18px;} /*Define o tamanho de fonte padrão para esse tamanho de tela*/
	section {padding: 60px 0;} /*Define um novo valor de espaçamento top e bottom entre as seções para esse tamanho de tela*/
}
```

**Seção features**

Note que com esse tamanho de tela o texto principal da seção de features ficou com um aspecto estranho, meio agromerado/comprimido. As propriedades desse texto são definidas pela classe _.long__copy_ do arquivo style.css

Vamos adicionar essa regra na media query para tamanho de tela de tablets (max-width: 1023px) no arquivo queries.css

```css

@media only screen and (max-width: 1023px){

	/*Regras definidas no passo anterior devem permanecer aqui...*/
	
	.long-copy{
		width: 80%; /*ocupa 80%, sobra 20%*/
    		margin-left: 10%; /*10% para cada lado*/
	}
}
```

**Seção lista de passos**

Na seção lista de passos, vamos ter o objetivo de minimizar o espaço em branco, ocupando melhor o espaço em tela. Para isso, vamos diminuir o espaçamento entre os textos dos passos e também dos botões para o aplicativo. Além disso vamos aumentar um pouco o tamanho da imagem do celular. 

```css
@media only screen and (max-width: 1023px){

	/*Regras definidas no passo anterior devem permanecer aqui...*/
	
	/*Precisamos minimizar espaço em branco, até pq não temos mais tanto espaço assim.*/
	.steps-box{margin-top: 10px;}
	.steps-box:last-child{margin-top: 10px;}
	.step {margin-bottom: 40px;}
	/*Ajusta apenas o espaçamento apenas do último passo. last-of-type similar ao last-child*/
	.step:last-of-type {margin-bottom: 60px;}
	.app-screen{width: 50%} /*Aumenta o tamanho da imagem*/
}
```



## Material complementar

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
