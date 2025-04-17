# 📊 Sistema de Previsão de Volume de Tickets

Este projeto implementa um modelo preditivo para prever o volume mensal de tickets com base em dados históricos, permitindo um planejamento mais eficiente de recursos e equipes de suporte.

## 📋 Estrutura do Projeto

- `previsao_tickets.ipynb`: Notebook Jupyter com a implementação completa
- `dados_historicos_tickets.csv`: Dados históricos para treinamento do modelo
- `previsao_junho_2024.csv`: Arquivo gerado com a previsão para o próximo mês

## 🔍 Conjunto de Dados

O conjunto de dados contém informações mensais sobre tickets de suporte entre 2022 e 2024, incluindo:

- **Data**: Mês e ano do registro
- **Tickets**: Volume mensal de tickets (variável alvo)
- **Usuários Ativos**: Número de usuários ativos no mês
- **Feriados**: Quantidade de feriados no mês
- **Campanhas de Marketing**: Número de campanhas realizadas
- **Tickets Prévios**: Volume de tickets do mês anterior
- **Dias Úteis**: Quantidade de dias úteis no mês

## 🚀 Como Utilizar

1. Clone este repositório
2. Instale as dependências necessárias:
   ```
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
3. Execute o notebook `previsao_tickets.ipynb`
4. Para previsões em novos períodos, atualize os dados de entrada na Seção 6 do notebook

## 🌲 Por que Random Forest?

O algoritmo Random Forest foi escolhido para este projeto por diversos motivos:

### Vantagens para Previsão de Tickets:

1. **Robustez a outliers**: O volume de tickets pode ter picos ocasionais devido a incidentes específicos, e o Random Forest é menos afetado por esses valores extremos.

2. **Captura de relações não-lineares**: A relação entre o volume de tickets e fatores como campanhas de marketing, feriados ou usuários ativos raramente é linear, e o Random Forest consegue modelar essas complexidades.

3. **Interpretabilidade**: Apesar de ser um modelo de ensemble, o Random Forest fornece medidas de importância das variáveis, permitindo entender quais fatores mais influenciam o volume de tickets.

4. **Bom desempenho com tamanho moderado de dados**: Para séries temporais mensais, geralmente temos algumas dezenas ou centenas de observações, e o Random Forest funciona bem nessas dimensões.

5. **Baixo risco de overfitting**: Com a configuração adequada, o Random Forest tende a generalizar bem e não se ajustar demais aos dados de treinamento.

6. **Lida bem com múltiplas variáveis**: O modelo consegue trabalhar eficientemente com diversos preditores, incluindo variáveis categóricas e numéricas.

### Comparação com Alternativas:

- **Regressão Linear**: Mais simples, mas incapaz de capturar relações não-lineares complexas presentes nos dados de tickets.
- **Redes Neurais**: Potencialmente mais poderosas, mas exigem mais dados e são mais difíceis de interpretar.
- **ARIMA/SARIMA**: Modelos específicos para séries temporais, mas que não incorporam facilmente variáveis explicativas externas.
- **XGBoost**: Desempenho similar ao Random Forest, mas geralmente requer mais ajuste de hiperparâmetros.

## 📈 Resultados

O modelo apresenta métricas robustas de desempenho no conjunto de teste, com baixo erro médio absoluto (MAE) e boa capacidade de generalização. A visualização da série temporal com a previsão demonstra a eficácia do modelo em capturar a tendência dos dados.

## 📝 Próximos Passos

- Implementar previsões para múltiplos meses à frente
- Adicionar mais variáveis explicativas (ex: lançamentos de produtos, mudanças sazonais)
- Explorar modelos de séries temporais híbridos (LSTM + Random Forest)
- Criar um dashboard interativo para visualização das previsões
