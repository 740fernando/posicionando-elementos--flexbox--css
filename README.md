<h1> O que é o Flexbox </h1>
Por muito tempo, as únicas ferramentas disponíveis para a criação de leiautes em CSS e posicionar elementos com boa compatibilidade entre browsers eram float e position. Porém, essas ferramentas possuem algumas limitações muito frustrantes, especialmente no que diz respeito à responsividade. Algumas tarefas que consideramos básicas em um leiaute, como centralização vertical de uma div-filha com relação a uma div-mãe, fazer com que divs-filhas ocupem a mesma quantidade de espaço e colunas terem o mesmo tamanho independente da quantidade de conteúdo interno, eram impossíveis ou muito difíceis de serem manejadas com floats ou position, ao menos de forma prática e flexível.

A ferramenta Flexbox (de Flexible Box) foi criada para tornar essas tarefas mais simples e funcionais: as filhas de um elemento com Flexbox podem se posicionar em qualquer direção e pode ter dimensões flexíveis para se adaptar.


<h2>Elementos</h2>

Flex container é o elemento que envolve sua estrutura. Você define que um elemento é um Flex Container com a propriedade display e valores flex ou inline-flex.

![image](https://user-images.githubusercontent.com/32016610/173561614-c9483bd7-3564-4393-99c1-09324a79151f.png)


Flex Item são elementos-filhas do flex container.

Eixos ou Axes são as duas direções básicas que existem em um Flex Container: main axis, que seria o eixo horizontal ou o eixo principal, e cross axis que seria o eixo vertical.


<h2>Propriedades para o elemento-mãe</h2>

![image](https://user-images.githubusercontent.com/32016610/173561716-8a513928-0883-4aa1-8d71-a719e462c5d0.png)

Quando utilizamos o Flexbox, é muito importante saber quais propriedades são declaradas no elemento-mãe (por exemplo, uma div que irá conter os elementos a serem alinhados) e quais serão declaradas nos elementos-filhas. Abaixo, seguem algumas propriedades que devem ser declaradas utilizando o elemento-mãe como seletor (para alinhar elementos-filhas):

flex-direction determina a origem e o término do fluxo dos ítens. Eles seguem o vetor estabelecido pelo modo tradicional de escrita: esquerda para direita em row, cima para baixo em column, ou no sentido inverso utilizando -reverse.

![image](https://user-images.githubusercontent.com/32016610/173561803-1063dc74-3451-406a-aa34-fcc3829db456.png)


![image](https://user-images.githubusercontent.com/32016610/173561862-c06c85ef-f9a0-4b77-8b10-33bdca771b6f.png)


Você pode definir se os elementos serão forçados a ficar em uma mesma linha ou se eles irão quebrar em várias linhas com a propriedade flex-wrap.

![image](https://user-images.githubusercontent.com/32016610/173561892-2d9c6862-1699-4dc1-9d1d-7d537ab28965.png)

![image](https://user-images.githubusercontent.com/32016610/173561920-f85976d9-fd89-4d68-a219-0fa5f47f1bb2.png)

A propriedade flex-flow é uma propriedade shorthand (uma mesma declaração inclui vários valores relacionados a uma mesma propriedade) que inclui flex-direction e flex-wrap. Determina a ordem do fluxo em que os elementos aparecerão.

O justify-content define o alinhamento das filhas ao longo do eixo principal.

 - flex-container justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
 
![image](https://user-images.githubusercontent.com/32016610/173562283-29b665fc-c7c1-4336-a103-9dc8ed57a985.png)

![image](https://user-images.githubusercontent.com/32016610/173562570-d6f7ddb2-5a2d-4ec6-9333-065970a500fa.png)

align-items define o comportamento padrão de como flex items são alinhados de acordo com o eixo vertical (cross axis). De certa forma, funciona de forma similar ao justify-content, porém no eixo perpendicular.

![image](https://user-images.githubusercontent.com/32016610/173562628-cb32e65a-7318-4197-801e-30c0a627c100.png)

![image](https://user-images.githubusercontent.com/32016610/173562666-ff9e1b75-14c5-4d7c-9503-48818f550bd2.png)

![image](https://user-images.githubusercontent.com/32016610/173562734-6fe79fb2-214b-4bc7-9583-43d11defeaa5.png)


align-content alinha o conteúdo dentro do container quando há espaço extra no eixo vertical, similar à forma que justify-content alinha ítens individuais dentro do eixo principal.

  - flex-container - align-content: flex-start | flex-end | center | space-between | space-around | stretch;
  
![image](https://user-images.githubusercontent.com/32016610/173562956-e232dd24-3826-4d9a-97a7-dd1d6c296946.png)

![image](https://user-images.githubusercontent.com/32016610/173562981-23ee47be-0d3d-4959-89b8-7190c8e10268.png)


Propriedades para elementos-filhas
A seguir, veremos propriedades que devem ser declaradas tendo como seletor elementos-filhas, ou seja:

![image](https://user-images.githubusercontent.com/32016610/173563026-91470fce-40b2-499f-a9e6-f464b4c83a37.png)

Isso significa que, onde existe um elemento-mãe com propriedade flex, é possível atribuir propriedades flex específicas também para as filhas.

Importante!

O CSS só enxerga a hierarquia mãe-filha; não vai aplicar as propriedades flex para elementos HTML que não estejam diretamente relacionados;
Para que as propriedades funcionem nos elementos-filhas, as mães devem ter propriedade flex.
As propriedades float, clear e vertical-align não têm efeito em flex-items.
A propriedade order determina o lugar que os elementos aparecerão.

![image](https://user-images.githubusercontent.com/32016610/173563107-424e6b66-d5eb-45dd-b2f9-878747a8a7b1.png)

![image](https://user-images.githubusercontent.com/32016610/173563168-5ebdeb4a-1480-48ed-9e9f-89aa86d5f580.png)


flex-grow define a habilidade de um elemento-filha de "crescer" e ocupar uma área maior, se necessário. Por exemplo, se em uma lista de 3 filhas, 2 delas têm propriedade flex-grox: 1 e 1 delas tem flex-grow:2, essa última crescerá para ocupar o dobro do tamanho das irmãs.

  .flex-item {
    flex-grow: <numero>; /* o valor default(padrão) é 0 */
  }

![image](https://user-images.githubusercontent.com/32016610/173563288-f072333f-45c7-4214-80ef-2a41a2befe16.png)

Existem outras propriedades para as filhas, como flex-shrink, flex-basis e a shorthand flex, você pode pesquisar sobre elas para aumentar seu repertório.
