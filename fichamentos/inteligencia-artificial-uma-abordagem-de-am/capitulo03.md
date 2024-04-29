# # 2.3 Capítulo 3 (p. 28/48)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 1 | Preparação de dados (capítulos 2 e 3)

### 3. Pré-processamento de dados

O pré-processamento de dados engloba o uso de uma ou mais técnicas com o objetivo fundamental de aperfeiçoar a qualidade dos dados para a posterior alimentação dos algoritmos de aprendizagem de máquina. Essa etapa é necessária porque os "conjuntos de dados podem apresentar diferentes características, dimensões ou formatos" (FACELI et al., 2023, p. 28), além de problemas que dificultem, desaconselhem ou mesmo impeçam o uso em sua forma bruta.

De fato, o pré-processamento é importante porque o estado e a qualidade dos dados afeta diretamente o desempenho dos algoritmos de aprendizagem.

De modo geral, podem ser elencas as seguintes vantagens no pré-processamento de dados:

>"[...] facilitar o uso de técnicas de AM, levar à construção de modelos mais fiéis à distribuição real dos dados, reduzindo sua complexidade computacional, tornar mais fáceis e rápidos o ajuste de parâmetros do modelo e seu posterior uso. [...] adicionalmente, facilitar a interpretação dos padrões extraídos pelo modelo. Técnicas de pré-processamento de dados são úteis não apenas porque podem minimizar ou eliminar problemas existentes em um conjunto de dados, mas também porque podem tornar os dados mais adequados para sua utilização por um determinado algoritmo de AM." (FACELI et al., 2023, p. 28).

#### 3.1 Integração de dados

Esta técnica atende, essencialmente, a duas finalidades distintas: combinar diferentes fontes de dados, e consequentemente mais de um conjunto de dados, e assegurar a integridade dos dados, e desse modo a sua confiabilidade, ao impedir que um mesmo atributo de determinado objeto seja representado mais de uma vez, em conjuntos diversos, e/ou que um dado objeto tenha seus atributos fragmentados em diferentes conjuntos.

Nesse sentido, o **problema de identificação de entidade** é enfrentado "[...] por meio da busca por atributos comuns nos conjuntos a serem combinados" (FACELI et al., 2023, p. 29), de sorte que "[...] os objetos dos diferentes conjuntos que possuem o mesmo valor para o atributo [...] são combinados em um único objeto do conjunto integrado. [Esses atributos] deve(m) ter um valor único para cada objeto." (FACELI et al., 2023, p. 29).

Uma das formas de contornar eventuais dificuldades ao se implementar esta técnica é por meio de metadados, que "[...] são dados sobre dados que, ao descrever as suas principais características, podem ser utilizados para evitar erros no processo de integração. [Se isso for feito] O processo de integração origina um depósito ou repositório de dados (*data warehouse*), que funciona como uma base de dados centralizada." (FACELI et al., 2023, p. 29).

#### 3.2 Eliminação manual de atributos

É sabido que objetos com grande quantidade de atributos podem comprometer o desempenho dos algoritmos de aprendizado. Ademais, há que se ponderar sobre a "[...] relevância dos atributos para o problema que está sendo tratado [o que] também é essencial para a qualidade dos resultados" (FACELI et al., 2023, p. 29), pois há situações nas quais somente alguns deles serão realmente úteis, ao passo que os demais podem ser descartados pela irrelevância para certa tarefa.

Por esse motivo, ressalvadas as obviedades, "o conjunto de atributos que formarão o conjunto de dados a ser analisado é geralmente definido de acordo com a experiência de especialistas no domínio dos dados" (FACELI et al., 2023, p. 29) ou por meio de técnicas de seleção de atributos irrelevantes.

#### 3.3 Amostragem de dados

A depender do algoritmo utilizado, a grande quantidade de objetos/instâncias/exemplos em um conjunto de dados pode ser uma condição indesejada. Nesse sentido,

>"associado ao número de objetos em um conjunto de dados, existe um balanço entre eficiência computacional e acurácia (taxa de predições corretas). Quanto mais dados são utilizados, maior tende a ser a acurácia do modelo e menor a eficiência computacional do processo indutivo, pois um número muito grande de objetos pode tornar o tempo de processamento muito longo. [Por esse motivo] Para se obter um bom compromisso entre eficiência e acurácia, geralmente trabalha-se com uma amostra ou subconjunto de dados." (FACELI et al., 2023, p. 30).

