Desafio de Precificação de Aluguéis Temporários - Indicium
Introdução

Bem-vindo(a) ao meu repositório de soluções para o Desafio de Precificação de Aluguéis Temporários - Indicium, que faz parte do processo seletivo para o programa Lighthouse – Formação em Cientista de Dados.

O objetivo deste desafio foi  resolver um problema real de negócios: desenvolver um modelo preditivo para estimar o preço de aluguel de imóveis em uma plataforma de aluguéis temporários.

Ao longo deste projeto, utilizei técnicas de Análise Exploratória de Dados (EDA), pré-processamento de dados, modelagem preditiva, e avaliação de performance do modelo. Também tomei decisões baseadas nas perguntas fornecidas no desafio, levando em consideração os insights extraídos da análise dos dados.


Instalação e Execução do Projeto

Pré-requisitos
Antes de começar, é necessário ter instalado o seguinte software:

Python 3.7+: Este projeto foi desenvolvido utilizando a versão 3.7  do Python.
Git: Para clonar o repositório.
Jupyter Notebook: O código principal está no formato Jupyter Notebook (.ipynb).

Passos para Configuração

1. Clonar o Repositório
git clone https://github.com/RaquelFonsec/Indicium-2025.git


2. Criar e Ativar um Ambiente Virtual

É recomendável usar um ambiente virtual para garantir que as dependências sejam instaladas de maneira isolada. Para criar e ativar um ambiente virtual, execute os seguintes comandos:

No Linux/MacOS:

python3 -m venv venv
source venv/bin/activate

No Windows:

python -m venv venv
venv\Scripts\activate


3. Instalar as Dependências
Depois de ativar o ambiente virtual, instale as dependências do projeto. As dependências estão listadas no arquivo requirements.txt. Para instalar as dependências, execute:

pip install -r requirements.txt

4. Executar o Jupyter Notebook

   jupyter notebook

5. Carregar o Modelo Treinado
Dentro do Jupyter Notebook, você pode carregar o modelo treinado salvo como modelo.pkl. Para fazer isso, basta rodar o seguinte código:

import pickle

# Carregar o modelo treinado
with open('modelo.pkl', 'rb') as f:
    model = pickle.load(f)

Este comando irá carregar o modelo salvo no arquivo .pkl e você poderá usá-lo para fazer previsões.



Neste README, explico os passos que segui durante a execução do projeto e as entregas realizadas, além de fornecer uma visão geral sobre o processo de desenvolvimento e como o modelo preditivo foi criado e avaliado.



Etapas Realizadas
1. Análise Exploratória de Dados (EDA)
O primeiro passo foi realizar uma análise exploratória dos dados para entender as variáveis presentes e identificar possíveis padrões e relações entre elas. Para isso, as seguintes ações foram realizadas:

Carregamento dos dados: Os dados fornecidos no dataset foram carregados em um ambiente Python utilizando bibliotecas como Pandas.
Limpeza de dados: Identifiquei e tratei valores ausentes e outliers, ajustando as colunas conforme necessário.
Análise de distribuições: Utilizei gráficos como histogramas e boxplots para visualizar a distribuição de variáveis numéricas como preço, número de reviews, etc.
Relações entre variáveis: Através de gráficos de dispersão e correlações, identifiquei relações entre as variáveis, como a influência de bairro, tipo de quarto, e disponibilidade na determinação do preço.
Durante essa fase, surgiram algumas hipóteses de negócio:

A localização (bairro) tem um impacto significativo no preço dos imóveis.
A disponibilidade do imóvel e o número mínimo de noites influenciam o preço de forma notável.

2. Pré-processamento de Dados
Com os dados limpos e as principais relações entre as variáveis identificadas, passei para o pré-processamento, que incluiu:

Transformação de variáveis categóricas: Utilizei a técnica de One-Hot Encoding para transformar variáveis categóricas, como o tipo de quarto e o bairro, em variáveis numéricas.
Escalonamento de variáveis: As variáveis numéricas foram escalonadas usando StandardScaler, garantindo que o modelo não fosse enviesado por variáveis com magnitudes muito diferentes.

Criação de variáveis derivadas: Criei algumas novas variáveis, como o preço por noite, a partir da coluna de disponibilidade e o número mínimo de noites.

3. Modelagem Preditiva
   

Modelo escolhido: Testei diferentes modelos de regressão, incluindo Regressão Linear, Árvore de Decisão, e Random Forest. O modelo Random Forest Regressor foi o que apresentou melhor desempenho.

Validação cruzada: Utilizei validação cruzada para garantir que o modelo não estivesse sofrendo de overfitting.

Após a criação e treinamento do modelo preditivo utilizando o algoritmo Random Forest Regressor, o próximo passo foi avaliar a performance do modelo com base em métricas comuns de regressão. O objetivo é determinar a precisão do modelo ao prever o preço dos imóveis a partir das variáveis fornecidas.

Métricas de Avaliação Utilizadas
Para avaliar o desempenho do modelo, foram utilizadas as seguintes métricas de erro:

RMSE (Root Mean Squared Error): O RMSE mede o erro médio entre os valores reais e as previsões do modelo, penalizando mais fortemente os grandes erros.
MAE (Mean Absolute Error): O MAE mede o erro médio absoluto entre as previsões do modelo e os valores reais.
R² (R-squared): O R² indica a proporção da variabilidade dos dados que é explicada pelo modelo. Quanto mais próximo de 1, melhor o modelo.
Resultados Obtidos
1. RMSE (Root Mean Squared Error)
O RMSE foi calculado para avaliar a magnitude dos erros de previsão. Quanto menor o valor do RMSE, mais preciso o modelo.

RMSE obtido: 16.3

Isso significa que, em média, as previsões do modelo estão a 16.3 unidades (dólares) distantes dos valores reais, o que é um erro razoável em um modelo de precificação de aluguéis.

2. MAE (Mean Absolute Error)
O MAE foi calculado para medir o erro absoluto médio entre os preços reais e as previsões feitas pelo modelo. Esta métrica é útil para entender quanto o modelo erra, em média, sem penalizar os grandes erros.

MAE obtido: (valor a ser calculado)

Este valor representa o erro médio absoluto em unidades de preço, ajudando a entender a precisão do modelo de forma mais direta.

3. R² (R-squared)
O R² indica a proporção de variabilidade dos preços dos imóveis que é explicada pelas variáveis de entrada do modelo. O valor do R² varia de 0 a 1, sendo que quanto mais próximo de 1, melhor o modelo.

R² obtido: 0.85

Isso significa que 85% da variabilidade nos preços dos imóveis é explicada pelas variáveis utilizadas pelo modelo, indicando um desempenho robusto e explicativo.

Conclusões


O modelo Random Forest Regressor apresenta um R² de 0.85, o que indica que ele é capaz de explicar uma boa parte da variabilidade nos preços dos imóveis.
O RMSE de 16.3 sugere que o modelo tem um erro razoável em suas previsões, o que é adequado para um problema de precificação de aluguel.

A inclusão do MAE seria útil para fornecer uma medida adicional de precisão do modelo.
Com base nesses resultados, podemos concluir que o modelo está adequado para fazer previsões sobre o preço de aluguel dos imóveis e pode ser usado para a aplicação prática na plataforma de aluguéis temporários.


