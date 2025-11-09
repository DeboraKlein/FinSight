#  Inteligência Preditiva para Otimização de Capital e Risco de Crédito ($\text{RAROC}$-Driven)

## Resumo Executivo: Ganhos Reais com Sustentabilidade

Este projeto propõe uma solução de **intervenção de crédito proativa** baseada em Machine Learning (ML) avançado para Fintechs.

O modelo identifica clientes em **Estresse Agudo** (evitando o efeito bola de neve da dívida) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cartão Rotativo e Parcelamento de Fatura) por um **empréstimo com taxas de juros significativamente mais baixas**.

Essa abordagem de valor resulta na **mitigação imediata do risco ($\text{Recall}$ $\mathbf{89\%}$)**, na fidelização do cliente e na otimização do **Retorno Ajustado ao Risco ($\text{RAROC}$)**, alinhando concessão de crédito com a redução do custo de provisão.

---

### 1. A Tese de Valor Validada

O modelo automatiza a identificação de clientes no ciclo vicioso de linhas caras e não-core (Cartão de Crédito Rotativo e Cheque Especial). Ao oferecer uma consolidação de dívida proativa, o projeto valida a seguinte melhoria estratégica:

* **De Reativo para Proativo:** Intervenção acionada pela probabilidade de risco ($y\_proba$), em vez de esperar o default.
* **Decisão Otimizada:** Utilização do **Threshold $\mathbf{0.20}$** para garantir o máximo retorno ajustado ao risco, em conformidade com as regras de $\text{PECLD}$ ($\text{IFRS}$ 9).

| Métrica | Valor Final | Ponto Chave |
| :--- | :--- | :--- |
| **Poder Preditivo ($\text{AUC}$)** | **$\mathbf{0.7776}$** | **Alta Robustez** – Supera o benchmark de $\text{AUC} > 0.75$ para modelos de risco. |
| **Captura de Risco ($\text{Recall}$)** | **$\mathbf{100\%}$** | De 100 clientes que entrariam no Rotativo, $\mathbf{89}$ são capturados para intervenção. |
| **Threshold de Ação** | **$\mathbf{0.20}$** | Ponto de corte que maximiza o Retorno Ajustado ao Risco ($\text{RAROC}$). |
| **Viabilidade Operacional** | **$\text{Precision}$ $\mathbf{36\%}$** | O custo de $\mathbf{64\%}$ de Falsos Positivos é convertido em uma Estratégia de Fidelização (Ofertas Consultivas). |

---

## 2. Visuais Chave do Modelo (Interpretabilidade para Leigos)

Os gráficos gerados na modelagem são a prova visual da eficácia e da lógica de negócio do modelo.

### 2.1. Curva ROC: Poder Preditivo

// Formato Correto:
![Curva ROC do Modelo LightGBM com AUC de 0.7776](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/curva_ROC.png)

> **O que este gráfico significa?**
> Este gráfico mostra a **capacidade do modelo de distinguir** entre um cliente que vai entrar no rotativo e um cliente seguro. O **$\text{AUC}$ de $\mathbf{0.7732}$** é a prova de que nosso modelo é altamente eficaz, afastando-se drasticamente da linha diagonal (que representa uma adivinhação aleatória).

### 2.2. Top 10 Features Mais Importantes

> ![Top 10 Features Mais Importantes (Gain) do LightGBM](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/features.png)

> **O que este gráfico significa?**
> Ele mostra **o que o modelo realmente aprendeu**. As *features* mais importantes são aquelas que medem a **mudança de comportamento (tendência)** do cliente, como o **Crescimento do Gasto** e a **Taxa de Comprometimento de Renda Implícita `scr_tcr_implicita`**. O modelo ignora características estáticas (como Região ou Idade), focando apenas nos sinais de estresse financeiro agudo.

### 2.3. Matriz de Confusão ($\text{Threshold}$ $\mathbf{0.20}$)

> ![Matriz de Confusão do Modelo LightGBM com Threshold 0.20](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/matriz_confusao.png)

> **O que este gráfico significa?**
> Este é o resultado de negócio. Os **Verdadeiros Positivos (TP)** representam os clientes de risco que **capturamos com sucesso** e que evitamos que gerassem $\text{PDD}$ (prejuízo). Esta matriz valida que o *threshold* $\mathbf{0.20}$ alcança um alto volume de captura de risco ($\text{Recall}$ $\mathbf{100\%}$), protegendo o capital da FinTech.

---

## 3. Estrutura de Operacionalização ($\text{MLOps}$)

O modelo está pronto para ser implementado em um pipeline de **Processamento em Lote ($\text{Batch}$)** para *scoring* diário:

1.  **Inferência:** Modelo gera a probabilidade ($y\_proba$) para toda a carteira.
2.  **Decisão:** Sistema aplica a regra $y\_proba \ge \mathbf{0.20}$.
3.  **Engajamento:** Clientes acionados via canais digitais ($0.20 \le y\_proba < 0.50$) ou Gerentes de Carteira ($y\_proba \ge 0.50$).
4.  **Monitoramento:** Acompanhamento contínuo da estabilidade do $\text{AUC}$ e das *Features* para garantir que o **$\text{RAROC}$ realizado** se mantenha próximo do **$\text{RAROC}$ otimizado**.

---

### Navegação nos Notebooks

| Notebook | Título | Foco Principal |
| :--- | :--- | :--- |
| `01_fundamentacao_comportamental.ipynb` | Fundamentação e Feature Engineering | Tese do Estresse Agudo e Dicionário de Variáveis. |
| `02_sustentabilidade_financeira.ipynb` | Sustentabilidade Financeira: $\text{RAROC}$ | Cálculo de $\text{Threshold}$ Otimizado e Impacto Financeiro. |
| `03_modelagem.ipynb` | Modelagem e Validação ($\text{LightGBM}$) | Treinamento, $\text{OOT}$ e Resultados Finais ($\mathbf{AUC=0.7732}$). |
| `04_operacionalizacao.ipynb` | Operacionalização do Modelo ($\text{MLOps}$) | Pipeline de Produção e Simulação de Inferência. |
| `05_apresentação.ipynb` | Apresentação Executiva | $\text{Business Case}$ em Formato $\text{Slide}$ para Diretoria. |