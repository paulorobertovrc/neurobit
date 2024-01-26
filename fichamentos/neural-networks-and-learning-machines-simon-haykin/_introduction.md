# # 1.2

![Static Badge](https://img.shields.io/badge/Fase-Escrevendo-grey?labelColor=5F9EA0)

## Introdução (p. 1/46)

### Definição de rede neural

Desde o início, o estudo das redes neurais artificiais foi pautado pela observação de que tanto o cérebro humano quanto os computadores convencionais são sistemas de processamento de informações[1] e, por conseguinte, realizam trabalho computacional[2]. Não apenas seu funcionamento é bastante distinto, mas a capacidade computacional do cérebro - não só humano, mas também o de outros animais - supera, em muito, a dos computadores digitais.

O cérebro é um sistema de processamento de informações complexo, não linear e paralelo[3]. Suas estruturas fundamentais são os neurônios, organizados de modo a realizar tarefas computacionais, a exemplo do reconhecimento de padrões. Portanto, assim no cérebro como nas redes artificiais, os neurônios constituem as unidades de processamento da informação.

A plasticidade[4], característica que permite a adaptação do indivíduo ao ambiente em que está inserido, também é importante para as redes neurais artificiais.

Em linhas gerais, pode-se dizer que uma rede neural artificial é um modelo computacional inspirado no modo como o cérebro realiza o processamento de informações. Nas palavras de Haykin (2009, p. 2), "[...] a neural network is a machine that is designed to model the way in which the brain performs a particular task or function of interest".

Já como definição formal, o autor dá às redes neurais, vistas como uma máquina adaptativa[5], o seguinte conceito:

> A neural network is a massively parallel distributed processor made up of simple processing units that has a natural propensity for storing experiential knowledge and making it available for use. It resembles the brain in two respects:
> 1. Knowledge is acquired by the network from its environment through a learning process.
> 2. Interneuron connection strengths, known as synaptic weights, are used to store the ac-
quired knowledge. (HAYKIN, 2009, p. 2)

Em português, conforme definição dada na edição anterior do livro:
> Uma rede neural é um processador maciçamente paralelamente distribuído constituído de unidades de processamento simples, que tem uma propensão natural para armazenar conhecimento experimental e torná-lo disponível para uso. Ela se assemelha ao cérebro em dois aspectos:
> 1. O conhecimento é adquirido pela rede a partir de seu ambiente através de um processo de aprendizagem.
> 2. Forças de conexão entre os neurônios, conhecidas como pesos sinápticos, são utilizadas para armazenar o conhecimento adquirido. (HAYKIN, 2001, p. 28)

Assim, na medida do possível, as redes neurais artificiais assemelham-se e são modeladas à luz do cérebro humano [interconexão de unidades computacionais simples - neurônios - assim no cérebro biológico, como nas redes neurais artificiais].

O processo de aprendizagem - **algoritmo de aprendizagem** - tradicionalmente aplicado em redes neurais consiste na **modificação dos pesos sinápticos** das conexões neuronais e deve necessariamente resultar em **atividade computacional útil**, ou seja, o alcance do objetivo almejado.

A rede neural pode alterar sua própria estrutura (topologia).

Conforme o autor, a técnica de modificação dos pesos sinápticos guarda muita similaridade com a teoria dos filtros adaptativos lineares (*linear adaptive filter theory*) [6].

#### Benefícios das redes neurais

A capacidade computacional das redes neurais é resultado de sua estrutura massiva e paralelamente distribuída, bem como da habilidade de aprender e generalizar. "A generalização se refere ao fato de a rede neural produzir saídas adequadas para entradas que não estavam presentes durante o treinamento (aprendizagem). Estas duas capacidades de processamento de informação [aprender e generalizar] tornam possível para as redes neurais resolver problemas complexos (de grande escala) que são atualmente intratáveis." (HAYKIN, 2001, p. 28) [da 2 edição, em português].

> A generalização se refere ao fato de a rede neural produzir saídas adequadas para entradas que não estavam presentes durante o treinamento (aprendizagem) (HAYKIN, 2001, p. 28).

> Generalization refers to the neural network's production of reasonable outputs for inputs not encountered during training (learning) (HAYKIN, 2009, p. 2).

São produzidas saídas (*outputs*) adequadas para as entradas (*inputs*) fornecidas - *good approximate solutions*, do original em inglês (Haykin, 2009). Atualmente, o problema grande e complexo deve ser decomposto em problemas menores, os quais redes neurais de propósito específico têm capacidade de resolver.

Principais capacidades e propriedades das redes neurais artificiais (p. 2/6):

- Não linearidade (embora individualmente os neurônios artificiais possam ser lineares ou não lineares);
- Mapeamento de entrada e saída (na aprendizagem supervisionada);
- Adaptabilidade (capacidade de modificar os pesos sinápticos);
  - **Dilema estabilidade x plasticidade:** "Para aproveitar todos os benefícios da adaptabilidade, as constantes de tempo principais do sistema devem ser grandes o suficiente para que o sistema ignore perturbações espúrias mas ainda assim serem suficientemente pequenas para responder a mudanças significativas no ambiente" (HAYKIN, 2001, p. 30).
- Resposta a evidências (não apenas classificar o padrão adequadamente, mas informar o nível de confiabilidade da escolha, rejeitando ambiguidade);
- Informação contextualizada ("O conhecimento é representado pela própria estrutura e estado de ativação de uma rede neural." (HAYKIN, 2001, p. 30));
- Tolerância a falhas (devido à sua estrutura massiva e paralelamente distribuída);
- Implementação em VSLI (*very-large-scale-integration*)[7];
- Uniformidade de análise e projeto ("[...] as redes neurais desfrutam de universalidade como processadores de informação" (HAYKIN, 2001, p. 30));
- Analogia neurobiológica (motivadas por estruturas biológicas do cérebro humano).

### O cérebro humano[8]

O sistema nervoso humano pode ser visto como um sistema de três estágios, do qual fazem parte cérebro, receptores e atuadores. Os estímulos - entrada (*input*) do sistema - são captados e convertidos em sinais elétricos pelos receptores; o cérebro continuamente recebe e processa esses sinais; os atuadores convertem os sinais recebidos de modo a gerar as ações (respostas) apropriadas, que constituem a saída (*output*) do sistema. A informação captada é transmitida em um único sentido - receptor > cérebro > atuador -, mas o sistema se retroalimenta no sentido oposto dessa transmissão - atuador > cérebro > receptor (*feedback*).

Foi o trabalho de Santiago Ramón y Cajal que, em 1911, introduziu o neurônio como estrutura fundamental do cérebro. Os neurônios são cinco a seis ordens de grandeza mais lentos do que os circuitos digitais e, ainda assim, o cérebro é muito mais eficiente do que computadores em termos de eficiência energética. Provavelmente, isso é resultado da enorme quantidade de células neuronais e à massiva interconexão entre elas - a eficiência energética do cérebro humano é de $10^{-16}$ joules por operação por segundo. Eles se apresentam sob diversas formas e tamanhos, sendo que um dos mais comuns é a denominada célula piramidal, e se organizam na anatomia cerebral em diversos níveis e em pequena ou grande escala.

Essa estrutura hierárquica vai, em menor nível, das moléculas responsáveis pelas sinapses ao próprio sistema nervoso central, último nível hierárquico. A estrutura completa é apresentada por Haykin (2009, p. 9), na figura 3, da seguinte forma: moléculas > sinapses > microcircuitos neurais > árvore dendrítica > neurônio > circuitos locais > circuitos regionais > sistema nervoso central.

> The synapses represent the most fundamental level, depending on molecules and ions for their action. [...] A neural microcircuit refers to an assembly of synapses organized into patterns of connectivity to produce a functional operation of interest. A neural microcircuit may be likened to a silicon chip made up of an assembly of transistors. At the next level of complexity, we have local circuits [...] made up of neurons with similar or different properties; there neural assemblies perform operations characteristic of a localized region in the brain. They are followed by interregional circuits made up of pathways, columns, and topographic maps, which involve multiple regions located in different parts of the brain.
> Topographic maps are organized to respond to incoming sensory information. These maps are often arranged in sheets, [...] stacked in adjacent layers in such a way that stimuli from corresponding points in space lie above or below each other. [...] different sensory inputs [...] are mapped onto corresponding areas of the cerebral cortex in an orderly fashion. At the final level of complexity, the topographic maps and other interregional circuits mediate specific types of behavior in the central nervous system. (HAYKIN, 2009, p. 7/9)

O equivalente, na 2 edição, em português:
> As sinapses representam o nível mais fundamental, dependente de moléculas e íons para sua ação. [...] Um microcircuito neural se refere a um agrupamento de sinapses organizadas em padrões de conectividade para produzir uma operação funcional de interesse. Um microcircuito neural pode ser comparado a um circuito de silício constituído por um agrupamento de transistores. [...] No nível seguinte de complexidade nós temos circuitos locais [...] constituídos por neurônios com propriedades similares ou diferentes; estes agrupamentos neurais realizam operações características de uma região localizada no cérebro. Eles são seguidos por circuitos inter-regionais constituídos por caminhos, colunas e mapas topográficos, que envolvem regiões múltiplas localizadas em partes diferentes do cérebro.
> Os mapas topográficos são organizados para responder à informação sensorial incidente. Estes mapas são frequentemente arranjados em folhas, [...] empilhados em camadas adjacentes de tal modo que estímulos advindos de pontos correspondentes no espaço se localizem acima ou abaixo de cada um deles. [...] diferentes entradas sensoriais [...] são mapeadas sobre áreas correspondentes do córtex cerebral de forma ordenada. No nível final de complexidade, os mapas topográficos e outros circuitos inter-regionais medeiam tipos específicos de comportamento no sistema nervoso central. (HAYKIN, 2001, p. 33/36)

As sinapses são unidades estruturais e funcionais elementares responsáveis por intermediar a comunicação entre neurônios[9] e, em maioria, são químicas. Nelas, um sinal elétrico pré-sináptico é transformado em sinal químico pela liberação de neurotransmissores, e depois se converte novamente em sinal elétrico, pós-sináptico (Shepherd; Koch, 1990 *apud* Haykin, 2009). "Nas descrições tradicionais da organização neural, assume-se que uma sinapse é uma conexão simples que pode impor ao neurônio receptivo excitação ou inibição, mas não ambas." (HAYKIN, 2001, p. 33). **O surgimento de novas sinapses ou a modificação das já existentes são os mecanismos responsáveis pela plasticidade cerebral e, consequentemente, pela aprendizagem.**

A saída (*output*) do processamento neuronal são, no mais das vezes, impulsos elétricos denominados **potenciais de ação**[10] ou ***spikes*** - na 2 edição, em português, o termo é traduzido como **impulso**.

### Modelos de neurônio [artificial]

Em sua forma mais rudimentar, o modelo de um neurônio artificial possui três elementos básicos: um **conjunto de sinapses ou elos de ligação (*synapses or connecting links*)**, cada um com seu próprio peso ou força (peso sináptico/*synaptic weight*)[11]; um **somador (*adder*)**; e uma **função de ativação (*activation function*)**.

Eis a ilustração do modelo (HAYKIN, 2009, p. 11):
![Modelo de neurônio artificial](./images/03_neuronio_artificial_nao_linear_basico.png)

Depreende-se que um sinal de **entrada** - representado pela letra $x$ - é direcionado à sinapse - representada pela letra $j$ -, que está conectada ao neurônio - representado pela letra $k$ - e que, por sua vez, possui um peso sináptico - representado pela letra $w$. Noutras palavras, considerados quaisquer índices, diz-se que "[...] um sinal $x_j$ na entrada da sinapse $j$ conectada ao neurônio $k$ é multiplicada pelo peso sináptico $w_{kj}$. [...] O primeiro índice se refere ao neurônio em questão e o segundo se refere ao terminal de entrada da sinapse à qual o peso se refere." (HAYKIN, 2001, p. 36).

O somatório dos sinais de entrada ponderados pelos pesos sinápticos de cada neurônio pode, ou não, executar a função de ativação, que visa "restringir a amplitude da saída de um neurônio. A função de ativação é também referida como *função restritiva* já que restringe (limita) o intervalo permissível de amplitude do sinal de saída a um valor finito. Tipicamente, o intervalo normalizado da amplitude da saída de um neurônio é escrito como o intervalo unitário fechado [0, 1] ou alternativamente [-1, 1]" (HAYKIN, 2001, p. 37). Na terminologia em inglês, a dita função restritiva é denominada *squashing function* (HAYKIN, 2009, p. 10).

O resultado - saída/*output* - do cálculo realizado pelo somador (na figura, *summing junction*) descreve um **combinador linear (*linear combiner*)**, representado pela letra $u$ (não aparece no modelo acima), que consiste na soma dos valores da entrada do sistema multiplicada pelo peso sináptico do neurônio.

Pode ser considerado no cálculo o ***bias*** (**viés**, em tradução literal), que "tem o efeito de aumentar ou diminuir a entrada líquida da função de ativação, dependendo se ele é positivo ou negativo, respectivamente" (HAYKIN, 2001, p. 37). No modelo acima, é representado por $b_k$, do que se infere que **cada neurônio pode ter um viés específico**. Tem-se, ainda, que o *bias* aplica uma **transformação afim** (*affine transformation*, em inglês) **à saída do somador, que equivale à entrada líquida da função de ativação.**

A saída do combinador linear - $u_k$ -, após a incidência do *bias* - $b_k$ -, se for o caso, é a **entrada líquida (*net input*) da função de ativação**. Esta, por sua vez, é representada na imagem por $\phi(\cdot)$ e sua aplicação resulta na saída (*output*) do próprio neurônio, representada pela letra $y$.

Portanto, **para o neurônio $k$, sua saída é dada por $y_k = \phi(u_k + b_k)$, cujos parâmetros são a saída do combinador linear ($u_k$) e o *bias* do neurônio ($b_k$).**

Até aqui, a representação matemática do neurônio $k$ é dada por:

$$
u_k = \sum_{j=1}^{m} w_{kj}x_j
$$

e

$$
y_k = \phi(u_k + b_k)
$$

#### Funções de ativação

#### Modelo estocástico de neurônio

### Redes neurais como grafos dirigidos

### Feedback

### Arquiteturas de redes neurais

### Representação do conhecimento

#### Regras

#### Informação prévia no projeto de uma rede neural

#### Invariâncias no projeto de uma rede neural

### Processos de aprendizagem

### Tipos de aprendizagem

## Principais conceitos/definições/ideias extraídos do texto original

- **Definição de rede neural**
  - O cérebro é um sistema de processamento de informações complexo, não linear e paralelo, com capacidade computacional muito superior à dos computadores digitais convencionais.
  - As redes neurais artificiais são inspiradas no cérebro humano e a ele se assemelham na medida em que compostas por neurônios artificiais interconectados.
  - A plasticidade é uma característica importante tanto no cérebro quanto nas redes neurais artificiais e é ela que assegura a adaptação do indivíduo ao ambiente e a capacidade de aprender.
  - Em redes biológicas ou artificiais, os neurônios são a unidade de processamento de informação e, portanto, responsáveis pelo trabalho computacional.
  - Uma rede neural artificial modela o modo como o cérebro biológico realiza determinada tarefa ou função.
  - O processo de aprendizagem tradicional consiste na modificação dos pesos sinápticos da rede neural artificial.

- **Benefícios das redes neurais**
  - Massiva e paralelamente distribuída.
  - Habilidade de aprender e generalizar.
  - Produz saídas (*outputs*) adequadas para as entradas (*inputs*) fornecidas.
  - Principais características:
    - Não linearidade (embora individualmente os neurônios artificiais possam ser lineares ou não lineares);
    - Mapeamento de entrada e saída (na aprendizagem supervisionada);
    - Adaptabilidade (capacidade de modificar os pesos sinápticos);
    - Resposta a evidências (não apenas classificar o padrão adequadamente, mas informar o nível de confiabilidade da escolha, rejeitando ambiguidade);
    - Informação contextualizada ("O conhecimento é representado pela própria estrutura e estado de ativação de uma rede neural." (HAYKIN, 2001, p. 30));
    - Tolerância a falhas (devido à sua estrutura massiva e paralelamente distribuída);
    - Implementação em VSLI (*very-large-scale-integration*) [6];
    - Uniformidade de análise e projeto ("[...] as redes neurais desfrutam de universalidade como processadores de informação" (HAYKIN, 2001, p. 30));
    - Analogia neurobiológica (motivadas por estruturas biológicas do cérebro humano).

- **O cérebro humano**
  - Uma das formas de se enxergar o sistema nervoso do ser humano é como um sistema de três estágios composto por cérebro, receptores e atuadores. Os sinais de entrada (*input*) desse sistema são os estímulos externos e/ou internos que são captados pelos receptores e, submetidos ao dito sistema, tem-se como saída (*output*) alguma resposta que pode variar desde a mera percepção a um movimento corporal.
  - Os neurônios, estruturas fundamentais do cérebro humano, comunicam-se entre si por meio do processo denominado transmissão sináptica. A sinapse é o local onde essa comunicação ocorre e pode ser, basicamente, elétrica ou química.
    - O potencial de ação é a saída (*output*) do processamento neuronal.
    - O surgimento de novas conexões entre os neurônios ou a modificação das já existentes são os mecanismos responsáveis pela plasticidade cerebral e, consequentemente, pela aprendizagem.
    - O potencial de ação (*spike* ou impulso) é a saída (*output*) do processamento neuronal.
  - Anatomicamente, o cérebro se organiza em níveis hierárquicos.
  - Regiões específicas do cérebro são responsáveis por determinadas funções, mas não necessariamente de forma isolada, pois há casos em que um único resultado decorre da ativação de mais de uma região cerebral, que interagem entre si para produzi-lo.
    - Isso ocorre porque o cérebro é vastamente interconectado.

- **Modelos de neurônio**
  - Elementos básicos: um conjunto de sinapses ou elos de ligação (*synapses or connecting links*), cada um com seu próprio peso ou força; um somador (*adder*); e uma função de ativação (*activation function*). Pode ser aplicado outro elemento chamado viés (*bias*), igualmente relativo a cada neurônio.
    - Cada neurônio pode ter seu próprio *bias*.

## Notas

<!-- [1] DEFINIR INFORMAÇÃO -->

[2] A palavra computar significa "fazer o cômputo de; calcular; orçar; contar; processar através de computadores". Fonte: [Dicionário Priberam da Língua Portuguesa](https://dicionario.priberam.org/computar).

[3] Sobre o **processamento em paralelo**, das Neurociências colhe-se que, ao que parece, os comportamentos humanos de maior complexidade não decorrem da sinalização de um único neurônio, mas pela ação de muitos não necessariamente localizados na mesma região cortical (Kandel et al., 2014).
> O envolvimento de vários grupos neurais ou rotas para transmitir uma informação similar é chamado *processamento em paralelo*. O processamento em paralelo também ocorre em uma única via quando diferentes neurônios nessa via executa ações similares simultaneamente. [...] O campo da ciência computacional conhecido como inteligência artificial originalmente usou o processamento serial para simular os processos cognitivos do encéfalo [...] Esses modelos seriais executavam muitas tarefas de forma adequada, inclusive jogar xadrez. Entretanto, eram muito ruims em outras tarefas que o encéfalo faz quase instantaneamente, com o reconhecimento de faces ou a compreensão do discurso. [...] Nesses modelos [redes neurais], elementos do sistema processam a informação simultaneamente usando conexões de pró-ação e de retroalimentação. É interessante observar que, em sistemas com circuitos de retroalimentação é a atividade dinâmica do sistema que determina o desfecho do processamento, não as aferências ou condições iniciais. Modelos de redes neurais capturam bem a arquitetura altamente recorrente da maioria dos circuitos neurais reais e também a capacidade do encéfalo de funcionar na ausência de uma aferência sensorial específica vinda de fora do corpo [...] Modelos de redes neurais também demonstram que a análise de elementos individuais de um sistema pode não ser suficiente para decodificar a *mensagem dos potenciais de ação*. De acordo com tal visão de redes neurais, o que faz o encéfalo ser um deslumbrante órgão que processa a informação não é a complexidade de seus neurônios, mas o fato de ter muitos elementos interconectados de várias formas complexas." (KANDEL et al., 2014, p. 32/33)

[4] Vide complemento [plasticidade](../../complementos/plasticidade.md).

<!-- [5] CONCEITUAR MÁQUINA ADAPTATIVA -->

<!-- [6] A **teoria dos filtros adaptativos lineares (*linear adaptative filter theory*)** CONCEITUAR ..... -->

[7] VLSI, do inglês *Very Large Scale Integration*, é um processo de fabricação de circuitos eletrônicos integrados com altíssima quantidade de transistores em um único chip.

[8] [10] Vide complemento [sistema nervoso, encéfalo e neurônio](../../complementos/sistema_nervoso_encefalo_neuronio.md) para consulta mais detalhada sobre o assunto, a partir de referências da literatura de Neurociências.

[9] A sinapse é uma região específica, ao passo que ao processo de comunicação entre neurônios dá-se o nome de transmissão sináptica (Kandel et al., 2004). Nesse sentido, "o local especializado em que um neurônio se comunica com outro é chamado de sinapse [...]" (KANDEL et al., 2014, p. 157).

[11] Em se tratando de peso sináptico, também referido como força sináptica, "[...] muitos modelos neurais estão equipados com processos dinâmicos que [se]reorganizam continuamente [...] criam ou eliminam neurônios ou suas conexões [...] ajustam as forças de conexões sinápticas existentes ou mudam outras propriedades dos neurônios. [...] O termo peso sináptico frequentemente é utilizado para se referir à força de determinada conexão sináptica, enquanto o termo matriz de pesos sinápticos aplica-se ao conjunto de todos os pesos sinápticos em uma rede. A força da sinapse do neurônio $j$ sobre o neurônio $i$ é descrita como $W_{ij}$. Esse é o elemento da matriz de pesos localizado na intersecção da linha $i$ com a coluna $j$." (KANDEL et al., 2014, p. 1387). O fenômeno da modificação dos pesos sinápticos é consequência da plasticidade - **regra de plasticidade sináptica** -, que Kandel et al. (2014) argumenta que não deve se confundida com a **regra da aprendizagem**, embora sejam comumente utilizadas como sinônimas, pois aprendizado é a "[...] expressão do comportamento de uma rede e não de uma única sinapse" (KANDEL et al., 2014, p. 1387). Nesse sentido, a **regra ou plasticidade *hebbiana***, em alusão a Donald Hebb, ensina que "[...] as sinapses são modificadas com base na atividade temporalmente contígua dos neurônios pré e pós-sinápticos" (KANDEL et al., 2014, p. 1387). Conforme Bear et al. (, p. 878), "Donald Hebb propôs que cada sinapse individual se torna um pouco mais forte quando participa com sucesso no disparo de um neurônio pós-sináptico", embora haja trabalhos no sentido de que a mudança do peso sináptico esteja mais proximamente relacionada ao neurônio pré-sináptico, apenas (Gallinaro; Scholl; Clopath, 2023) <!-- CONFIRMAR --> .

## Referências complementares consultadas durante o fichamento deste capítulo

BEAR, Mark F.; CONNORS, Barry W.; PARADISO, Michael A. **Neurociências: desvendando o sistema nervoso**. Trad. Carla Dalmaz et al. 4. ed. Porto Alegre: Artmed, 2017.

GALLINARO, Júlia V.; SCHOLL, Benjamin; CLOPATH, Claudia. 2023. **Synaptic weights that correlate with presynaptic selectivity increase decoding performance.** PLOS Computational Biology 19(8): e1011362. <https://doi.org/10.1371/journal.pcbi.1011362>.

KANDEL, Eric R.; SCHWARTZ, James H.; JESSELL, Thomas M.; SIEGELBAUM, Steven A.; HUDSPETH, A. J. **Princípios de neurociências**. Trad. Ana Lúcia Severo Rodrigues et al. 5. ed. Porto Alegre: AMGH, 2014.

VERY LARGE SCALE INTEGRATION. In: WIKIPEDIA. Disponível em <https://en.wikipedia.org/wiki/Very_Large_Scale_Integration>. Acesso em 22 jan. 2024.
