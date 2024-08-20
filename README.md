
![vendas](https://github.com/user-attachments/assets/42dc80fd-1673-4276-a40b-7d59b660f1d9)


## HACKDAY COMUNIDADE DS - Previsão de Vendas

### Visão Geral da Competição 
Este projeto foi desenvolvido durante uma competição da Comunidade DS (HACKDAY ou HACKTHON), um evento que ocorre em um final de semana, reunindo alunos da comunidade e dividindo-os em equipes de diferentes níveis de aprendizado. O objetivo é proporcionar aos alunos um contato mais próximo com problemas de negócio reais. Os alunos mais avançados podem aplicar seus conhecimentos e habilidades, enquanto os mais novos têm a oportunidade de ter seu primeiro contato com um problema real de ciência de dados e aprender como desenvolver uma solução. Além disso, a competição promove o trabalho em equipe, ajuda a afastar a síndrome do impostor e facilita a interação entre os alunos.

---

## Problema de Negócio Proposto 

### Visão Geral
A EletroPlaza Store é um conglomerado de lojas presente em diversos países. Apesar da presença online, as vendas são predominantemente físicas. A multinacional atua com eletrônicos, eletrodomésticos e acessórios, oferecendo produtos acessíveis e de qualidade para uma vasta gama de clientes.

Após diversos investimentos em vendas, marketing e desenvolvimento de produtos, a empresa teve um grande salto no faturamento no último ano. No entanto, com o aumento do faturamento, surgiram novos desafios para entender como as vendas vão se comportar nas próximas semanas.

Com a aproximação da Black Friday e do Natal, as vendas tendem a aumentar ainda mais. A equipe de negócios tem uma meta de faturamento e está preocupada se conseguirá alcançá-la. É urgente entender os possíveis resultados futuros.

O desafio da sua equipe, formada por cientistas e analistas de dados, é construir uma solução que preveja as vendas semanais das lojas e de seus diversos setores para as 5 semanas finais do ano. Dessa forma, os gestores da EletroPlaza Store poderão definir planos futuros, organizar estoques, calcular receitas e decidir sobre novos investimentos, além de alocar estes investimentos de forma mais eficiente em campanhas de marketing e vendas.

Os dados disponíveis para a previsão são referentes às vendas realizadas desde o início do ano até o momento. Cada linha representa um setor específico de uma loja específica em uma determinada semana. Diversas informações são fornecidas para análise, incluindo dados externos como temperatura, preço de combustível e taxa de desemprego. Devido à urgência, há muitos dados faltantes, e a equipe não tem tempo suficiente para coletá-los, devendo buscar soluções alternativas para realizar previsões eficazes.

A métrica de performance proposta para medir a generalização do modelo é a raiz quadrada do erro quadrático médio (RMSE).

Para mais informações acesse o [link da competição](https://www.kaggle.com/competitions/test-hackday-7).

---

## Alguns Insights
- Vendas de eletrodomestico são superiores a outros tipos de produtos oferecidos pela loja.
![Captura de Tela 2024-08-19 às 22 55 37](https://github.com/user-attachments/assets/948b9996-eb81-4a08-8bbb-de9dc79ac057)

  
- Lojas pequenas vendem mais e tem mais concentração de clientes
  ![Captura de Tela 2024-08-19 às 22 55 59](https://github.com/user-attachments/assets/18bba2bf-9ec2-4482-a5f6-7021ca4866ef)
  ![Captura de Tela 2024-08-19 às 22 57 13](https://github.com/user-attachments/assets/29be32ed-2ac9-422c-a3c7-0e1e285f3952)

## Resolução do Problema
Para resolver o problema foi aplicado um metodo CRISP de forma reduzida. Como assim?
Como a competição ocorre em dois dias, o tempo é precioso, então se pega os principais passos do metodo CRISP e se aplica para poder dar o ponta pé inicial do projeto.

Durante a Análise Exploratoria de Dados, o principal objetivo analisar a qualidade dos dados e identificar como esta sua distribuição e integridade. Afim de saber quais medidas tomar quando for preparar os dados para treinar os algoritmos de Machine Learning.

### Preparação dos Dados
Com base no dataset, foi observado a necessidade de se fazer Encoder de alguns dados, convertendo os dados categoricos em números inteiros. Foram utilizadas as técnicas de LabelEncoder e OrdinalEncoder.
LabelEncoder: somente para tranformar o dado categorico em um número inteiro;
OrdinalEncoder: também tranforma o dado categorico em um número iteiro, porém preserva a ordem natural das categorias.

Foi necessário tranformar as datas em algo ciclico, para isso foi usado a tecnica do seno e coseno para que seja representada como variáveis temporais (dias do mes, meses do ano e semanas do ano). Dessa forma o algoritmo de MAchine Learning reconheça esse ciclo.

### Seleção das Features
Para selecionar as melhores features para o modelo, foi treinado um modelo de RandonForest que pudesse selecionar as features mais relevantes. Após a seleção das features pelo modelo, foi calculada a importancias dessas features usando a métrica Mean Decrease In Impurity - MDI (Diminuição Média na Impureza), que avalia quando cada feature contribui para a redução da impureza nas divisoes do modelo, e foi plotado um gráfico.

### Algoritmos utilizados
Para realizar o treinamento e as prediçoes foram usados os algoritmos:
- Random Forest;
- Linear Regression Lasso;
- Regressão de ridge
- LightGBM

Tendo a métrica de performance proposta para esse desafio ser a raiz quadrada do erro quadrático médio (RMSE), que nada mais é o desvio padrão dos valores residuais, o algoritmo que apresentou a melhor perfomance foi a Random Forest.
![Captura de Tela 2024-08-19 às 23 21 41](https://github.com/user-attachments/assets/6fd68785-53fe-4289-aca2-b38d70bf26c7)

---

## Resultado da Competição
Com o trabalho em equipe realizado, conseguimos alcançar uma boa colocação geral com o nosso projeto, fazendo com que o algoritmo conseguisse generalizar bem perante dados nunca vistos. Nessa competição conseguimos alcançar o 5º Lugar com o resultado do nosso esforço e dedicação.

![Captura de Tela 2024-08-19 às 23 26 54](https://github.com/user-attachments/assets/2656aba3-d051-46a0-8311-6f10a87cc91d)

---

## Para os Próximos Passos a Serem Seguidos Nesse Projeto

- Identificar e criar novas variáveis (features) que possam melhorar o desempenho do modelo atual;
- Levantar novas hipóteses conhecimento do negócio;
- Testas novos algoritmos de Machine Learning.


