# Revisão Geral Display Grid

## Básico (Primeira página)

Primeiramente vamos criar o documento **index1.html** e estrurar nossa primeira página.

A _div grid-container_ será nosso container GRID e cada _div_ dentro desse container será um item do GRID.

```html
<!DOCTYPE html>
<html>
<head>
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css" href="css/index1.css">
	<title>Grid System</title>
</head>
<body>
	<div class="grid-container">
		<div>Lorem</div>
		<div>Lorem</div>
	</div>
</body>
</html>
```

Antes de começar a trabalhar com Grid vamos criar o arquivo **index1.css** com as seguintes propriedades básicas:

```css
/*Define cor de fundo e padding apenas para as div que são diretamente filhas da classe grid-container*/
.grid-container > div{
	background: #eee;
	padding: 1em;

}

/*Define cor de fundo diferente apenas para as div "ímpares" 
que são diretamente filhas da classe grid-container*/
.grid-container > div:nth-child(odd){
	background: #ddd;
}
```

Agora vamos definir que o container de classe _grid-container_ 
vai se comportar como um container GRID, por meio da propriedade display.
Também vamos definir que nosso grid container terá duas colunas, 
a primeira coluna ocupa 70% da largura e a segunda coluna ocupa 30% de largura.

```css
.grid-container {
	/*Define que esse elemento é um container GRID*/
	display: grid;
	grid-template-columns: 70% 30%;
}

/*Demais regras criadas anteriormente*/
```
Por padrão essas colunas terão essas larguras idependente de quantas linhas nossa grid terá. 

Não precisamos definir o número de linhas do grid. Por padrão número de linhas depende de número de itens do grid. 

```html
<div class="grid-container">
	<div>Lorem</div>
	<div>Lorem</div>
	<div>Lorem</div>
	<div>Lorem</div>
</div>
```

Para ajustar os espaçamentos entre os as colunas e linhas do container **NÃO** usamos as propriedades _margin padding_.

Quando trabalhamos com GRID usamos as propriedades relativas ao _gap_ entre as linhas e colunas.


```css
.grid-container {
	/*Define que esse elemento é um container GRID*/
	display: grid;
	grid-template-columns: 70% 30%;
	
	/*Define espaçamento entre colunas
	grid-column-gap: 1em;
	Define espaçamento entre linhas
	grid-row-gap: 1em;*/
	/*Define espaçamento entre ambos*/
	grid-gap: 1em;

}
```

Pronto, já sabemos o básico de GRID.


## Básico (Segunda página)

Agora vamos criar o documento **index2.html** e **index2.css** e estrurar nossa primeira página e estilo básico.

```html
<body>
	<div class="grid-container">
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
	</div>
</body>
```


```css
.grid-container > div{
	background: #eee;
	padding: 1em;

}

.grid-container > div:nth-child(odd){
	background: #ddd;
}
```
### Colunas, unidade fr e função repeat

É recomendável usarmos a unidade _fr_ ao trabalhar com as larguras do grid. 
Isso vai evitar problemas com margins e paddins, principalmente quando começamos 
a trabalhar com elementos alinhados (nested).

```css
.grid-container {
	/*Define que esse elemento é um container GRID*/
	display: grid;
	/*Define quantidade de colunas e suas larguras
	grid-template-columns: 1fr 1fr 1fr;*/
	grid-template-columns: 1fr 2fr 1fr;
	
	/*Define espaçamento entre ambos... linhas e colunas*/
	grid-gap: 1em;
}
```

Também podemos usar a função _repeat_ para definir a quantidade de colunas e suas larguras:

	- O primeiro argumento da função é a quantidade de colunas.
	- O segundo argumento da função são as largura das colunas.
		- use espaço para separar as larguras.

```css
	/*Defição de largura única*/
	grid-template-columns: repeat(4, 1fr);
	
	/*Defição de largura múltipla*/
	grid-template-columns: repeat(4, 1fr 2fr 1fr);
```

### Altura e função minmax

Podemos definir a altura das linhas do grid por meio da propriedade _grid-auto-rows_