Contudo, esse balanço deve ser cuidadosamente ponderado a fim de assegurar a representatividade da amostra, de modo que a partir dela seja possível obter resultados idênticos àqueles que de outra forma já seriam verificados, isto é, "[...] o uso da amostra [deve] leva[r] ao mesmo desempenho obtido com o uso do conjunto completo, porém com um custo computacional muito menor." (FACELI et al., 2023, p. 30). Logo, em linhas gerais, pode-se dizer que a melhor amostragem é aquela que preserva a distribuição estatística original e, ao mesmo tempo, reduza o tamanho da amostra a ponto de gerar economia relevante em termos de recursos computacionais.

Por conseguinte, a amostra extraída deve ser capaz de estimar com razoabilidade a "[...] informação contida na população original, permitindo tirar conclusões de um todo a partir de uma parte." (FACELI et al., 2023, p. 30).

Dentre as formas de extração, menciona-se a amostragem aleatória simples, a amostragem estratificada e a amostragem progressiva[^1].

#### 3.4 [Balanceamento de] Dados desbalanceados

O balanceamento de dados necessariamente pressupõe que o modelo implementará uma tarefa de classificação e que, dentre os objetos dos dados de entrada, a frequência de determinada classe é significativamente maior do que a de outra, tal que faça sentido distingui-los de maneira binária entre classes majoritária e minoritária. Sendo o caso, para que não seja necessário balancear o conjunto original, "[...] a acurácia preditiva [...] deve ser maior que a acurácia obtida atribuindo todo novo objeto à classe majoritária" (FACELI et al., 2023, p. 31), sob pena de que o modelo perca desempenho.

Com efeito, "quando alimentados com dados desbalanceados, esses algoritmos tendem  a favorecer a classificação de novos dados na classe majoritária. Se for possível gerar novos dados pelo mesmo processo que originou o conjunto atual, o conjunto de dados pode ser naturalmente balanceado. Na maioria das aplicações práticas, no entanto, isso não é possível." (FACELI et al., 2023, p. 31).

Dentre as formas mais utilizadas para enfrentar o problema do desbalanceamento de dados estão a (a) **redefinição do tamanho do conjunto de dados**, que pode ser feita pela (a.i) adição de novos objetos à classe minoritária ou (a.ii) pela retirada de exemplos da minoritária. Aquela solução envolve os riscos de (a.i.i) incorporar casos impossíveis ao modelo e/ou (a.i.ii) enviesá-lo a ponto de provocar o superajustamento aos dados de treino e, por conseguinte, o comprometimento da capacidade de generalização (*overfitting*); esta, por sua vez, pode acabar por (a.ii.i) ignorar dados importantes tal que comprometa a capacidade preditiva do modelo, culminando em subajustamento (*underfitting*). Outras abordagens possíveis são a (b) **criação de funções de custo específicas para cada classe**, opção que é obstaculizada pela dificuldade (b.i) no cálculo de tais custos e (b.ii) na implementação dessa lógica nos algoritmos, e a (c) **indução de modelos específicos**, em que cada classe é aprendida separadamente.

#### 3.5 Limpeza de dados

Dizem respeito a formas de atenuar ou eliminar problemas associados a dados ruidosos, incompletos, inconsistentes ou redundantes. "Essas deficiências nos dados podem ser causadas por problemas nos equipamentos que realizam a coleta, a transmissão e o armazenamento dos dados ou problemas no preenchimento ou na entrada dos dados por seres humanos." (FACELI et al., 2023, p. 32). O objetivo é **aumentar a qualidade** dos dados para otimizar o desempenho dos algoritmos de aprendizagem, pois mesmo aqueles que conseguem lidar com certas imperfeições costumam se beneficiar do uso de dados mais limpos.

##### 3.5.1 Dados incompletos

