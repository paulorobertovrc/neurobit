# # 2.6 Capítulo 6 (p. 78/100)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 2 | Modelos preditivos (capítulos 4 a 10)

### 6. Métodos simbólicos

Englobam modelos cujo objetivo é representar explicitamente, através de estruturas simbólicas[^1], o conhecimento extraído do conjunto de dados. Esses métodos facilitam a interpretação do resultado por seres humanos, visto que asseguram "[...] uma compreensibilidade maior do processo decisório [...], estando mais alinhado[s] aos princípios de que os modelos de AM devem também ser 'explicáveis' (*Explainable Machine Learning*) para garantir maior transparência em sua operação." (FACELI et al., 2023, p. 78). Em contrapartida, se utilizados isoladamente, têm menor acurácia preditiva em comparação a outros modelos, ditos "caixa-preta"[^2].

Não obstante, é importante destacar que, "atualmente, existem algoritmos eficientes para indução de árvores de decisão ou conjuntos de regras e de aplicação eficiente, com um desempenho equivalente ao de outros modelos (como redes neurais e SVM), mas com maior grau de interpretabilidade. [...] A combinação de múltiplos modelos de árvores em comitês (*ensembles*) também tem se mostrado competitiva e é uma abordagem frequentemente empregada para aumentar o desempenho preditivo desses modelos." (FACELI et al., 2023, p. 97).

## 6.1 Modelos baseados em árvores[^3]

Os modelos baseados em árvores utilizam a estrutura de dados homônima para solucionar problemas de classificação ou regressão, casos em que os algoritmos são respectivamente denominados **árvores de decisão** ou **árvores de regressão**. Em ambos os casos, a forma de se interpretar o modelo e de construir o algoritmo indutor da própria árvore são bastante similares e, de modo geral, o problema é abordado **recursivamente** por meio da estratégia da **divisão e conquista**[^4].

Nesse sentido, "um problema complexo é dividido em problemas mais simples, aos quais recursivamente é aplicada a mesma estratégia. As soluções dos subproblemas podem ser combinadas, na forma de uma árvore, para produzir uma solução do problema complexo. A força dessa proposta vem da capacidade de dividir o espaço de instâncias em subespaços e cada subespaço é ajustado usando diferentes modelos." (FACELI et al., 2023, p. 78).

"Formalmente, uma árvore de decisão[^5] é um grafo direcionado acíclico em que cada nó ou é um nó de divisão, com dois ou mais sucessores, ou um nó folha." (FACELI et al., 2023, p. 79). Os **nós de divisão** possuem testes condicionais de acordo com o valor do atributo que representam; os **nós folha** são funções que representam as saídas do modelo, possuindo os valores da variável alvo. Cada nó da árvore corresponde a uma região no espaço definido pelos atributos.

>"As regiões definidas pelas folhas da árvore são mutuamente excludentes, e a reunião dessas regiões cobre todo o espaço definido pelos atributos. A interseção das regiões abrangidas por quaisquer duas folhas é vazia. A união de todas as regiões (todas as folhas) é U. Uma árvore de decisão abrange todo o espaço de instâncias. Esse fato implica que uma árvore de decisão pode fazer predições para qualquer exemplo de entrada. [...] As condições ao longo de um ramo (um percurso entre a raiz e uma folha) são conjunções de condições e os ramos individuais são disjunções. Assim, cada ramo forma uma regra com uma parte condicional e uma conclusão. A parte condicional é uma conjunção de condições. Condições são testes que envolvem um atributo particular, operador [...] e um valor do domínio do atributo." (FACELI et al., 2023, p. 79).

Para exemplificar, vejamos a imagem a seguir:
![Árvore de decisão e regiões de decisão no espaço de objetos](../../imagens/21_am_faceli_arvore_de_decisao.png)
Figura 21 — Árvore de decisão e regiões de decisão no espaço de objetos (FACELI et al., 2023, p. 79).

### 6.1.1 Regras de divisão em tarefas de classificação

As regras de divisão servem para **atenuar a impureza** dos conjuntos de dados e balizam a construção da árvore de decisão no intuito de **maximizar a homogeneidade** dos subconjuntos gerados em cada recursão, de modo que garantir a congruência dos atributos no tocante à seleção daqueles que melhor discriminam cada classe (*goodness of split*). Para isso, normalmente adota-se a estratégia "olha para a frente um passo", de sorte que, uma vez tomada, a decisão não é reconsiderada pelo algoritmo. "Essa pesquisa de subida de encosta (*hill-climbing*) sem *backtracking* é suscetível aos riscos usuais de convergência a uma solução ótima localmente que não é ótima globalmente." (FACELI et al., 2023, p. 80).

