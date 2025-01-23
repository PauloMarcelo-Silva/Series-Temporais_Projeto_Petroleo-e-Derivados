# Análise de Séries Temporais: Petróleo e Derivados
Este projeto realiza a análise de séries temporais relacionadas à produção, consumo, importação e exportação de petróleo e seus derivados no Brasil. Utiliza diversas ferramentas estatísticas e de aprendizado de máquina para explorar tendências, sazonalidades, ruídos e realizar previsões futuras.

## Objetivos
### Análise Exploratória dos Dados (EDA):

- Limpeza, transformação e visualização dos dados.
- Identificação de outliers, tendências e sazonalidade.

### Modelagem Preditiva:
- Implementação de modelos como ARIMA, Suavização Exponencial (ETS), Regressão Linear e Redes Neurais LSTM para previsão de séries temporais.

## Estrutura do Código

1. Leitura e Preparação dos Dados
Os dados são carregados a partir de arquivos Excel contendo informações sobre:

- Exportação de Petróleo e Derivados (df_exportacao)
- Importação de Petróleo e Derivados (df_importacao)
- Consumo Aparente de Petróleo e Derivados (df_consumo)
- Produção de Petróleo (df_producao)

#### Principais etapas realizadas:

Renomeação de colunas para nomes mais intuitivos.
Verificação e tratamento de valores ausentes e duplicados.
Conversão da coluna Data para o formato datetime.
Junção dos datasets em um único dataframe.

2. Análise Exploratória
- Estatísticas descritivas dos dados.
- Visualização de tendências e sazonalidade por meio de gráficos e decomposição de séries temporais.
- Identificação de outliers usando boxplots.

3. Transformação dos Dados
- Aplicação de diferenciação para remover tendências e analisar padrões sazonais.

4. Modelagem
- Os modelos são implementados em funções para facilitar sua reutilização e comparação.

Modelos Implementados:
ARIMA (AutoRegressive Integrated Moving Average):

Modelo estatístico usado para capturar relações lineares em séries temporais.
Função: run_arima(data, order=(p, d, q))
ETS (Exponential Smoothing):

Modelo que considera componentes de tendência e sazonalidade.
Função: run_ets(data, trend='add', seasonal='add', seasonal_periods=12)
Regressão Linear:

Modelo simples que ajusta uma linha reta aos dados.
Função: run_linear_regression(train, test)
LSTM (Long Short-Term Memory):

Rede neural recorrente usada para capturar padrões não lineares em séries temporais.
Funções:
prepare_lstm_data(data, look_back=12)
run_lstm(train, test, look_back=12, epochs=50, batch_size=1)
5. Avaliação dos Modelos
Métrica utilizada: Root Mean Squared Error (RMSE)
Compara as previsões dos modelos com os valores reais.
6. Visualização dos Resultados
Gráficos para comparar as previsões de cada modelo.