# Atividade complementar no Orange Data Mining — energias renováveis

Use os **dois CSVs produzidos pelo notebook da avaliação**. Desenvolva uma tarefa de classificação e outra de regressão no Orange. Em cada uma, selecione, configure e compare **três algoritmos diferentes**. O enunciado completo dos dados, atributos e entrega está em `Enunciado_Avaliacao_APIs_Energia_ML.md`.

## 1. Classificação — ANEEL

Abra `aneel_classificacao_orange.csv` com **File**, examine a tabela em **Data Table** e configure em **Select Columns**:

- **Features:** `potencia_kw` (potência outorgada em kW), `latitude`, `longitude` (coordenadas aproximadas em graus decimais).
- **Target:** `fonte` (Solar, Eólica, Hidráulica).

Examine a distribuição das classes e escolha **três classificadores**. Compare os três usando a mesma configuração de **Test & Score**; examine **CA/Accuracy, Precision, Recall e F1** e a **Confusion Matrix**. Explique quais classes foram confundidas e a limitação de prever a fonte apenas com potência e localização. Não interprete a quantidade de exemplos consultados como participação das fontes na matriz energética brasileira.

## 2. Regressão — Open-Meteo

Abra `meteo_regressao_orange.csv` com **File** e configure em **Select Columns**:

- **Features:** `temperatura_c` (°C), `umidade_pct` (%), `nuvens_pct` (%), `vento_kmh` (km/h), `hora` (hora local).
- **Target:** `radiacao_w_m2` (radiação solar global horizontal média da hora anterior em W/m²).
- **Meta:** `data_hora` (identifica e ordena as observações).

Examine as distribuições e uma relação entre entrada e alvo. Escolha **três regressores** e use a mesma configuração de **Test & Score**. Compare **MAE, MSE e R²** e examine os erros em **Predictions** ou em um gráfico. Caso sua versão exiba apenas **RMSE**, registre que **MSE = RMSE²**. Explique o papel da hora e por que radiação não é geração elétrica.

**Divisão temporal:** os registros do notebook estão em ordem cronológica. Para reproduzir a avaliação em Python no Orange, separe primeiro o CSV em aproximadamente 80% de linhas iniciais para treino e 20% finais para teste; carregue os dois arquivos e use a opção de conjunto de teste separado em **Test & Score**. Caso opte por validação cruzada aleatória, declare essa escolha e sua limitação para observações temporais. A comparação numérica com o notebook só é direta quando as divisões e os algoritmos são equivalentes.

## Entrega

No **mesmo repositório público do GitHub** da avaliação, adicione capturas legíveis dos dois fluxos do Orange e uma breve análise dos três resultados de cada tarefa. Identifique claramente os algoritmos, as métricas e o procedimento de avaliação usado. Envie **somente o link do repositório**.

**Fontes:** [ANEEL/SIGA](https://dadosabertos.aneel.gov.br/dataset/siga-sistema-de-informacoes-de-geracao-da-aneel) · [Open-Meteo histórico](https://open-meteo.com/en/docs/historical-weather-api).
