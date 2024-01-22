# # 1.2

![Static Badge](https://img.shields.io/badge/Fase-Escrevendo-grey?labelColor=5F9EA0)

## Introdução (p. 1/46)

### Definição de rede neural

Desde o início, o estudo das redes neurais artificiais foi pautado pela observação de que tanto o cérebro humano quanto os computadores convencionais são sistemas de processamento de informações[1] e, por conseguinte, realizam trabalho computacional[2]. Não apenas seu funcionamento é bastante distinto, mas a capacidade computacional do cérebro - não só humano, mas também o de outros animais - supera, em muito, a dos computadores digitais.

O cérebro é um sistema de processamento de informações complexo, não linear e paralelo [3]. Suas estruturas fundamentais são os neurônios, organizados de modo a realizar tarefas computacionais, a exemplo do reconhecimento de padrões. Portanto, assim no cérebro como nas redes artificiais, os neurônios constituem as unidades de processamento da informação.

A plasticidade[3], característica que permite a adaptação do indivíduo ao ambiente em que está inserido, também é importante para as redes neurais artificiais.

Em linhas gerais, pode-se dizer que uma rede neural artificial é um modelo computacional inspirado no modo como o cérebro realiza o processamento de informações. Nas palavras de Haykin (2009, p. 2), "[...] a neural network is a machine that is designed to model the way in which the brain performs a particular task or function of interest".

Já como definição formal, o autor dá às redes neurais, vistas como uma máquina adaptativa[4], o seguinte conceito:

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

Conforme o autor, a técnica de modificação dos pesos sinápticos guarda muita similaridade com a teoria dos filtros adaptativos lineares (*linear adaptative filter theory*) [5].

#### Benefícios das redes neurais

A capacidade computacional das redes neurais é resultado de sua estrutura massiva e paralelamente distribuída, bem como da habilidade de aprender e generalizar. "A generalização se refere ao fato de a rede neural produzir saídas adequadas para entradas que não estavam presentes durante o treinamento (aprendizagem). Estas duas capacidades de processamento de informação [aprender e generalizar] tornam possível para as redes neurais resolver problemas complexos (de grande escala) que são atualmente intratáveis." (HAYKIN, 2001, p. 28) [da 2 edição, em português].

> A generalização se refere ao fato de a rede neural produzir saídas adequadas para entradas que não estavam presentes durante o treinamento (aprendizagem) (HAYKIN, 2001, p. 28).

> Generalization refers to the neural network's production of reasonable outputs for inputs not encountered during training (learning) (HAYKIN, 2009, p. 2).

São produzidas saídas (*outputs*) adequadas para as entradas (*inputs*) fornecidas - *good approximate solutions*, do original em inglês (Haykin, 2009). Atualmente, o problema grande e complexo deve ser decomposto em problemas menores, os quais redes neurais de propósito específico têm capacidade de resolver.

Principais capacidades e propriedades das redes neurais artificiais (p. 2/6):

- Não linearidade (embora individualmente os neurônios artificiais possam ser lineares ou não lineares);
- Mapeamento de entrada e saída (na aprendizagem supervisionada);
- Adaptabilidade (capacidade de modificar os pesos sinápticos);
  - **Dilema estabilidade x plasticidade:** "Para aproveitar todos os benefícios da adaptabilidade, as constantes de tempo principais do sistema devem ser grandes o suficiente para que o sistema ignore perturbações espúriais mas ainda assim serem suficientemente pequenas para responder a mudanças significativas no ambiente" (HAYKIN, 2001, p. 30).
- Resposta a evidências (não apenas classificar o padrão adequadamente, mas informar o nível de confiabilidade da escolha, rejeitando ambiguidade);
- Informação contextualizada ("O conhecimento é representado pela própria estrutura e estado de ativação de uma rede neural." (HAYKIN, 2001, p. 30));
- Tolerância a falhas (devido à sua estrutura massiva e paralelamente distribuída);
- Implementação em VSLI (*very-large-scale-integration*) [6];
- Uniformidade de análise e projeto ("[...] as redes neurais desfrutam de universalidade como procesadores de informação" (HAYKIN, 2001, p. 30));
- Analogia neurobiológica (motivadas por estruturas biológicas do cérebro humano).

### O cérebro humano

### Modelos de neurônio

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

## Principais conceitos/definições/ideias

- Definição de rede neural
  - O cérebro é um sistema de processamento de informações complexo, não linear e paralelo, com capacidade computacional muito superior à dos computadores digitais convencionais.
  - As redes neurais artificiais são inspiradas no cérebro humano e a ele se assemelham na medida em que compostas por neurônios artificiais interconectados.
  - A plasticidade é uma característica importante tanto no cérebro quanto nas redes neurais artificiais e é ela que assegura a adaptação do indivíduo ao ambiente e a capacidade de aprender.
  - Em redes biológicas ou artificiais, os neurônios são a unidade de processamento de informação e, portanto, responsáveis pelo trabalho computacional.
  - Uma rede neural artificial modela o modo como o cérebro biológico realiza determinada tarefa ou função.
  - O processo de aprendizagem tradicional consiste na modificação dos pesos sinápticos da rede neural artificial.

- Benefícios das redes neurais
  - Massiva e paralelamente distribuída.
  - Habilidade de aprender e generalizar.
  - Produz saídas (*outputs*) adequadas para as entradas (*inputs*) fornecidas.
  - Principais características:
    - Não linearidade (embora individualmente os neurônios artificiais possam ser lineares ou não lineares);
    - Mapeamento de entrada e saída (na aprendizagem supervisionada);
    - Adaptabilidade (capacidade de modificar os pesos sinápticos);
      - **Dilema estabilidade x plasticidade:** "Para aproveitar todos os benefícios da adaptabilidade, as constantes de tempo principais do sistema devem ser grandes o suficiente para que o sistema ignore perturbações espúriais mas ainda assim serem suficientemente pequenas para responder a mudanças significativas no ambiente" (HAYKIN, 2001, p. 30).
    - Resposta a evidências (não apenas classificar o padrão adequadamente, mas informar o nível de confiabilidade da escolha, rejeitando ambiguidade);
    - Informação contextualizada ("O conhecimento é representado pela própria estrutura e estado de ativação de uma rede neural." (HAYKIN, 2001, p. 30));
    - Tolerância a falhas (devido à sua estrutura massiva e paralelamente distribuída);
    - Implementação em VSLI (*very-large-scale-integration*) [6];
    - Uniformidade de análise e projeto ("[...] as redes neurais desfrutam de universalidade como procesadores de informação" (HAYKIN, 2001, p. 30));
    - Analogia neurobiológica (motivadas por estruturas biológicas do cérebro humano).

## Citações importantes

> In its most general form, a neural network is a machine that is designed to model the way in which the brain performs a particular task or function of interest. (HAYKIN, 2009, p. 2)

> A neural network is a massively parallel distributed processor made up of simple processing units that has a natural propensity for storing experiential knowledge and making it available for use. It resembles the brain in two respects:
> 1. Knowledge is acquired by the network from its environment through a learning process.
> 2. Interneuron connection strengths, known as synaptic weights, are used to store the ac-
quired knowledge. (HAYKIN, 2009, p. 2)

> Generalization refers to the neural network's production of reasonable outputs for inputs not encountered during training (learning) (HAYKIN, 2009, p. 2).

## Notas do fichamento

<!-- [1] DEFINIR INFORMAÇÃO -->

[2] A palavra computar significa "fazer o cômputo de; calcular; orçar; contar; processar através de computadores". Fonte: [Dicionário Priberam da Língua Portuguesa](https://dicionario.priberam.org/computar).

[3] Sobre o **processamento em paralelo**, das Neurociências colhe-se que, ao que parece, os comportamentos humanos de maior complexidade não decorrem da sinalização de um único neurônio, mas pela ação de muitos não necessariamente localizados na mesma região cortical (Kandel et al., 2014).
> O envolvimento de vários grupos neurais ou rotas para transmitir uma informação similar é chamado *processamento em paralelo*. O processamento em paralelo também ocorre em uma única via quando diferentes neurônios nessa via executa ações similares simultaneamente. [...] O campo da ciência computacional conhecido como inteligência artificial originalmente usou o processamento serial para simular os processos cognitivos do encéfalo [...] Esses modelos seriais executavam muitas tarefas de forma adequada, inclusive jogar xadrez. Entretanto, eram muito ruims em outras tarefas que o encéfalo faz quase instantaneamente, com o reconhecimento de faces ou a compreensão do discurso. [...] Nesses modelos [redes neurais], elementos do sistema processam a informação simultaneamente usando conexões de pró-ação e de retroalimentação. É interessante observar que, em sistemas com circuitos de retroalimentação é a atividade dinâmica do sistema que determina o desfecho do processamento, não as aferências ou condições iniciais. Modelos de redes neurais capturam bem a arquitetura altamente recorrente da maioria dos circuitos neurais reais e também a capacidade do encéfalo de funcionar na ausência de uma aferência sensorial específica vinda de fora do corpo [...] Modelos de redes neurais também demonstram que a análise de elementos individuais de um sistema pode não ser suficiente para decodificar a *mensagem dos potenciais de ação*. De acordo com tal visão de redes neurais, o que faz o encéfalo ser um deslumbrante órgão que processa a informação não é a complexidade de seus neurônios, mas o fato de ter muitos elementos interconectados de várias formas complexas." (KANDEL et al., 2014, p. 32/33)

[4] Vide complemento [plasticidade](../../complementos/plasticidade.md).

<!-- [4] CONCEITUAR MÁQUINA ADAPTATIVA -->

<!-- [5] A **teoria dos filtros adaptativos lineares (*linear adaptative filter theory*)** CONCEITUAR ..... -->

[6] VLSI, do inglês *Very Large Scale Integration*, é um processo de fabricação de circuitos eletrônicos integrados com altíssima quantidade de transistores em um único chip.

## Referências complementares consultadas durante o fichamento deste capítulo

KANDEL, Eric R.; SCHWARTZ, James H.; JESSELL, Thomas M.; SIEGELBAUM, Steven A.; HUDSPETH, A. J. **Princípios de neurociências**. Trad. Ana Lúcia Severo Rodrigues et al. 5. ed. Porto Alegre: AMGH, 2014.

VERY LARGE SCALE INTEGRATION. In: WIKIPEDIA. Disponível em <https://en.wikipedia.org/wiki/Very_Large_Scale_Integration>. Acesso em 22 jan. 2024.
