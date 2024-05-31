# # 2.5 Capítulo 5 (p. 64/77)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 2 | Modelos preditivos (capítulos 4 a 10)

### 5. Métodos probabilísticos

#### 5.1 Brevíssimas considerações sobre probabilidade[^1]

Em linhas gerais, a probabilidade pode ser definida como **medida da frequência relativa**[^2] de um evento[^3] — isto é, a quantidade de vezes em que um determinado resultado ocorre ao longo de uma série experimental, desde que as condições nas quais foi observado se mantenham constantes — ou **medida de crença** de um indivíduo, decorrente de subjetivismo pessoal (Ross, 2010). Ela diz respeito a formas de quantificar a incerteza associada à previsão de resultados de eventos aleatórios e, sob uma perspectiva mais ampla, também à quantidade de surpresa esperada ao observar essas ocorrências e à quantidade de informação intrínseca a tais observações (Ross, 2010).

>"Parece razoável supor que a quantidade de surpresa causada pela informação de que E ocorreu deve depender da probabilidade de E. [...] [Logo,] a surpresa que alguém sente ao saber da ocorrência do evento E depende somente da probabilidade de E, [...] [então] não há surpresa ao ouvirmos que um evento cuja ocorrência é certa tenha de fato ocorrido [...] [, pois] quanto mais improvável é a ocorrência de um evento, maior é a surpresa causada por sua ocorrência." (ROSS, 2010, p. 501/502).

Nesse sentido, a quantificação tanto da surpresa quanto da incerteza traduzem a mesma imprevisibilidade inerente ao contexto probabilístico e, exatamente por consubstanciarem enfoques distintos de uma mesma linha de raciocínio, podem ser vistas como a entropia[^4] de uma variável aleatória[^5] (Ross, 2010) ou, em outras palavras, de um evento qualquer. "De fato, na teoria da informação, [...] é interpretada como a quantidade média de informação recebida quando o valor de [uma variável aleatória] X é observado." (ROSS, 2010, p. 504). O **valor esperado** ou a **esperança** de uma variável aleatória "[...] é uma média ponderada dos possíveis valores que [a variável aleatória] X pode receber, com cada valor sendo ponderado pela probabilidade de que [a variável aleatória] X seja igual a esse valor." (ROSS, 2010, p. 160).

Consoante a teoria da informação, a entropia de um sistema pode ser compreendida como uma métrica da [im]previsibilidade da ocorrência de determinado evento, tal que quanto maior a quantidade de informações disponíveis para ajustar a expectativa relacionada à observação, tão menor será a entropia e a incerteza associadas; consequentemente, por outro lado, se houver poucas informações prévias para auxiliar na valoração da probabilidade, o aumento da entropia consequentemente importará em maior incerteza. Isso acontece porque ela é inversamente proporcional à interpretabilidade dos dados: cenários de maior entropia reduzem o valor informacional porque aumentam a desorganização (confusão), enquanto os de menor entropia favorecem a organização — e reduzem a confusão — dos dados, tornando-os mais interpretáveis e previsíveis.

Não por outro motivo, "*uncertainty represents the reliability of our inferences*" (DAVIS et al., 2020, p. 3).

Entretanto, é valioso observar que, "frequentemente, quando realizamos um experimento, estamos interessados principalmente em alguma função do resultado e não no resultado em si." (ROSS, 2010, p. 151).

#### 5.2 Teorema de Bayes, métodos probabilísticos bayesianos e aprendizado bayesiano[^6]

A **probabilidade condicional**[^7] avalia a probabilidade de que um evento ocorra, dada a ocorrência ou não de outro, já conhecido, a qual deve ser considerada para obter a probabilidade total. O cálculo da probabilidade condicionada é especialmente útil quando se trabalha com dados incompletos ou imprecisos.

