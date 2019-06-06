# Galeria com cards


```html

    <h1>My Awesome Shots</h1>

    <main>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="http://freeaussiestock.com/free/Victoria/Melbourne/slides/fed_square.jpg">
        </div>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="https://media.defense.gov/2013/Jul/16/2000032379/-1/-1/0/130628-F-DQ639-002.JPG">
        </div>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="https://s0.geograph.org.uk/geophotos/03/25/64/3256477_ec7d83ab.jpg">
        </div>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="http://freeaussiestock.com/free/Victoria/Melbourne/slides/melbourne_museum_roof.jpg">
        </div>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="https://live.staticflickr.com/2387/1726578675_62f09cb233_z.jpg">
        </div>
        <div class="card">
            <div class="info">
                <strong class="title">My Title</strong>
                <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia consectetur sapiente ipsam nihil velit quae ab unde quasi exercitationem esse</p>        
            </div>
            <img src="https://s0.geograph.org.uk/geophotos/04/31/24/4312454_79d0a1d8.jpg">
        </div>
    </main>
 ```

```css
$colors: rgb(248, 248, 248), rgb(238, 238, 238), rgb(250, 250, 250), rgb(207, 207, 207), rgb(245, 245, 245), rgb(212, 212, 212);

body, html {
    height: 100%;
}

body {
    margin: 0;
    font-family: 'Montserrat';
}

h1 {
    margin: 5rem;
}

main {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(19rem, 1fr));
    //grid-gap: 1rem;
    cursor: pointer;

    .card {
        
        transition: transform 1s;
        
        @for $i from 1 through 6 {
            &:nth-of-type(#{$i}) {
                background: nth($colors, $i);
            }  
        }

        &:hover {
            transform: translateY(-10px);
        } 

        .info {
            padding: 1rem;
            //display: none;
        }
    
        img {
            width: 100%;
        }

        .desc {
            color: gray;
        }
    }
}
```


#REF

https://www.youtube.com/watch?v=bam83Xv4VMA

https://andy-bell.design/wrote/create-a-responsive-grid-layout-with-no-media-queries-using-css-grid/

https://drafts.csswg.org/css-grid/#auto-repeat

https://codepen.io/designcourse/pen/mYrxKr


Mais meterial sobre FR
https://medium.com/flexbox-and-grids/the-css-fractional-unit-fr-in-approachable-plain-language-fdc47bd387f7

https://hackernoon.com/understanding-css-grids-fractional-units-fr-the-easy-way-5f43ee008f29

https://alligator.io/css/css-grid-layout-fr-unit/

https://css-tricks.com/introduction-fr-css-unit/
https://css-tricks.com/introduction-fr-css-unit/