"Uma proposta natural é rotular cada subconjunto da divisão por sua classe mais frequente e escolher a divisão que tem menores erros" (FACELI et al., 2023, p. 81), e as diversas propostas para isso convergem para a conclusão de que "[...] uma divisão que mantém a proporção de classes em todo o subconjunto não tem utilidade, e uma divisão na qual cada subconjunto contém somente exemplos de uma classe tem utilidade máxima." (FACELI et al., 2023, p. 81).

Assim, a melhor divisão é aquela que minimiza a impureza e, consequentemente, heterogeneidade dos subconjuntos. Em sentido logicamente contrário, portanto, é de se concluir que a divisão ideal busca maximizar a homogeneidade dos dados em cada subconjunto.

Conforme Martin (1997), os autores distinguem as métricas para avaliar a qualidade das divisões em subconjuntos em três grandes grupos (**funções de mérito**), considerando diferentes critérios: **(1)** baseadas na diferença entre a **distribuição de dados antes e depois da divisão**, que enfatizam a **pureza dos subconjuntos**; **(2)** baseadas em **diferenças entre os subconjuntos**, cujo enfoque é a **disparidade entre os subconjuntos** após a divisão; e **(3)** baseadas na **confiabilidade dos subconjuntos**, isto é, em medidas estatísticas de independência capazes de denotar que cada nó/subconjunto (atributo) é efetivamente adequado para produzir boas previsões, em que a ênfase é no **peso da evidência**.

Embora não haja consenso em relação à superioridade, a escolha por algum critério parece ser superior à divisão aleatória de atributos.

Nas tarefas de classificação, as regras baseadas no **ganho de informação** e no **índice de Gini** são as mais comuns.

#### 6.1.1.1 Baseadas no ganho de informação

Esta regra é baseada no conceito de **entropia**, que informa a **aleatoriedade de uma variável**, isto é, **quantifica a dificuldade** de predizê-la. A entropia também pode ser compreendida como uma medida da desordem ou impureza do conjunto de dados, e é medida em logaritmos na base 2. Logo, quanto maior a entropia, mais difícil será predizer o valor dessa variável aleatória, e **a árvore de decisão é construída de modo a minimizar a dificuldade** de predizer a variável alvo.

>"A cada nó de decisão, o atributo que mais reduz a aleatoriedade da variável alvo será escolhido para dividir os dados. [...] Os valores de um atributo definem partições [divisões] no conjunto de exemplos. Para cada atributo, o ganho de informação mede a redução na entropia nas partições obtidas de acordo com os valores do atributo. Informalmente, o ganho de informação é dado pela diferença entre a entropia do conjunto de exemplos e a soma ponderada da entropia das partições. A construção da árvore de decisão é guiada pelo objetivo de reduzir a entropia, isto é, a aleatoriedade (dificuldade para predizer) da variável alvo." (FACELI et al., 2023, p. 81).

Em cada nó de divisão da árvore, o atributo que mais reduzir a entropia, consequentemente maximizando o ganho de informação, será escolhido para resolver o subproblema — leia-se, a divisão em subconjunto naquela etapa recursiva. Logo, é esperado que a cada divisão ocorra a diminuição da aleatoriedade — incerteza em relação à classificação correta da variável alvo — em virtude da consistência dos atributos que conformam o subconjunto como sendo aqueles que melhor discriminam as classes.

Por isso é que, essencialmente, o ganho de informação consiste na redução da aleatoriedade resultante da diferença entre a entropia de todo o conjunto de dados e a dos subconjuntos.

#### 6.1.1.2 Baseadas no índice de Gini [^6]

É uma métrica de **impureza** dos nós de decisão (subconjuntos). **Avalia a probabilidade de que exemplos escolhidos ao acaso pertençam a classes diferentes, mas estejam no mesmo subconjunto.** Quanto menor o índice de Gini, mais homogêneo — e menos impuro — é o subconjunto. Nesse sentido, o atributo que melhor discrimina a classe é aquele que minimiza o índice de Gini e, via de consequência, reduz a impureza e aumenta a homogeneidade dos subconjuntos.

### 6.1.2 Regras de divisão em tarefas de regressão

## 6.2 Modelos baseados em regras

## Principais tópicos

