# # 1 — Ciência da Computação

![Static Badge](https://img.shields.io/badge/Última_atualização-20/06/2024-grey?labelColor=5F9EA0)

<!-- ## 1.1 Aspectos históricos da computação e da Ciência da Computação -->
<!-- ## 1.2 Definição -->

## 1.3 Objetivos

Dentre os objetivos da Ciência da Computação, "[...] uma tarefa fundamental [...] é encontrar técnicas para computar as funções que se encontram subjacentes aos problemas que queremos solucionar." (BROOKSHEAR, 2013, p. 469).

## 1.4 Conceitos gerais importantes

### 1.4.1 Abstração[^1]

Consiste na distinção das características extrínsecas e intrínsecas de uma entidade, de modo a torná-lo mais compreensível e possibilitar que seja manipulado como uma unidade, ignorando os detalhes internos e/ou de implementação (Brookshear, 2013). Noutras palavras, é um exercício imagético de simplificação que, em detrimento da complexidade inerente à construção, visa facilitar a compreensão e a interação com o objeto.

Nesse sentido, as estruturas de dados consubstanciam um exemplo de abstração, pois eximem o usuário — que pode ser humano ou outro sistema computacional, como um cliente no protocolo HTTP — do conhecimento dos detalhes inerentes ao acesso e manuseio dos dados armazenados em memória, pela simulação de um formato abstrato mais conveniente (Brookshear, 2013).

Os atributos comuns da entidade podem ser abstraídos, possibilitando o destaque daqueles que precisam ser detalhados porque diferenciam e/ou especificam um exemplar em particular, em relação aos demais (Sebesta, 2018). Aliás, **processos**[^2] ou **dados**[^3] podem ser abstraídos, nos dois casos, com o objetivo de reduzir a complexidade do programa (Sebesta, 2018).

#### 1.4.1.1 Conceito formal

"O termo abstração [...] refere-se à distinção entre as propriedades externas de um entidade e os detalhes da composição interna da entidade. É a abstração que nos permite ignorar os detalhes internos de um dispositivo complexo [...] e usá-lo como uma unidade única, compreensível. Além disso, é por meio da abstração que tais sistemas complexos são projetados e fabricados. [...] Cada componente representa um nível de abstração no qual o uso do componente é isolado dos detalhes da composição interna do componente. [...] A cada nível de abstração, vemos o sistema em termos de componentes, chamados de **ferramentas abstratas**, cuja composição interna ignoramos. Isso permite nos concentrarmos em como cada componente interage com outro em um mesmo nível e em como o conjunto, como um todo, forma parte do sistema que é relevante para a tarefa desejada em vez de nos perdermos em um mar de detalhes." (BROOKSHEAR, 2013, p. 11/12).

"Uma abstração é uma visão ou representação de uma entidade que inclui apenas os atributos mais significativos. De um modo geral, a abstração permite que alguém colete exemplares de entidades em grupos nos quais seus atributos comuns não precisam ser considerados." (SEBESTA, 2018, p. 446).

## 1.5 Linguagens de programação

### 1.5.1 Sintaxe e semântica

Assim como nas linguagens naturais, a sintaxe diz respeito à estrutura das expressões, sentenças e unidades do programa, e a semântica, ao significado (Sebesta, 2018). "Em uma linguagem de programação bem projetada, a semântica deve seguir diretamente a partir da sintaxe; ou seja, a aparência de uma sentença deve sugerir o que ela realiza." (SEBESTA, 2018, p. 111).

## Lista de tópicos

- **Conceitos importantes**
  - Abstração
- **Noções e terminologias**
  - Símbolos, alfabeto, cadeias de caracteres e linguagem
  - Sentenças
- **Linguagens de programação**
  - Sintaxe e semântica
  - Abstração de dados e de processos
    - Tipo de dado abstrato
      - Objeto
  - Subprogramas
    - Funções e procedimentos
  - Estruturas de dados [^4]
    - Registros

## Referências

BROOKSHEAR, J. Glenn. **Ciência da computação: uma visão abrangente**. Trad. Eduardo Kessler Piveta. 11. ed. Porto Alegre: Bookman, 2013.

SEBESTA, Robert W. **Conceitos de linguagens de programação**. Trad. João Eduardo Nóbrega Tortello. 11. ed. Porto Alegre: Bookman, 2018.

SIPSER, Michael. **Introdução à teoria da computação**. Trad. Rui José Guerra Barreto de Queiroz. 2 ed. São Paulo: Cengage Learning, 2021.

## Notas

[^1]: Ver Brookshear (2013), capítulo 0, seção 0.4 (p. 11/13) e Sebesta (2018), capítulo 11 (sobre o conceito de abstração, abstração de dados e tipos de dados abstratos).

[^2]: "O conceito de abstração de processo está entre os mais antigos no projeto de linguagens de programação. [...] Todos os subprogramas são abstrações de processo, porque fornecem uma maneira pela qual um programa especifica um processo, sem fornecer os detalhes de como ele realiza sua tarefa [...]." (SEBESTA, 2018, p. 447). Por sua vez, **subprogramas** são coleções de **sentenças** — instruções completas e específicas de uma ação ou, em menor nível, "[...] um conjunto de cadeias de caracteres formadas a partir de um alfabeto" (SEBESTA, 2018, p. 111) — e podem ser categorizados em **funções** ou **procedimentos** (Sebesta, 2018). "**Cadeias de caracteres** são blocos básicos fundamentais em ciência da computação. O **alfabeto** sobre o qual as cadeias são definidas pode variar com a aplicação. Para nossos propósitos, definimos um alfabeto como podendo ser qualquer conjunto finito não vazio. Os membros do alfabeto são os **símbolos** do alfabeto. [...] Uma **cadeia sobre um alfabeto** é uma sequência finita de símbolos daquele alfabeto [...]. Uma **linguagem** é um conjunto de cadeias." (SIPSER, 2021, p. 13/14).

[^3]: "Um **tipo de dado abstrato** é uma estrutura de dados na forma de um **registro**, mas que inclui subprogramas que manipulam seus dados. Sintaticamente, um tipo de dados abstrato é um invólucro que inclui apenas a representação de dados de um tipo de dados específico e os subprogramas que fornecem as operações para esse tipo. [...] Um exemplar de um tipo de dados abstrato é chamado de **objeto**." (SEBESTA, 2018, p. 447). Em linguagens de programação, um **registro** (*struct*) "[...] é uma estrutura de dados que armazena campos, os quais têm nomes e podem ser de tipos diferentes." (SEBESTA, 2018, p. 447, nota de rodapé).

[^4]: Estruturas de dados são abordadas em material suplementar específico. Ver [suplemento 03](./03-estruturas-de-dados.md).