Os métodos probabilísticos bayesianos, sustentados no Teorema de Bayes, "[...] assumem que a probabilidade de um evento A, que pode ser uma classe [...], dado um evento B, que pode ser o conjunto de valores dos atributos de entrada [...], não depende apenas da relação entre A e B, mas também da probabilidade de observar A independentemente de observar B (Mitchell, 1997)." (FACELI et al., 2023, p. 64). No que pertine ao aprendizado de máquina, ele "[...] fornece uma maneira de calcular a probabilidade de um evento ou objeto pertencer a uma classe P(B|A) utilizando a probabilidade *a priori* da classe, P(A), a probabilidade de observar vários objetos com os mesmos valores de atributos que pertencem à classe, P(B|A), e a probabilidade de ocorrência desses objetos, P(B)." (FACELI et al., 2023, p. 64), e pode ser utilizado para resolver problemas em cenários probabilísticos.

Noutras palavras, o Teorema de Bayes expressa a probabilidade *a posteriori*, que é a probabilidade *a priori*, inicialmente conhecida, sopesada pelas informações adicionais disponíveis — na verdade, pela verossimilhança da hipótese mais provável à luz das novas evidências, que servem para atualizar ou refinar a probabilidade inicial, em vez de desconstruí-la ou substituí-la por completo.

"No aprendizado bayesiano, o valor de uma variável aleatória tem uma probabilidade associada. [...] O teorema de Bayes é usado para calcular a probabilidade *a posteriori* de um evento, dadas sua probabilidade *a priori* e a verossimilhança do novo dado." (FACELI et al., 2023, p. 66).

A função que calcula a probabilidade condicionada e separa os exemplos em classes distintas é chamada **função discriminante**. "Dependendo das hipóteses propostas, diferentes funções discriminantes são obtidas, levando a diferentes classificadores" (FACELI et al., 2023, p. 66), e uma das formas de obtê-la é por meio da estimativa MAP (*Maximum A Posteriori*), que busca maximizar a eficiência preditiva ao combinar as informações disponíveis *a priori* com a hipótese mais provável (verossímil) dada a nova evidência observada.

#### 5.3 Classificador *naive* Bayes

É um algoritmo que, aplicando o Teorema de Bayes, classifica objetos a partir do cálculo da probabilidade individual de cada atributo, assumindo serem independentes entre si e em relação à classe. Presume-se que a probabilidade de que o exemplo, assim considerado como um conjunto de atributos, pertença à classe é proporcional ao produto das probabilidades dos atributos individualmente considerados, isto é, de que cada um deles ocorra em objetos daquela classe. Essa característica faz com que não seja uma boa opção em cenários que envolvam atributos interdependentes ou em que seja importante a busca e/ou análise de correlações.

No tocante à implementação, as probabilidades são calculadas durante o treinamento por meio do uso extensivo de contadores: um para a probabilidade *a priori* de cada classe; outros tantos quantos forem os atributos qualitativos por classe; e para os atributos quantitativos, se previamente discretizados, deverá haver um contador por intervalo para cada classe. Alternativamente, é possível supor que os atributos quantitativos possuam determinada distribuição, comumente a normal/gaussiana, o que a literatura aponta menos eficiente em comparação com a discretização (Dougherty et al., 1995; Domingos e Pazzini, 1997, apud Faceli et al., 2023), porque não necessariamente tal assunção será verdadeira.

De modo geral, são destacados dentre os aspectos positivos do algoritmo a eficiência na indução do modelo, facilidade de implementação, bom desempenho em cenários variados, ainda que haja alguma correlação entre atributos, boa interpretabilidade de resultados, pois "[...] resume a variabilidade do conjunto de dados em tabelas de contingência, e assume que estas são suficientes para distinguir entre as classes" (FACELI et al., 2023, p. 71), e a capacidade de lidar com dados incompletos ou imprecisos, "isso porque [supondo um problema de classificação binária] o atributo contribuirá igualmente na previsão das duas classes e os outros atributos é que determinarão a classificação final." (FACELI et al., 2023, p. 71).

