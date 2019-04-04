# Página Lista de Passos

Nesta seção iremos apresentar os passos necessários para adquirir o produto ou serviço fornecido pelo nosso cleinte.

**Conteúdo que iremos abordar:**

  - Desenhando circulos apenas com CSS
  - Técnica para separação de seções
  - Como encorporar botões do App Store (iPhone) e Play Store (Android)

## Criando a Seção Steps (_section-steps_)

Primeiramente vamos criar uma nova seção com a classe (_section-steps_), logo após a seção _section-photos_ 

```html
    <!--Abrindo a seção steps (passos) -->
    <section class="section-steps">

    <!--Fechando a seção steps (passos) -->
    </section>
```
## Título da Seção
Agora vamos criar uma _div_ com a classe _row_ dentro da seção (_section-steps_). Assim teremos um container centralizado, onde iremos incluir o título desta seção, como um elemento de _h2_.

```html
    <!--Abrindo a seção steps (passos) -->
    <section class="section-steps">
      <!--Abrindo a div com a classe ROW para criar um container centralizado,
        será usando para colocar nosso título  -->
      <div class="row">
        
        <!--Título da seção -->
        <h2>Esperando o quê? &mdash; Bastam 3 passos</h2>
      
      <!--Fechando a div ROW -->
      </div>
    <!--Fechando a seção steps (passos) -->
    </section>
```

## Conteúdo da Seção

Após incluir o título da seção, vamos incluir um novo container (_row_) abaixo do container do título. Pois abaixo do título teremos uma linha com duas colunas. Na coluna da esquerda teremos uma imagem e na coluna da direita teremos a descrição dos passos para adquirir o produto ou serviço. Como teremos 2 colunas, o nome da classe dessas colunas deve ser _col_ _span-1-of-2_ _steps-box_

  - _col_ para indicar que a div é uma coluna
  - _span-1-of-2_ para indicar que é uma coluna de duas
  - _steps-box_ para indicar que é nossa "caixa" de passos, mais para fins de estilo


```html
    <section class="section-steps">
      <!--Container com o título da seção -->
      <div class="row">
        <h2>Esperando o quê? &mdash; Bastam 3 passos</h2>
      </div>

      <!-- Abrindo a div com a classe ROW para criar um container centralizado,
            será usando para colocar 2 colunas  -->
      <div class="row">
          <div class="col span-1-of-2 steps-box">
              <!-- Conteúdo da coluna da esquerda -->
          </div>
          <div class="col span-1-of-2 steps-box">
              <!-- Conteúdo da coluna da direita -->
          </div>
      </div>
      
    </section>
```
Após a criação do container (_row_) com as duas colunas (_col_ _span-1-of-2_ _steps-box_), vamos colocar o conteúdo de cada uma das colunas. Na Coluna da esquerda, vamos adicionar a imagem de um smartphone rodando o aplicativo do Saúde no Prato, utilizando a tag _img_, vamos criar uma classe para essa tag, chamando ela de _app-screen_.

Na coluna da direita, vamos incluir uma _div_ com a classe _step_ (significa "passo", pode usar nomeclatura em português, caso considere mais fácil de entender o conteúdo). Dentro do container _step_, vamos adicionar uma _div_ com o número do passo e logo após um paragráfo com a frase referente a esse passo. 

Neste caso teremos 3 passos, sendo assim, teremos 3 _div_ da classe _step_

```html
<div class="row">
  <!-- Conteúdo da coluna da esquerda -->
  <div class="col span-1-of-2 steps-box">
      <!-- Adiciona a imagem da tela de um smarphone com nosso aplicativo aberto -->
      <img src="resources/img/app-screen.png" alt="Seu pedido pelo iPhone" class="app-screen">
  </div>

  <!-- Conteúdo da coluna da direita -->
  <div class="col span-1-of-2 steps-box">
      <!-- Container com o primeiro passo -->
      <div class="step">
          <div>1</div>
          <p>Selecione qual plano melhor se encaixa no seu bolso!</p>
      </div>
      <!-- Container com o segundo passo -->
      <div class="step">
          <div>2</div>
          <p>Escolha uma refeição deliciosa e super saúdavel!</p>
      </div>
      <!-- Container com o terceiro passo -->
      <div class="step">
          <div>3</div>
          <p>Aguarde apenas 15 minutos e receba a refeição escolhida na porta da sua casa!</p>
      </div>
  </div>
```
Basta incluir os botões de download dos aplicativos para Android e iOS, após o container do terceiro passo. Para isso, crie um link utilizando a tag _a_, então vamos criar a classe _btn-app_ para esse tag. Após isso, inclua uma imagem (tag _img_) como conteúdo desse link. Faça isso para o criar um botão para o aplicativo nativo para Android e outro para iOS.

```html
      <!-- Container com o terceiro passo -->
      <div class="step">
          <div>3</div>
          <p>Aguarde apenas 15 minutos e receba a refeição escolhida na porta da sua casa!</p>
      </div>
    
      <!-- Botões para os aplicativos -->
      <a href="#" class="btn-app"><img src="resources/img/download-app-ios.svg" alt="Botão App Store"></a>
      <a href="#" class="btn-app"><img src="resources/img/download-app-android.png" alt="Botão Play Store"></a>
  </div>
```

Agora, se abrirmos nossa página, vamos verificar que o conteúdo esta lá, porém, de uma forma não muito atrativa.

## Estilizando nossa seção com CSS


