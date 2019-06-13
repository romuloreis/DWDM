# Revisão Geral Display Grid

Primeiramente vamos criar o documento **pg01.html** e estrurar nossa primeira página.

A _div grid-container_ será nosso container GRID e cada _div_ dentro desse container será um item do GRID.

```html
<!DOCTYPE html>
<html>
<head>
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css" href="css/exemplo01.css">
	<title>Grid System</title>
</head>
<body>
	<div class="grid-container">
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
		<div>Lorem</div>
	</div>
</body>
</html>
```

Antes de começar a trabalhar com Grid vamos criar o arquivo **exemplo01.css** com as seguintes propriedades básicas:

```css
/*Define cor de fundo e padding apenas para as div que são diretamente filhas da classe grid-container*/
.grid-container > div{
	background: #eee;
	padding: 1em;

}

/*Define cor de fundo diferente apenas para as div "ímpares" que são diretamente filhas da classe grid-container*/
.grid-container > div:nth-child(odd){
	background: #ddd;
}
```


```
```


```
```


```
```


```
```



```
```
