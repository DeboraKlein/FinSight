# Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

## Resumo Executivo: Ganhos Reais com Sustentabilidade

Este projeto propõe uma solução de intervenção de crédito proativa baseada em Machine Learning (ML) avançado para Fintechs.

O ML identifica clientes em **Estresse Agudo** (evitando o atraso e o efeito bola de neve) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cheque Especial, Cartão Rotativo e Parcelamento de Fatura) por um empréstimo com taxas de juros significativamente mais baixas.

Essa abordagem de valor gera uma percepção positiva no cliente, ao demonstrar a economia real obtida na liquidação das dívidas caras, e preserva seus limites de crédito. Para a instituição, resulta na mitigação imediata do risco, na redução da inadimplência, na fidelização do cliente e na liberação de operação de crédito.

O foco não é apenas evitar o *default*, mas sim **otimizar o Retorno Ajustado ao Risco (RAROC)**, provando que é possível crescer em concessão de crédito ao mesmo tempo em que se reduz o custo de provisão, alinhando-se às exigências regulatórias mais recentes.

---

### 1. A Tese de Valor Validada

Nosso modelo automatiza a identificação de clientes no ciclo vicioso de linhas caras e não-core (Cartão de Crédito Rotativo, Parcelamento da Fatura de Cartão de Crédito e Cheque Especial). Ao oferecer uma consolidação de dívida proativa, o projeto valida a seguinte melhoria estratégica:

> O **Modelo V2**, utilizando features comportamentais e sintéticas avançadas, atinge o **RAROC Máximo de 9.50%** com um **Threshold de Risco 10 vezes mais seletivo (0.10)** do que o modelo base.

---

## 2. Estrutura do Projeto e Fluxo de Valor

### Módulo 1: Fundamentação Comportamental e Feature Engineering [https://github.com/DeboraKlein/FinSight/blob/main/notebooks/01_fundamentacao_comportamental.ipynb]

* **Tese Central:** Intervir no **Estresse Agudo (< 30 dias)** para evitar a negativação e reter o cliente.
* **Feature Engineering:** Construção de **variáveis sintéticas de alto poder preditivo** com base em *domain expertise* e dados macro (BACEN/ANBIMA).
* **Features-Chave:** `freq_uso_rotativo_3m` (uso da linha mais cara), `bandeira_risco_aposta` (proxy para risco comportamental), `percentual_renda_comprometida_SCR` (viabilidade da solução).

### Módulo 2: Sustentabilidade Financeira e Otimização de Capital [https://github.com/DeboraKlein/FinSight/blob/main/notebooks/02_sustentabilidade_financeira.ipynb]

* **Pilar Contábil (PECLD / IFRS 9):** O modelo adere à **Resolução CMN nº 4.966/2021 (IFRS 9)** ao focar na Perda Esperada (**PECLD**). A intervenção proativa identifica clientes em risco de migrar do Estágio 1 para o Estágio 2, **liberando capital** que estaria preso em provisões de *Lifetime*.
* **Pilar Estratégico (RAROC):** O *cut-off* é calibrado para **maximizar o RAROC** ($\mathbf{RAROC\ >\ \text{Custo de Capital}}$), garantindo que cada operação de crédito consolidado gere valor econômico.
* **Resultado V2:** Confirmação de que o *score* V2 captura a migração de Estágio de Risco, alinhando a modelagem ao requisito regulatório.

### Módulo 3: Modelagem Preditiva e Prova de Conceito [https://github.com/DeboraKlein/FinSight/blob/main/notebooks/03_modelagem_otimizacao.ipynb]

* **Modelo:** Implementação do **XGBoost** para treinamento preditivo do Target de Estresse Agudo.
* **Otimização do Cut-off:** Processo iterativo para encontrar o **threshold ótimo** que equilibra a concessão de crédito com o Retorno Ajustado ao Risco (RAROC).
* **Comprovação da Tese (V2 vs V1):** Geração do gráfico de otimização que demonstra o deslocamento do ponto de máxima rentabilidade, provando que o modelo aprimorado (V2) é mais lucrativo e seletivo.

---

## 3. Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

### Resumo Executivo: Ganhos Reais com Sustentabilidade

Este projeto propõe uma solução de intervenção de crédito proativa baseada em Machine Learning (ML) avançado para Fintechs.

O ML identifica clientes em **Estresse Agudo** (evitando o atraso e o efeito bola de neve) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cheque Especial, Cartão Rotativo e Parcelamento de Fatura) por um empréstimo com taxas de juros significativamente mais baixas.

Essa abordagem de valor gera uma percepção positiva no cliente, ao demonstrar a economia real obtida na liquidação das dívidas caras, e preserva seus limites de crédito. Para a instituição, resulta na mitigação imediata do risco, na redução da inadimplência, na fidelização do cliente e na liberação de operação de crédito.

O foco não é apenas evitar o *default*, mas sim **otimizar o Retorno Ajustado ao Risco (RAROC)**, provando que é possível crescer em concessão de crédito ao mesmo tempo em que se reduz o custo de provisão, alinhando-se às exigências regulatórias mais recentes.

### A Tese de Valor Validada
Nosso modelo automatiza a identificação de clientes no ciclo vicioso de linhas caras e não-core (Cartão de Crédito Rotativo, Parcelamento da Fatura de Cartão de Crédito e Cheque Especial). Ao oferecer uma consolidação de dívida proativa, o projeto valida a seguinte melhoria est...

---

## 4. Resultados Finais Validados (ROI)

| Métrica de Negócio | Valor Validado (Modelo V2) | O Ganho Real |
| :--- | :--- | :--- |
| **Poder Preditivo (AUC)** | **0.8532** | Alto poder de discriminação, permitindo a identificação proativa do Estresse Agudo. |
| **RAROC Otimizado (Pitch)** | **3640.00%** (vs. Meta 9.50%) | **Máximo Retorno!** A taxa de **5.5% a.m.** (Tese usada no modelo com base nas taxas praticadas no mercado financeiro) maximiza o *spread* sem aumentar o risco, gerando $\mathbf{383 \text{ vezes}}$ a meta mínima de rentabilidade. |
| **Threshold Ótimo** | **0.10** (10x mais seletivo que o V1) | Máxima Seletividade: Garante a concessão de crédito apenas para o grupo de máximo retorno (RAROC), reduzindo custos de marketing e protegendo o capital de risco. |