# # 2.6 Capítulo 6 (p. 78/100)

![Static Badge](https://img.shields.io/badge/Status-Estudando-grey?labelColor=31A8B8)

## Parte 2 | Modelos preditivos (capítulos 4 a 10)

### 6. Métodos simbólicos

Englobam modelos cujo objetivo é representar explicitamente, através de estruturas simbólicas[1], o conhecimento extraído do conjunto de dados. Esses métodos facilitam a interpretação do resultado por seres humanos, visto que asseguram "[...] uma compreensibilidade maior do processo decisório [...], estando mais alinhado[s] aos princípios de que os modelos de AM devem também ser 'explicáveis' (*Explainable Machine Learning*) para garantir maior transparência em sua operação." (FACELI et al., 2023, p. 78). Em contrapartida, se utilizados isoladamente, têm menor acurácia preditiva em comparação a outros modelos, ditos "caixa-preta"[2].

Não obstante, é importante destacar que "a combinação de múltiplos modelos de árvores em comitês (*ensembles*) [...] tem se mostrado competitiva e é uma abordagem frequentemente empregada para aumentar o desempenho preditivo desses modelos." (FACELI et al., 2023, p. 97).

No livro, dentre os modelos que implementam métodos simbólicos, são apresentados aqueles baseados em árvores e em regras.

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
- **Modelos baseados em regras**

## Referências complementares

## Notas

[1]: Neste contexto, o termo **símbolo** refere-se à abstração de conceitos, objetos ou relações do mundo real, que propriamente os representam ou a suas características e estados. Por conseguinte, **estruturas simbólicas** são agrupamentos desses elementos fundamentais, de modo a representar conhecimentos e relacionamentos mais complexos.

[2]: A literatura comumente utiliza a expressão "caixa-preta" (*black box*) para se referir a modelos cujo processo decisório não é facilmente inferível ou interpretável por seres humanos, como é o caso das redes neurais artificiais. A propósito, vide o fichamento [1.2](../neural-networks-and-learning-machines-simon-haykin/_introduction.md), que contém algumas referências à terminologia no âmbito das redes neurais, em especial as [notas](../neural-networks-and-learning-machines-simon-haykin/_introduction.md#notas) 1 e 19.