Já como aspectos negativos, destaca-se a sensibilidade à presença de atributos redundantes, que exercerão maior influência sobre a classificação porque "[...] o NB desconsidera a relação entre os atributos, tratando-os como independentes" (FACELI et al., 2023, p. 71) e as peculiaridades inerentes aos atributos quantitativos. Ademais, "frequentemente, os valores de probabilidade obtidos pelo NB não são realistas. Contudo, eles fornecem um bom ranqueamento, de maneira que a regra do máximo *a posteriori* pode ser aplicada com sucesso." (FACELI et al., 2023, p. 71).

Há diversas implementações alternativas desse algoritmo, desenvolvidas para contornar as limitações e otimizar o desempenho do classificador, como o *naive* Bayes hierárquico, a árvore de *naive* Bayes, o semi-*naive* Bayes, o *naive* Bayes construtivo, o Bayes Flexível e o Linear Bayes, os quais podem apresentar desempenho superior, especialmente, em cenários específicos.

#### 5.4 Redes bayesianas

"Os modelos gráficos probabilísticos, ou redes bayesianas (Pearl, 1988), utilizam o conceito de independência condicional entre variáveis para obter um equilíbrio entre o número de parâmetros a calcular e a representação de dependências entre as variáveis. Esses modelos representam a distribuição de probabilidade conjunta de um grupo de variáveis aleatórias em um domínio específico" (FACELI et al., 2023, p. 72) e podem ser empregados em tarefas que vão "[...] desde [a] previsão, em que se pretende obter o resultado mais provável para os dados de entrada, até o diagnóstico, em que se pretende obter as causas mais prováveis para os efeitos observados." (FACELI et al., 2023, p. 75).

Nesse sentido, duas **variáveis aleatórias** são **independentes**[^8] se a probabilidade de uma não influenciar a de outra — ou seja, o valor de uma não serve para sugerir o de outra —; **condicionalmente independentes** se essa condição subsistir na presença de uma terceira variável, tal que a probabilidade da primeira dada a segunda e a terceira é igual à da primeira dada unicamente a terceira — isto é, as probabilidades condicionais não se influenciam mutuamente, de modo que a da primeira terá o mesmo valor na presença de apenas uma delas ou de ambas; e, contrariamente, são **dependentes** aquelas que não forem independentes (Ross, 2010), ou seja, quando a probabilidade de ocorrência de uma mudar a da outra[^9].

Uma rede Bayesiana utiliza um grafo acíclico direcionado[^10] (*directed acyclic graph* - DAG) para representar as variáveis aleatórias preditivas/independentes, conjuntamente denominadas Pais da variável alvo/dependente, que correspondem a seus nós ou vértices, e a correlação ou influência entre eles, consubstanciadas em suas arestas ou linhas. Esse elemento estrutural é acompanhado pelo conjunto de tabelas de probabilidade condicional, formado pelas probabilidades condicionais de cada variável aleatória dados os nós parentais, em se tratando de valores discretos.

## Principais tópicos

- **Probabilidade**
  - Dois pontos de vista
    - Medida da frequência relativa de um evento
    - Medida da crença de um indivíduo em relação a um evento
  - **Quantificação**:
    - da incerteza associada à [im]previsibilidade de eventos aleatórios
    - da surpresa esperada ao observar tais eventos
    - da informação intrínseca à observação
  - **Conceitos abordados**
    - Espaço amostral, evento e probabilidade
    - Esperança ou valor esperado
    - **Entropia**
      - Medida da desordem de um sistema
      - Organização, interpretabilidade e valor informacional dos dados
      - Relacionada com a incerteza e a surpresa em cenários probabilísticos
    - **Variável aleatória**
      - Função definida no espaço amostral
      - Discretas e contínuas
      - Independentes, condicionalmente independentes e dependentes
