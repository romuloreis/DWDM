# Galeria responsiva sem media queries!

```html
 <div class="wrapper">
    <div class="item"><img src="1.png" alt=""></div>
    ...
   <div class="item"><img src="10.png" alt=""></div>
 </div>
```


## Semi-responsivo

```css
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
background: #FBFBFB;
}

.wrapper{
width: 90%;
margin: 0 auto;
display: grid;
grid-template-columns: 1fr 1fr 1fr;
grid-auto-rows: 100%;
grid-gap: 20px;

}

```

## Responsivo

```css
.wrapper{
width: 90%;
margin: 0 auto;
display: grid;
/*valor mínimo para as imagens 200px e máximo 1fr*/
grid-template-columns: repeat(auto-fit, minmax(200px;));
grid-auto-rows: 100%;
grid-gap: 20px;

}

```
