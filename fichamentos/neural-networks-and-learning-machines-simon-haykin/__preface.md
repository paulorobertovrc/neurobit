# # 1.1

![Static Badge](https://img.shields.io/badge/Status-Finalizado-grey?labelColor=5F9EA0)

## Prefácio (p. xi/xix)

Logo no primeiro parágrafo do prefácio, o autor esclarece que o objetivo do livro continua o mesmo desde a primeira edição, isto é, "*write an up-to-date treatment of neural networks in a comprehensive, thorough, and read- able manner*" (p. xi). Em tradução direta, o objetivo é produzir *um tratado atualizado sobre redes neurais de maneira abrangente, completa e legível*.

A seguir, é exposta a justificativa para a modificação do título do livro, que nesta 3a edição passou a ser entitulado de *Neural Networks and Learning Machines*, de modo a contemplar tanto o estudo das redes neurais inspiradas no cérebro humano, quanto métodos de aprendizagem de máquina embasados em modelos estatísticos. O estudo e aplicação em conjunto dessas diferentes vertentes pode ser sinérgico.

No mais, é esclarecida a forma de organização do livro, que é composto por quinze capítulos,  implicitamente agrupados em seis partes distintas, a saber: os capítulos 1 a 4 versam sobre **aprendizagem supervisionada (*supervised learning*)** [1], sendo que os três primeiros cuidam de modelo com uma única unidade computacional, ao passo que o último, com multicamadas; os capítulos 5 e 6, respectivamente, dizem respeito aos denominados **métodos de *kernel* (*kernel methods*)** [2] baseados em **redes de funções de base radial - ***radial-basis function networks*** (RBF)** - [3], e às **Máquinas de Vetores de Suporte - ***Support Vector Machines*** (SVM)** [4]; o capítulo 7 é dedicado à **Teoria da Regularização (*Regularization Theory*)** [5]; os capítulos 8 a 11 tratam da **aprendizagem não supervisionada (*unsupervised learning*)** [6]; o capítulo 12 é dedicado à **aprendizagem por reforço (*reinforcement learning*)** [7]; e, por fim, os capítulos 13 a 15 versam sobre **sistemas de feedback não lineares (*nonlinear feedback systems*) com ênfase em redes neurais recorrentes (*recurrent neural networks*)** [8].

## Notas

[1] [6] [7] No contexto dos **processos de aprendizagem de máquina**, segundo a classificação adotada pelo autor, há dois principais **paradigmas**: a **aprendizagem com um professor (*learning with a teacher*)**, que é sinônimo de **aprendizagem supervisionada (*supervised learning*)**, e a **aprendizagem sem um professor (*learning without a teacher*)**, da qual são espécies a **aprendizagem não supervisionada (*unsupervised learning*)** e a **aprendizagem por reforço (*reinforcement learning*)**.

[2] Neste contexto, o termo **kernel** se refere a uma função matemática que compara pares ordenados (*pairwise comparison*) - pontos em um plano cartesiano, por exemplo - representativos de um conjunto de dados. Por **métodos de kernel (*kernel methods*)** entende-se uma classe de algoritmos estatísticos de aprendizado de máquina (análise de padrões) que utiliza funções de kernel para mapear os dados de um espaço para outro, isto é, os dados de entrada (espaço original) são submetidos à função de kernel - mapeamento -, o que resulta em um novo conjunto de dados (novo [implícito] espaço), que é utilizado para treinar o modelo (Unzueta, 2021). A ideia é que os pontos do espaço original não precisem ser analisados pelo modelo, mas apenas os do implícito, técnica que é denominada de *kernel trick*.
> Métodos de kernel são uma classe de modelos de aprendizado de máquina baseados em kernels positivo semidefinidos, que servem como medidas de similaridade entre covariáveis. Exemplos de métodos de kernel incluem a regressão ridge com kernels, as máquinas de vetor de suporte e os splines suavizadores. Apesar do seu amplo uso, os métoos de kernel possuem duas desvantagens significativas. Em primeiro lugar, ao operar sobre todos os pares de observações, eles demandam grande quantidade de memória e computação, o que impossibilita sua aplicação em grandes conjuntos de dados. Este problema pode ser resolvido através de aproximaçõers da matriz do kernem via *random Fourier features* ou precondicionadores. Em segundo lugar, a maoria dos kernels tratam todas as covariáveis disponíveis como igualmente relevantes, desconsiderando seu impacto na predição. Isso resulta em um decréscimo da interpretabilidade, uma vez que a influência de covariáveis irrelevantes não é mitigada. (Otto, 2023, p. 13)

[3] No contexto das **funções de base radial - ***radial basis function*** (RBF)**, as camadas ocultas das redes neurais fornecem as denominadas funções de base, que são arbitrariamente aplicadas sobre os padrões ou vetores informados na camada de entrada - *inputs* (Haykin, 2001). Diz-se que é radial porque depende exclusivamente da distância entre o valor (ponto) de entrada e um ponto fixo (centro ou central). A principal característica de uma função radial é que seu resultado **aumenta ou diminui monotonamente conforme a distância do ponto central** (Engel). A função gaussiana é uma função radial. **A função de ativação de uma rede RBF é uma função de base radial.**

[4] Espécie de algoritmo de aprendizagem de máquina utiliza os *kernel methods*.

[5] "Um Método de Regularização é um algoritmo capaz de resolver o problema inverso de maneira estável" (Margotti). Por sua vez, "os problemas inversos formam um conjunto de problemas matemáticos onde se objetiva determinar a causa de um fenômeno particular (solução do problema), observando-se o efeito por ele produzido (dados)" (Margotti).

[8] **Redes neurais recorrentes (*recurrent neural networks*)** são aquelas que possuem um ou mais laços de realimentação (Haykin, 2001).

## Referências complementares consultadas durante o fichamento deste capítulo

ENGEL, Paulo Martins. **Redes Neurais: A Rede RBF.** Disponível em <https://www.inf.ufrgs.br/~engel/data/media/file/cmp121/rbf.pdf>. Acesso em 14 jan. 2024.

FUNÇÃO de base radial. In: WIKIPEDIA. Disponível em <https://pt.wikipedia.org/wiki/Fun%C3%A7%C3%A3o_de_base_radial>. Acesso em 14 jan. 2024.

LECTURE 1 on kernel methods: Positive definite kernels. Vídeo: 44min49s. Publicado pelo canal Julien Mairal. 22 fev. 2021. Disponível em <https://youtu.be/IzGS8uKc5E4?si=u1IDMZS9GB8d8vNG>. Acesso em 14 jan. 2024.

LECTURE 4 on kernel methods: Kernel Trick. Vídeo: 42min22s. Publicado pelo canal Julien Mairal. 22 fev. 2021. Disponível em <https://youtu.be/Ra06l4fqlSU?si=g0V996AeIlRb4tH1>. Acesso em 14 jan. 2024.

MARGOTTI, Fábio. **Problemas Inversos**. Universidade Federal de Santa Catarina. Disponível em <https://fabiomargotti.paginas.ufsc.br/pesquisa/problemas-inversos/>. Acesso em 14 jan. 2024.

MARGOTTI, Fábio. **Teoria da Regularização**. Universidade Federal de Santa Catarina. Disponível em <https://fabiomargotti.paginas.ufsc.br/pesquisa/problemas-inversos/teoria-da-regularizacao/>. Acesso em 14 jan. 2024.

OTTO, Mateus Piovezan. **Métodos de kernel escaláveis e interpretáveis baseados em random Fourier features**. 2023. Dissertação (Mestrado em Estatística) - Estatística Interinstitucional do ICMC e UFSCarr, Universidade de São Paulo, São Carlos, 2023. doi:10.11606/D.104.2023.tde-02052023-084042. Acesso em: 14 jan. 2024.

RADIAL basis function. In: WIKIPEDIA. Disponível em <https://en.wikipedia.org/wiki/Radial_basis_function>. Acesso em 14 jan. 2024.

RADIAL basis function network. In: WIKIPEDIA. Disponível em <https://en.wikipedia.org/wiki/Radial_basis_function_network>. Acesso em 14 jan. 2024.

UNZUETA, Diego. **Kernel Methods: A Simple Introduction**. Medium, 2021. Disponível em <https://towardsdatascience.com/kernel-methods-a-simple-introduction-4a26dcbe4ebd>. Acesso em 14 jan. 2024.
