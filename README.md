# Tech Challenge — FIAP Pós IADT

### Predição de Custos Médicos com Aprendizado de Máquina

> Repositório contendo o notebook `FIAP_POS_Trabalho_01.ipynb`, que implementa todo o fluxo de exploração, pré-processamento, modelagem e avaliação de um modelo de regressão para estimar custos médicos individuais, conforme o Tech Challenge da Fase 1.

---

## ✨ Visão Geral

O objetivo é prever o valor dos encargos de planos de saúde com base em atributos como idade, IMC, filhos, hábito de fumar, gênero e região.\
O dataset foi construído a partir do *Medical Cost Personal Dataset* (Kaggle) e inserido diretamente no notebook como uma lista `pacientes`, evitando dependências externas.

---

## 🔧 Requisitos

| Ferramenta           | Versão mínima |
| -------------------- | ------------- |
| Python               | 3.9           |
| Jupyter              | 6.x           |
| pandas               | 1.5           |
| scikit-learn         | 1.4           |
| statsmodels          | 0.14          |
| seaborn • matplotlib | 0.13 • 3.8    |

> Use `python -m venv .venv && source .venv/bin/activate` seguido de `pip install -r requirements.txt`.

---

## 🚀 Como Executar

1. Acesse **[Google Colab](https://colab.research.google.com/)**.
2. Clique em **Upload** e selecione o arquivo `FIAP_POS_Trabalho_01.ipynb`.
3. Após o upload, abra o notebook e escolha **Executar ▾ → Executar tudo** (ou pressione `Ctrl+F9`).
4. Aguarde todas as células terminarem — os gráficos e métricas aparecerão automaticamente ao final.

---

## 📝 Guia Rápido do Notebook

| Seção                           | Descrição                                                                 |
| ------------------------------- | ------------------------------------------------------------------------- |
| **Criação do DataFrame**        | Geração do dataset em memória e checagens iniciais.                       |
| **Exploração de Dados**         | `info()`, estatísticas, distribuições, heatmap de correlação.             |
| **Pré-Processamento**           | *Label Encoding*, transformação booleana, remoção de outliers, imputação. |
| **Divisão Treino/Teste**        | `train_test_split` 80/20, `random_state` 42.                              |
| **Modelagem**                   | Regressão Linear, Árvore de Decisão, Random Forest.                       |
| **Avaliação**                   | `MSE`, `R²`, gráficos Real × Predito, análise de resíduos.                |
| **Validação Estatística**       | *p-values* e IC 95 % com `statsmodels` (OLS).                             |
| **Comparação com/sem Outliers** | Impacto da remoção de extremos nos erros.                                 |

---

## 📊 Resultados Principais (TODO)

| Modelo            | MSE (↓)    | R² (↑)    |
| ----------------- | ---------- | --------- |
| Regressão Linear  | \~ *x xxx* | \~ *0,7x* |
| Árvore de Decisão | \~ *x xxx* | \~ *0,8x* |
| Random Forest     | \~ *x xxx* | \~ *0,8x* |

Gráficos no notebook mostram boa aderência dos modelos baseados em árvores, sobretudo após exclusão de outliers.

---

## 🧪 Validação Estatística (TODO)

> *Esta etapa ficará para ser completada após entregarmos a primeira versão funcional do modelo.*

1. **Regressão Linear (OLS / statsmodels)**
   - ☑️ Adicionar coluna de intercepto em `X_train` e ajustar `sm.OLS`.
   - ☑️ Exibir `summary()` para obter **p-values**, F-stat e R² ajustado.
   - ☑️ Gerar tabela de **IC 95 %** dos coeficientes (`model.conf_int()`).
   - ☑️ Exportar esses resultados para o README ou anexo PDF.

2. **Intervalo de Predição**
   - ☑️ Utilizar `get_prediction()` no conjunto de teste.
   - ☑️ Construir DataFrame com `y_real`, `y_pred`, `IC_inf`, `IC_sup`.
   - ☑️ Plotar gráfico Real × Predito com faixa de IC (sombras ou barras).

3. **Modelos de Árvore / Random Forest**
   - ☑️ Aplicar **bootstrap** (≥ 100 re-amostras) para estimar variância.
   - ☑️ Calcular IC 95 % dos valores preditos via percentis 2,5 / 97,5.
   - ☑️ Documentar que árvores não fornecem p-value de coeficiente.

4. **Testes Adicionais (opcional)**
   - Breusch-Pagan ou White ⇒ verificar heterocedasticidade.
   - Shapiro-Wilk nos resíduos ⇒ avaliar normalidade.

5. **Relato no vídeo**
   - Destacar quais variáveis são estatisticamente significativas.
   - Comentar casos em que o valor real caiu fora do IC.

---

## 📹 Entregável em Vídeo (TODO)

Grave um vídeo de **até 10 min** demonstrando:

1. Motivação e objetivo;
2. Passo a passo do notebook (EDA → Modelagem → Resultados);
3. Insights e próximos passos.

Suba como “Não Listado” no YouTube e inclua o link na entrega do Canvas.

---

## ➕ Próximos Passos

- Hiper-otimização de parâmetros (Grid / Bayesian Search).
- Validação *k-fold* para robustez.
- *Feature Engineering* (e.g., interação IMC × fumante).
- Testar algoritmos de *Boosting* (XGBoost, LightGBM).

---

## 👥 Grupo 100

| Participante                       | E‑mail                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------ |
| Givanildo Dias da Silva            | [givanildo.dias.silva@gmail.com](mailto\:givanildo.dias.silva@gmail.com) |
| Felipe Domingues Silva de Andrade  | [feandrad@gmail.com](mailto\:feandrad@gmail.com)                         |
| Hellen Heiny Souza de Santi        | [hellen.heiny@gmail.com](mailto\:hellen.heiny@gmail.com)                 |
| Raphael Henrique Pavaneli de Brito | [rafael\_pava.2012@hotmail.com](mailto\:rafael_pava.2012@hotmail.com)    |
| Hellen Lima Abade                  | [hellen.abade@outlook.com](mailto\:hellen.abade@outlook.com)             |

---

## 📄 Licença

Distribuído sob a licença **MIT**. Consulte `LICENSE` para detalhes.

