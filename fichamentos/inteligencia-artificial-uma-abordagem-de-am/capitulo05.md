# # 2.5 Capítulo 5 (p. 64/77)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 2 | Modelos preditivos (capítulos 4 a 10)

### 5. Métodos probabilísticos

#### 5.1 Brevíssimas considerações sobre probabilidade[^1]

Em linhas gerais, a probabilidade pode ser definida como **medida da frequência relativa**[^2] de um evento[^3] — isto é, a quantidade de vezes em que um determinado resultado ocorre ao longo de uma série experimental, desde que as condições nas quais foi observado se mantenham constantes — ou **medida de crença** de um indivíduo, decorrente de subjetivismo pessoal (Ross, 2010). Ela diz respeito a formas de quantificar a incerteza associada à previsão de resultados de eventos aleatórios e, sob uma perspectiva mais ampla, também à quantidade de surpresa esperada ao observar essas ocorrências e à quantidade de informação intrínseca a tais observações (Ross, 2010).

>"Parece razoável supor que a quantidade de surpresa causada pela informação de que E ocorreu deve depender da probabilidade de E. [...] [Logo,] a surpresa que alguém sente ao saber da ocorrência do evento E depende somente da probabilidade de E, [...] [então] não há surpresa ao ouvirmos que um evento cuja ocorrência é certa tenha de fato ocorrido [...] [, pois] quanto mais improvável é a ocorrência de um evento, maior é a surpresa causada por sua ocorrência." (ROSS, 2010, p. 501/502).

Nesse sentido, a quantificação tanto da surpresa quanto da incerteza traduzem a mesma imprevisibilidade inerente ao contexto probabilístico e, exatamente por consubstanciarem enfoques distintos de uma mesma linha de raciocínio, podem ser vistas como a entropia[^4] de uma variável aleatória (Ross, 2010) ou, em outras palavras, de um evento qualquer. "De fato, na teoria da informação, [...] é interpretada como a quantidade média de informação recebida quando o valor de [uma variável aleatória] X é observado." (ROSS, 2010, p. 504).

Consoante a teoria da informação, a entropia de um sistema pode ser compreendida como uma métrica da [im]previsibilidade da ocorrência de determinado evento, tal que quanto maior a quantidade de informações disponíveis para ajustar a expectativa relacionada à observação, tão menor será a entropia e a incerteza associadas; consequentemente, por outro lado, se houver poucas informações prévias para auxiliar na valoração da probabilidade, o aumento da entropia consequentemente importará em maior incerteza. Isso acontece porque ela é inversamente proporcional à interpretabilidade dos dados: cenários de maior entropia reduzem o valor informacional porque aumentam a desorganização (confusão), enquanto os de menor entropia favorecem a organização — e reduzem a confusão — dos dados, tornando-os mais interpretáveis e previsíveis.

Não por outro motivo, "*uncertainty represents the reliability of our inferences*" (DAVIS et al., 2020, p. 3).

## Principais tópicos

- **Probabilidade**
  - Dois pontos de vista
    - Medida da frequência relativa de um evento
    - Medida da crença de um indivíduo em relação a um evento
  - **Quantificação**:
    - da incerteza associada à [im]previsibilidade de eventos aleatórios
    - da surpresa esperada ao observar tais eventos
    - da informação intrínseca à observação
  - Entropia
    - Medida da desordem de um sistema
    - Organização, interpretabilidade e valor informacional dos dados
    - Relacionada com a incerteza e a surpresa em cenários probabilísticos

## Referências complementares

AUDY, Jorge L N.; ANDRADE, Gilberto K.; CIDRAL, Alexandre. **Fundamentos de sistemas de informação**. E-book. Porto Alegre: Bookman, 2007.

DAVIS, Josiah; ZHU, Jason; OLDFATHER, Jeremy; MACDONALD, Samual; TRZASKOWSKI, Maciej; KELSEN, Max. 2020. **Quantifying uncertainty in deep learning systems**. Disponível em <https://d1.awsstatic.com/APG/quantifying-uncertainty-in-deep-learning-systems.pdf>. Acesso em 18 mai. 2024.

ROSS, Sheldon. **Probabilidade: um curso moderno com aplicações**. Trad. Alberto Resende De Conti. 8 ed. Porto Alegre: Bookman, 2010.

## Notas

[^1]: Este tópico é autoral, portanto, não consta no texto original do livro.

[^2]: Como uma métrica de frequência relativa, pode ser definida nos termos de "[...] um experimento, cujo espaço amostral é S, [que] seja realizado repetidamente em condições exatamente iguais. Para cada evento E do espaço amostral S, definimos n(E) como o número de vezes que o evento E ocorre nas n primeiras repetições do experimento. Então, P(E), a probabilidade do evento E, é definida como [...] a proporção (limite) de tempo em que E ocorre [...] ou como a frequência limite de E." (ROSS, 2010, p. 44).

[^3]: Denomina-se **espaço amostral** (S) o conjunto que presumidamente contenha a totalidade de resultados possíveis de um experimento, mesmo os incertos; e **evento** (E) qualquer subconjunto de S, tal que, "se o resultado do experimento estiver contido em E, então dizemos que E ocorreu." (ROSS, 2010, p. 40).

[^4]: Na teoria da informação, a entropia é uma propriedade que "[...] mede o grau de desordem de um sistema, e a forma de combater essa desordem se dá através da informação." (AUDY; CIDRAL, 2007, p. 37).

[^5]: No livro, equivalente à introdução do capítulo 5 e à seção 5.1 (aprendizado bayesiano).

[^6]: A "[...] probabilidade condicional de que E ocorra dado que F ocorreu [...] é representada por P(E | F). [...] [Noutras palavras,] se o evento F ocorrer, então, para que E ocorra, é necessário que a ocorrência real seja um ponto tanto em E quanto em F; isto é, ela deve estar em EF. Agora, como sabemos que F ocorreu, tem-se que F se torna nosso novo, ou reduzido, espaço amostral; com isso, a probabilidade de que o evento EF ocorra será igual à probabilidade de EF relativa à probabilidade de F." (ROSS, 2010, p. 82).
