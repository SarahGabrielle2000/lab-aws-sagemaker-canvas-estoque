# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

## 📙 Introdução
Este projeto foi realizado como parte do Bootcamp - Nexa Machine Learning para iniciantes na AWS, oferecido pela plataforma DIO. O objetivo foi utilizar o AWS SageMaker Canvas para criar um modelo de previsão de estoque com base em um conjunto de dados fornecido. Este documento detalha o processo de configuração, treinamento e avaliação do modelo, bem como as previsões e análises realizadas.

### O que é o AWS SageMaker Canvas?
AWS SageMaker Canvas é uma ferramenta que facilita o uso de aprendizado de máquina, oferecida pela Amazon Web Services (AWS). Com esta ferramenta é possível criar modelos preditivos e realizar análises avançadas sem precisar escrever código, utilizando uma interface gráfica simples e intuitiva, sendo possível a utilização até para quem não possui familiaridade com o assunto. As principais funcionalidades incluem:

- Carregar seus dados para análise.  
- Desenvolver modelos preditivos sem escrever código.
- Verificar como o modelo está se saindo e ajustar se necessário.
- Gerar previsões baseadas em seus dados.

## 🔃 Passos Seguidos
### 1. Preparação do Ambiente
Utilizei o dataset fornecido pela DIO, que inclui dados relevantes para a previsão de estoque. As colunas da planilha em questão eram formadas pelos seguintes dados: ID_PRODUTOS, DIA, FLAG_PROMOCAO, QUANTIDADE_ESTOQUE.
Acessei o AWS SageMaker Canvas através da console da AWS, selecionei o modelo que iria utilizar, no caso o de "Análise Preditiva" e naveguei até a seção de importação de dados.

### 2. Preparação dos Dados:
Carreguei o dataset fornecido no formato suportado (por exemplo, CSV); Revisei os dados para garantir que estavam limpos e bem formatados; Selecionei a coluna "QUANTIDADE_ESTOQUE" como a variável alvo de previsão; Configurei o modelo, ajustando informações como a quantidade de dados para treinamento e tirando linhas em brancos. Tudo de forma bem simples e intuitiva disponibilizada na ferramenta.

Por fim, após análisar se todas as informações estavam corretas, iniciei o treinamento do modelo de previsão utilizando a opção "Quick build", que durou em média 15 minutos para realizar as apurações, método mais rápido, porém com menos precisão das informações obtidas. O SageMaker Canvas, possui disponível também a opção "Standard build", que leva entre 2-4 horas para realizar os levantamentos, apesar de o tempo de espera ser um pouco mais longo, os dados obtidos são mais precisos.

### 3. Análise das Métricas de Desempenho
Após o treinamento, obtive as seguintes métricas:

- Avg. WQL (Weighted Quantile Loss): 1.140
Essa métrica mostra como o modelo está indo na previsão de diferentes quantis. Um valor de 1.140 sugere que o modelo está com uma precisão razoável, mas há espaço para melhorias.
- MAPE (Mean Absolute Percentage Error): 0.721
Esse valor indica que, em média, as previsões estão 72.1% distantes dos valores reais. Valores menores são melhores, e este número sugere que o modelo pode ser aprimorado para uma previsão mais precisa.
- WAPE (Weighted Absolute Percentage Error): 0.966
Esse valor mostra a média dos erros percentuais ponderados. Um valor próximo de 1 sugere que o modelo pode estar subestimando ou superestimando os valores em média.
- RMSE (Root Mean Square Error): 5.652
O RMSE mede o tamanho do erro. Esse valor indica que há uma certa margem de erro nas previsões, mas não é alarmante. É um bom ponto de partida para ajustes.
- MASE (Mean Absolute Scaled Error): 0.140
O MASE compara o desempenho do modelo com um modelo de referência simples. Um valor abaixo de 1 sugere que o modelo está se saindo melhor do que uma abordagem básica.

### 4. Análise e Ajustes
Análise das Métricas:

- RMSE e MASE indicam que o modelo está indo bem, mas sempre há espaço para melhorias.
- MAPE e WAPE sugerem que as previsões podem ser ajustadas para uma maior precisão.

Ajustei algumas configurações no modelo e re-treinei utilizando a opção "Standard build" para obter maior precisão e verificar se o desempenho melhorava. Pequenos ajustes podem fazer uma grande diferença.

### 5. Previsão e Resultados
Apliquei o modelo otimizado para fazer previsões de estoque com base nos dados obtidos e comparei as previsões com os valores reais para verificar a precisão. Documentei o que aprendi e como os dados previstos podem ajudar em tomadas de decisões.

## 📝 Conclusões e Insights
- O modelo demonstrou uma capacidade geral de previsão satisfatória, com métricas que indicam um bom desempenho, oferecendo insights valiosos sobre a gestão de estoque.
- Ajustes e melhorias contínuas podem ser feitas para aumentar a precisão dos dados previstos.
- As previsões ajudam a tomar decisões otimizadas sobre a estocagem e a alocação de recursos, o que pode ser muito útil para o planejamento futuro.
