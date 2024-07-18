# # 2.7 Capítulo 7 (p. 101/116)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 2 | Modelos preditivos (capítulos 4 a 10)

### 7. Métodos conexionistas

São métodos inspirados em modelos biológicos, que buscam não apenas **simular o funcionamento** do sistema nervoso humano e o modo como o cérebro **adquire novos conhecimentos** — ou seja, seu **processo de aprendizado** —, mas alcançar **capacidade de processamento** semelhante e obter **máquinas inteligentes ou que se comportem de maneira aparentemente inteligente.** Assim como o cérebro é composto por uma grande quantidade de neurônios interconectados, perfazendo redes neurais que funcionam em paralelo e trocam informações através de sinapses[^1], as redes neurais artificiais (RNAs) são formadas por unidades que implementam funções matemáticas a fim de simular a atividade neuronal e, de modo geral, **abstraem a compreensão da fisiologia do cérebro e dos processos biológicos de aprendizagem.**

>"A procura por modelos computacionais ou matemáticos do sistema nervoso teve início na mesma época em que foram desenvolvidos os primeiros computadores eletrônicos, na década de 1940. Os estudos pioneiros na área foram realizados por McCulloch e Pitts (1943). Em 1943, eles propuseram um modelo matemático de neurônio artificial, a unidade lógica com limiar (LTU, do inglês *Logic Threshold Unit*), que podia executar funções lógicas simples. McCulloch e Pitts mostraram que a combinação de vários neurônios artificiais em sistemas neurais tem um elevado poder computacional, pois pode implementar qualquer função obtida pela combinação de funções lógicas. Entretanto, redes de LTUs não possuíam capacidade de aprendizado. [...] Na década de 1970, houve um resfriamento das pesquisas em RNAs, principalmente com a [...] limitação da rede Perceptron a problemas linearmente separáveis. Na década de 1980, o aumento da capacidade de processamento, as pesquisas em processamento paralelo e, principalmente, a proposta de novas arquiteturas de RNAs com maior capacidade de representação e de algoritmos de aprendizado mais sofisticados levaram ao ressurgimento da área." (FACELI et al., 2023, p. 102).

## Principais tópicos

- Inspiração biológica
  - Simulam o funcionamento de uma rede neural biológica para alcançar capacidade computacional similar à do cérebro humano, com o objetivo de obter máquinas inteligentes e/ou capazes de emitir comportamentos aparentemente inteligentes
- Unidades de processamento simples — "neurônios artificiais" — implementam funções matemáticas a fim de resolver problemas complexos
- Estudos pioneiros
  - McCulloch e Pitts (1943)
    - Unidade lógica com limiar (*Logic Threshold Unit*, LTU)
    - Redes de LTUs não possuíam capacidade de aprendizado, apesar do elevado poder computacional

<!-- ## Referências complementares -->

## Notas

[^1]: "O principal bloco de construção do cérebro é o neurônio. Os principais componentes de um neurônio são: dendritos, corpo celular e axônio. [...] Os dendritos são prolongamentos dos neurônio especializados na recepção de estímulos nervosos provenientes de outros neurônios ou do ambiente. Esses estímulos são então transmitidos para o corpo celular ou soma. O soma coleta as informações recebidas dos dendritos, as combina e processa. De acordo com a intensidade e frequência dos estímulos recebidos, o corpo celular gera um novo impulso, que é enviado para o axônio. O axônio é um prolongamento dos neurônios, responsável pela condução dos impulsos elétricos produzidos no corpo celular até outro local mais distante [...]. O contato entre a terminação de um axônio e o dendrito de outro neurônio é denominado sinapse. As sinapses são, portanto, as unidades que medeiam as interações entre os neurônios [...] e podem ser excitatórias ou inibitórias." (FACELI et al., 2023, p. 102/103).