- **Características gerais**
  - Representação explícita do conhecimento extraído do conjunto de dados
  - Vantagens
    - Favorece a interpretabilidade por seres humanos
    - O processo de tomada de decisão do modelo é mais compreensível e transparente (*explainable machine learning*)
    - Inferência lógica
  - Desvantagens
    - Menor acurácia preditiva em comparação aos modelos "caixa-preta"
- **Modelos baseados em árvores**
  - **Classificação** (árvores de decisão) e **regressão** (árvores de regressão)
    - A interpretação dos modelos e implementação dos algoritmos construtores de ambas são similares
  - Recursividade
  - Divisão e conquista
  - Nós de divisão (testes condicionais com base nos valores dos atributos) e folha (valores da variável alvo)
  - **Regras de divisão em tarefas de classificação**
    - Minimizar a **impureza** e a heterogeneidade dos subconjuntos e, consequentemente, maximizar a homogeneidade dos dados que os compõem
    - Seleção dos atributos que melhor discriminam cada classe (*goodness of split*)
    - **Ganho de informação**
      - **Entropia**
        - Medida da desordem ou impureza do conjunto de dados
        - A aleatoriedade de uma variável dificulta sua predição
      - Exprime a redução da aleatoriedade/incerteza pela diferença da entropia de todo o conjunto de dados e a dos subconjuntos
    - **Índice de Gini**
      - Medida do grau de desigualdade de uma distribuição estatística
      - Medida de impureza dos nós de decisão (subconjuntos)
      - Avalia a probabilidade de que exemplos escolhidos ao acaso pertençam a classes diferentes, mas tenham sido classificados no mesmo subconjunto
  - **Regras de divisão em tarefas de regressão**
- **Modelos baseados em regras**

## Referências complementares

CORMEN, Thomas H.; LEISERSON, Charles E.; RIVEST, Ronald L.; STEIN, Clifford. **Algoritmos: teoria e prática**. Trad. Arlete Simille Marques. 3. ed. Rio de Janeiro: Elsevier, 2012.

HOFFMANN, Rodolfo. **Estatística para economistas**. 4. ed. São Paulo: Pioneira Thomson Learning, 2006.

## Notas

[^1]: Neste contexto, o termo **símbolo** refere-se à abstração de conceitos, objetos ou relações do mundo real, que propriamente os representam ou a suas características e estados. Por conseguinte, **estruturas simbólicas** são agrupamentos desses elementos fundamentais, de modo a representar conhecimentos e relacionamentos mais complexos.

[^2]: A literatura comumente utiliza a expressão "caixa-preta" (*black box*) para se referir a modelos cujo processo decisório não é facilmente inferível ou interpretável por seres humanos, como é o caso das redes neurais artificiais. A propósito, vide o fichamento [1.2](../neural-networks-and-learning-machines-simon-haykin/_introduction.md), que contém algumas referências à terminologia no âmbito das redes neurais, em especial as [notas](../neural-networks-and-learning-machines-simon-haykin/_introduction.md#notas) 1 e 19.

[^3]: Ver o [suplemento 3](../../suplementos/03-estruturas-de-dados.md), sobre estruturas de dados, para informações adicionais sobre **árvores**.

[^4]: A **recursividade** é uma característica de determinados algoritmos de se chamarem a si mesmos, uma ou mais vezes, a fim de fracionar um problema em tantos problemas menores quantos forem necessários, até que seja possível resolver o problema original. Normalmente, isso é feito por meio da abordagem da **divisão e conquista**, que em cada nível de recursão aplica três etapas: divisão, conquista e combinação (Cormen et al., 2012).

[^5]: No livro, os autores utilizam o termo árvore de decisão para se referir, indistintamente, às árvores de decisão ou de regressão, inclusive neste caso, dado que a interpretação dos modelos e a indução da árvore são bastante similares. Todavia, ressalvam que, se necessária, haverá a devida distinção.

[^6]: Na Economia, o **índice de Gini** é uma **medida de desigualdade** muito empregada para analisar a distribuição de renda, mas que pode ser usada para medir o grau de desigualdade de qualquer distribuição estatística, definido como a razão entre a **área de desigualdade**, obtida entre a **linha da perfeita igualdade** e a **curva de Lorenz**, e a área do triângulo formado pelos eixos do gráfico e a linha de perfeita igualdade (Hoffmann, 2006). Analogicamente, no contexto da aprendizagem de máquina, é possível trasladar esse raciocínio para a desigualdade — leia-se heterogeneidade — da distribuição dos elementos em um conjunto ou subconjunto de dados.