Os valores de alguns atributos de alguns dos objetos estão ausentes. Dentre as possíveis soluções, destacam-se a (a) **eliminação de objetos**, especialmente se o atributo em questão for indicativo da classe, mas desaconselhada se o problema afetar poucos atributos de um mesmo objeto, quando a quantidade de atributos ausentes variar muito entre os objetos ou quando houver muitos objetos com atributos faltantes; a (b) **inserção manual de atributos**, inviável se houver muitos deles; e a (c) **implementação de um método para definição automática**, o que pode ser feito (c.i) pela definição de um valor indicativo de que aquele atributo estava anteriormente vazio, o que pode levar à valoração equivocada da relevância desse atributo para o conjunto de dados, (c.ii) pelo uso de medidas estatísticas de frequência ou tendência central ou (c.iii) pela indução a partir do valor dos demais atributos presentes.

##### 3.5.2 Dados inconsistentes

Ocorre quando os atributos explicitam valores contraditórios ou conflitantes, tanto entre os atributos do conjunto de entrada comparados entre si, quanto entre o conjunto de entrada e o valor do atributo de saída. São bem evidentes quando há violação de relações conhecidas entre os atributos.

##### 3.5.3 Dados redundantes

Diz-se dos **objetos** que apresentem grande semelhança entre si, assim considerados aqueles cujos atributos têm valores muito próximos ou iguais a outro objeto, bem como de **atributos** com valores idênticos ou que possam ser deduzidos a partir de outro(s), pois "[...] têm a mesma informação preditiva." (FACELI et al., 2023, p. 36). A eliminação da redundância é importante para evitar a supervalorização de determinado aspecto do conjunto e para economizar recursos computacionais. "A redundância de um atributo está relacionada com a sua correlação com um ou mais atributos do conjunto de dados. Dois ou mais atributos estão correlacionados quando apresentam um perfil de variação semelhante para os diferentes objetos. Quanto mais correlacionados os atributos, maior o grau de redundância. Se a correlação ocorrer entre um atributo de entrada e um atributo rótulo, esse atributo de entrada terá uma grande influência na predição do valor do atributo rótulo." (FACELI et al., 2023, p. 36).

##### 3.5.4 Dados com ruídos

#### 3.6 Transformação de dados

##### 3.6.1 Conversão simbólico-numérico

##### 3.6.2 Conversão numérico-simbólico

##### 3.6.3 Transformação de atributos numéricos

#### 3.7 Redução de dimensionalidade

<!-- Um conjunto de dados grande não necessariamente é aquele que possui muitos objetos, mas também aquele que, embora os tenha em pequena quantidade, cada um deles possui muitos atributos. Ambas as situações são capazes de comprometer o desempenho dos algoritmos de AM e, por esse motivo, podem ser enfrentadas com o auxílio desta técnica. (maldição da dimensionalidade - VER) -->

##### 3.7.1 Agregação

##### 3.7.2 Seleção de atributos

##### 3.7.3 Técnicas de ordenação

##### 3.7.4 Técnicas de seleção de subconjunto

## Principais tópicos

- Pré-processamento de dados
  - Melhorar a qualidade dos dados
- **Técnicas de pré-processamento**
  - **Integração de dados**
    - Combinação de duas ou mais fontes diferentes
    - Assegurar a integridade dos dados
      - Problema de identificação de entidade
  - **Eliminação manual de atributos**
    - Descarte de atributos irrelevantes
  - **Amostragem de dados**
    - Redução do tamanho do conjunto de dados
    - Preservação da representatividade da amostra
    - Dilema eficácia computacional *versus* acurácia
    - Elaborar conclusões sobre o todo a partir de uma parte
  - **Balanceamento de dados desbalanceados**
    - Tarefa de classificação
    - Classes majoritária e minoritária
    - Maior frequência de uma classe
    - Abordagens
      - Redefinição do tamanho do conjunto de dados
      - Funções de custo para cada classe
      - Indução de modelos por classe
  - **Limpeza de dados**
    - Dados ruidosos, incompletos, inconsistentes ou redundantes
    - Aumentar a qualidade dos dados
  - **Transformação de dados**
  - **Redução de dimensionalidade**

## Notas

[^1]: Na seção 3.3, os autores distinguem essas abordagens. No entanto, optei por não incluir esses pontos neste momento, uma vez que pretendo estudá-los mais adiante em livros de Estatística.