- **Teorema de Bayes**
  - É uma forma de calcular a probabilidade de ocorrência de um evento A dado um evento B que já ocorreu (P(A|B)), considerando **(a)** a probabilidade *a priori* de A (P(A)), isto é, a probabilidade de que A ocorra independentemente de B; **(b)** a probabilidade condicional de B dada a ocorrência de A (P(B|A)); e **(c)** a probabilidade total de B (P(B)), que consiste **(c.1)** novamente na probabilidade *a priori* de A e na probabilidade de B dado A, acrescida **(c.2)** da probabilidade de que A não ocorra, mas B ocorra independentemente de A.
  - É uma forma de ajustar a probabilidade de A em relação a B, considerando novas evidências de B, sem descartar a probabilidade inicial de A, que ao invés disso é atualizada pela probabilidade de B dado A e pela probabilidade total de B.
- **Aprendizado bayesiano**
  - O valor de uma variável aleatória é estimado a partir da probabilidade *a priori* da classe (evento) e da probabilidade de que novos objetos pertençam àquela classe, considerando as informações disponíveis (verossimilhança).
  - Dados imprecisos ou incompletos
  - Função discriminante
- **Classificador *naive* Bayes**
  - A classificação resulta do produto das probabilidades individuais de cada atributo, que se presumem independentes entre si e em relação à classe.
  - Incapaz de lidar com atributos interdependentes
- **Redes bayesianas**
  - Modelos gráficos probabilísticos
  - Independência condicional entre variáveis
  - Grafo acíclico direcionado
    - Nós: variáveis aleatórias
    - Arestas: influência ou correlação entre as variáveis aleatórias
  - Tabelas de probabilidade condicional

## Referências complementares

AUDY, Jorge L N.; ANDRADE, Gilberto K.; CIDRAL, Alexandre. **Fundamentos de sistemas de informação**. E-book. Porto Alegre: Bookman, 2007.

DAVIS, Josiah; ZHU, Jason; OLDFATHER, Jeremy; MACDONALD, Samual; TRZASKOWSKI, Maciej; KELSEN, Max. 2020. **Quantifying uncertainty in deep learning systems**. Disponível em <https://d1.awsstatic.com/APG/quantifying-uncertainty-in-deep-learning-systems.pdf>. Acesso em 18 mai. 2024.

ROSS, Sheldon. **Probabilidade: um curso moderno com aplicações**. Trad. Alberto Resende De Conti. 8 ed. Porto Alegre: Bookman, 2010.

SIPSER, Michael. **Introdução à teoria da computação**. Trad. Rui José Guerra Barreto de Queiroz. 2 ed. São Paulo: Cengage Learning, 2021.

## Notas

[^1]: Este tópico é autoral, portanto, não consta no texto original do livro.

[^2]: Como uma métrica de frequência relativa, pode ser definida nos termos de "[...] um experimento, cujo espaço amostral é S, [que] seja realizado repetidamente em condições exatamente iguais. Para cada evento E do espaço amostral S, definimos n(E) como o número de vezes que o evento E ocorre nas n primeiras repetições do experimento. Então, P(E), a probabilidade do evento E, é definida como [...] a proporção (limite) de tempo em que E ocorre [...] ou como a frequência limite de E." (ROSS, 2010, p. 44).

[^3]: Denomina-se **espaço amostral** (S) o conjunto que presumidamente contenha a totalidade de resultados possíveis de um experimento, mesmo os incertos; e **evento** (E) qualquer subconjunto de S, tal que, "se o resultado do experimento estiver contido em E, então dizemos que E ocorreu." (ROSS, 2010, p. 40).

[^4]: Na teoria da informação, a **entropia** é uma propriedade que "[...] mede o grau de desordem de um sistema, e a forma de combater essa desordem se dá através da informação." (AUDY; CIDRAL, 2007, p. 37).

[^5]: **Variáveis aleatórias** são "[...] grandezas de interesse, ou, mais formalmente, [...] funções reais definidas no espaço amostral [...]. Como o valor da variável aleatória é determinado pelo resultado do experimento, podemos atribuir probabilidades aos possíveis valores da variável aleatória" (ROSS, 2010, p. 151), que podem ser **discretas** — há uma quantidade máxima (finita) e [infinitamente] contável de valores possíveis — ou [absolutamente] **contínuas** — há infinitos e incontáveis valores que podem ser assumidos ou, inversamente, cuja probabilidade de que assumam determinado valor específico é nula (Ross, 2010).

