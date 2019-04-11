# Página Rodapé (Footer)

Nesta seção iremos apresentar dois "menus" de navegação secundários, sendo 
o primeiro com links internos e o segundo com os links para nossas principais redes sociais.

![Image_of_footer](https://github.com/romuloreis/DWDM/blob/master/assets/footer.png)
Imagem de como será nossa seção de rodapé da página.

**Conteúdo que iremos abordar:**

  - Revisão do conteúdo abordado até o momento.

## Criando a Seção Rodapé (_footer_)

Primeiramente vamos criar uma nova seção utilizando o elemento _footer_, logo após a seção _section-testimonials_

```html
    <!--Abrindo a seção de rodapé-->
    <footer>

    <!--Fechando a seção de rodapé-->
    </footer>
```

Agora vamos organizar a estrutura do rodapé. Teremos duas _div_ da classe _row_, sendo uma abaixo da outra
(não é uma dentro da outra), conforme ilustrado no trecho de código abaixo.

```html
    <section class="section-testimonials">
        <div class="row">
            <!-- Aqui irá nossos dois menus de navegação -->
        </div>
        <div class="row">
            <!-- Aqui irá uma mensagem de copyright ou endereço da empresa -->
        </div>
    </section>
```

Na primeira _div_ da classe _row_ vamos inserir dois menus (_nav_), note pela imagem ilustrativa deste post, que os menus de navegaçao estão organizados em duas colunas, sendo assim, vamos atribuir a classe _col_ _span-1-of-2_ aos containers (_div_).

```html
       <div class="row">
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação com links internos -->
            </div>
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação de redes sociais -->
            </div>
        </div>
```

Agora basta criar uma lista não ordenada (_ul_) na primeira coluna, vamos atribuir a classe _footer-nav_ para a lista da primeiro container (_div_). Os itens (_li_) dessa lista serão links (_a_).

```html
       <div class="row">
            <div class="col span-1-of-2">
                <ul class="footer-nav">
                    <li><a href="#">Sobre Nós</a></li>
                    <li><a href="#">Nosso Blog</a></li>
                    <li><a href="#">Receitas</a></li>
                    <li><a href="#">App iOS</a></li>
                    <li><a href="#">App Android</a></li>
                </ul>
            </div>
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação de redes sociais -->
            </div>
        </div>
```

Na segunda _div_ da classe _col_ _span-1-of-1_ também vamos criar uma lista não ordenada (_ul_), atribuindo a classe _social-links_
Os elementos (_li_) dessa lista serão links (_a_) e o elemento desses links serão ícones. Caso você opte por utilizar ícones do [ionicons](https://ionicons.com/) usando a importação dos ícones pela tag _script_ no final do documento HTML, assim como foi feito aqui, vamos precisar criar um ícone para essas ícones. A classe desses ícones será utilizada posteriormente.

```html
        <div class="row">
            <div class="col span-1-of-2">
                <ul class="footer-nav">
                    <li><a href="#">Sobre Nós</a></li>
                    <li><a href="#">Nosso Blog</a></li>
                    <li><a href="#">Receitas</a></li>
                    <li><a href="#">App iOS</a></li>
                    <li><a href="#">App Android</a></li>
                </ul>
            </div>
            <div class="col span-1-of-2">
                <ul class="social-links">
                    <li><a href="#"><ion-icon class="logo-instagram" name="logo-instagram"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-facebook" name="logo-facebook"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-googleplus" name="logo-googleplus"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-twitter" name="logo-twitter"></ion-icon></a></li>
                </ul>
            </div>
        </div>
```