#### Unidade absoluta

Podemos definir a altura para diferentes linhas

```css
	/*Define altura das 2 primeiras linhas do grid*/
	/*a autura das demais linhas vão ser automáticas*/
	grid-template-rows: 50px 50px;
```

Ao usar unidade absoluta para definir a altura, o conteúdo pode violar a altura, pois a altura é absoluta*

```css
	/*Define altura das linhas do grid*/
	/*unidade absoluta vaza conteúdo, mas a altura é absoluta*/
	grid-auto-rows: 100px;
```

#### Função minmax

Uma opção para corrigir isso é usar a função _minmax_:
	- O primeiro argumento da função é a altura mínima da linha.
	- O segundo argumento da função são as largura máxima da linha.

```css
	grid-auto-rows: minmax(100px, auto);
```


**Também podemos ter os seguintes contextos:**

```css
	grid-template-columns: repeat(3, 1fr);
	/*Define altura das linhas do grid*/
	grid-template-rows: repeat(2, 100px);
```

```css
	/*primeiro atributo é em relação à linha, o segundo é em relação à coluna*/
	grid-template: repeat(2, 100px) / repeat(3, 1fr);
```

### Nested Grids ou Subgrids 

Agora vamos criar um grid container dentro de outro grid container.


```html
<body>
	<div class="grid-container">
		<div>Lorem</div>
		<div>Lorem</div>
		
		<div class="nested-container">
			<div>Lorem</div>
			<div>Lorem</div>
			<div>Lorem</div>
			<div>Lorem</div>
		</div>
		
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
	</div>
</body>
```


```css
.nested-container{
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	grid-auto-rows: 70px;
	grid-gap: 1em;
}

.nested-container > div{
	border: #333 1px solid;
	padding: 1em;
}
```

## Básico (Terceira página)

Agora vamos criar o documento **index3.html** e **index3.css** e estrurar nossa primeira página e estilo básico.

```html
<body>
	<div class="grid-container">
		<div class="item item1">Lorem</div>
		<div class="item item2">Lorem</div>
		<div class="item item3">Lorem</div>
		<div class="item item4">Lorem</div>
	</div>
</body>
```


```css
.grid-container > div{
	background: #eee;
	padding: 1em;

}

.grid-container > div:nth-child(odd){
	background: #ddd;
}
```

### Alinhamento-espaçamento-distribuição Geral



```css
.grid-container {
	/*Demais propriedades*/
	
	/*Define alinhamento-organização horizontal dos itens*/
	justify-content: : strectch;
	
	/*Define alinhamento-organização vertical dos itens*/
	align-content: end;
}
```

## Básico (Quarta página)

Agora vamos criar o documento **index4.html** e **index4.css** e estrurar nossa primeira página e estilo básico.

```html
<body>
	<div class="grid-container">
		<div class="item item1">Lorem</div>
		<div class="item item2">Lorem</div>
		<div class="item item3">Lorem</div>
		<div class="item item4">Lorem</div>
	</div>
</body>
```


```css
.grid-container {
	display: grid;
	grid-template-columns: 1fr 2fr 1fr;
	/*Define espaçamento entre colunas*/
	grid-column-gap: 1em;
	/*Define espaçamento entre linhas*/
	grid-row-gap: 1em;
	/*Define espaçamento entre ambos... linhas e colunas*/
	grid-gap: 1em;
	/*Define altura das linhas do grid*/
	grid-auto-rows: minmax(100px, auto);

}

.grid-container > div{
	background: #eee;
	padding: 1em;

}

.grid-container > div:nth-child(odd){
	background: #ddd;
}

```

### Posicionamento Básico


```css
.item1{
	grid-column: 1/3;
	grid-row: 1/3;
}
.item2{
	grid-column: 3;
	grid-row: 1/3;
}
.item3{
	grid-column: 2/4;
	grid-row: 3;
}
.item4{
	/*Sobreposição*/
	grid-column:1;
	grid-row: 2/4;
	border: 1px solid #333;
}

```


## Básico (Quinta página)