[^6]: No livro, equivalente à introdução do capítulo 5 e à seção 5.1 (aprendizado bayesiano).

[^7]: A "[...] probabilidade condicional de que E ocorra dado que F ocorreu [...] é representada por P(E | F). [...] [Noutras palavras,] se o evento F ocorrer, então, para que E ocorra, é necessário que a ocorrência real seja um ponto tanto em E quanto em F; isto é, ela deve estar em EF. Agora, como sabemos que F ocorreu, tem-se que F se torna nosso novo, ou reduzido, espaço amostral; com isso, a probabilidade de que o evento EF ocorra será igual à probabilidade de EF relativa à probabilidade de F." (ROSS, 2010, p. 82).

[^8]: Diz-se que duas variáveis aleatórias "[...] X e Y são independentes se o conhecimento do valor de um não mudar a distribuição do outro. Variáveis aleatórias que não são independentes são chamadas de dependentes." (ROSS, 2010, p. 293). Observe-se que a "independência é uma relação simétrica. As variáveis aleatórias X e Y são independentes se sua função densidade conjunta (ou função de probabilidade conjunta, no caso discreto) é o produto de suas funções densidade (ou de probabilidade) individuais. Portanto, dizer que X é independente de Y é equivalente a dizer que Y é independente de X — ou somente que X e Y são independentes. Como resultado, ao considerar se X é independente ou não de Y em situações em que não é intuitivo saber que o valor de Y não muda as probabilidades relacionadas a X, pode ser útil inverter os papeis de X e Y e perguntar se Y é independente de X." (ROSS, 2010, p. 304).

[^9]: Sobre **eventos independentes**, a P(E|F), isto é, "[...] a probabilidade condicional de E dado F, não é geralmente igual [...] [à] probabilidade incondicional de E [P(E)]. Em outras palavras, o conhecimento de que F ocorreu geralmente muda a chance de ocorrência de E. Nos casos especiais em que P(E|F) é de fato igual a P(E), dizemos que E é independente de F. Isto é, **E é independente de F se o conhecimento de que F ocorreu não mudar a probabilidade de ocorrência de E.**" (ROSS, 2010, p. 106, destaquei).

[^10]: "Um **grafo não-direcionado**, ou simplesmente **grafo**, é um conjunto de pontos com linhas conectando alguns dos pontos. Os pontos são conhecidos como **nós** ou **vértices**, e as linhas são chamadas **arestas** [...]. Em um grafo $G$ que contém nós $i$ e $j$, o par $(i,j)$ representa a aresta que conecta $i$ e $j$. A ordem de $i$ e $j$ não importa em um grafo não-direcionado; portanto, os pares $(i,j)$ e $(j,i)$ representam a mesma aresta. Às vezes, descrevemos arestas com conjuntos em vez de pares, como em $\{i,j\}$, porque a ordem dos nós não é importante." (SIPSER, 2021, p. 10, destaques no original). Nesse sentido, "um **caminho** em um grafo é uma sequência de nós conectados por arestas. [...] Um caminho é um **ciclo**, se começa e termina no mesmo nó. [...] Se ele possui setas em vez de linhas, o grafo é um **grafo direcionado** [...]. Em um grafo direcionado, representamos uma aresta de $i$ para $j$ como um par $(i,j)$. A descrição formal de um grafo direcionado $G$ é $(V,E)$, onde $V$ é o conjunto de nós e $E$, o conjunto de arestas. [...] Um caminho no qual todas as setas apontam na mesma direção que seus passos é chamado **caminho direcionado**." (SIPSER, 2021, p. 12/13, destaques no original). Portanto, *mutatis mutandis*, o percurso entre os vértices de um **grafo acíclico direcionado** é unidirecional, ou seja, as arestas que os conectam têm setas indicativas da única direção possível do encadeamento, e não forma ciclos, de modo que o fluxo não termina no mesmo nó em que começou ou, noutras palavras, não retorna ao ponto de origem.
