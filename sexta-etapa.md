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

## Estilizando nossa seção com CSS

No arquivo style.css vamos definir uma cor de fundo para essa seção e depois adicionar uma regra para criar uma margem entre o topo dos containers e o elemento h2

```css
/* ----------------------------------------------- */
/* Seção Lista de Passos (Section Steps) */
/* ----------------------------------------------- */

/*Definindo cor de fundo para essa seção*/
.section-steps {
    background-color: #f4f4f4;
}

/*Regra para ambos os boxes/containers*/
.steps-box {
    margin-top: 30px; /*Margem entre ambos os boxes e o h2*/
}
```

Verifique se funcionou. Em caso de dúvidas, não hesite em pedir ajuda ao professor.