Agora vamos criar o documento **index5.html** e **index5.css** e estrurar nossa primeira página e estilo básico.

```html
<body>
	<div class="grid-container">
		<div class="header">cabeçalho</div>
		<div class="menu">menu</div>
		<div class="content">conteúdo</div>
		<div class="footer">rodapé</div>
	</div>
</body>
```


```css
.grid-container{
	display: grid;
	grid-gap: 3px;
	grid-template-columns: repeat(2, 1fr);
	grid-template-rows: 40px 40px;
}
```

Vamos trabalhar com 3 colunas

```css
.grid-container{
	display: grid;
	grid-gap: 3px;
	grid-template-columns: repeat(2, 1fr);
	grid-template-rows: 40px 200px 40px;
}
```
O header deve ocupar toda a linha.


```css
.header{
	/*Sintaxe quebrada*/
	/*grid-column-start: 1;
	grid-column-end: 3;*/

	/*Sintaxe abreviada/
	grid-column:  1 / 3;
}
```

Nosso rodapé também deve ocupar uma linha inteira

```css
.footer{
	/*
	grid-column:  1 / 3;
	grid-column: 1 / span 2;*/
	
	/*Começa na coluna 1 e vai até a última coluna (penúltima linha)*/
	grid-column: 1 / -1;
}

```

Nosso cabeçalho também deve ir até a última coluna... então vamos atualizar

```css
.header{
	grid-column:  1 / -1;
}
```

Agora queremos colocar o menu com largura menor que a parte de conteúdo, então podemos redefinir a largura das colunas.

```css

	grid-template-columns: 1fr 4fr;

```

Entretanto, vamos deixar nossa página mais dinamica.

```css

	grid-template-columns: repeat(12, 1fr);

```

E configurar o tamanho do content na mão

```css

.content{
	grid-column: 2 / -1;
}

```

## Básico (Sexta página)

Agora vamos criar o documento **index6.html** e **index6.css** e estrurar nossa primeira página e estilo básico.

```html
<body>
	<div class="grid-container">
		<div class="header">cabeçalho</div>
		<div class="menu">menu</div>
		<div class="content">conteúdo</div>
		<div class="footer">rodapé</div>
	</div>
</body>
```


```css
.grid-container{
	/*altura responsiva*/
	height: 100%;
	display: grid;
	grid-gap: 3px;
	grid-template-columns: repeat(12, 1fr);
	grid-template-rows: 40px auto 40px;
}
.header{
	grid-column:  1 / -1;
}

.footer{
	grid-column: 1 / -1;
}

.content{
	grid-column: 2 / -1;
}
```

### Template Area

Vamos criar uma string para cada linha e uma célula para cada coluna. 

Aqui não estamos definindo as colunas e linhas, mas dando um nome/apelido para eles.

Teremos então uma representação de como queremos que nosso grid seja mostrado.

```css
.grid-container{
	height: 100%;
	display: grid;
	grid-gap: 3px;
	grid-template-columns: repeat(12, 1fr);
	grid-template-rows: 40px auto 40px;

	grid-template-areas: 
		"h h h h h h h h h h h h"
		"m c c c c c c c c c c c"
		"f f f f f f f f f f f f"
	;
}

```

Agora vamos deletar o posicionamento dos elementos e usar os apelidos definidos para posicionar os elementos

```css
.header{
	grid-area: h;
}

.footer{
	grid-area: f;
}

.content{
	grid-area: c;
}

.menu{
	grid-area: m;
}

```

	> Note que está responsivo!

Olhe que simples para fazer alterações!

```css
.grid-container{
	height: 100%;
	display: grid;
	grid-gap: 3px;
	grid-template-columns: repeat(12, 1fr);
	grid-template-rows: 40px auto 40px;

	grid-template-areas: 
		"m h h h h h h h h h h h"
		"m c c c c c c c c c c c"
		"m f f f f f f f f f f ."
	;
}

```
# Próxima Aula

## justify 2.0

## Auto-fit e Auto-fill

## Galeria Responsiva 2.0

## Fluid Grid System Layout
