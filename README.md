# 📈 Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

## Resumo Executivo: Ganhos Reais com Sustentabilidade

Este projeto propõe uma solução de **intervenção de crédito proativa** baseada em Machine Learning (ML) avançado para Fintechs.

O modelo identifica clientes em **Estresse Agudo** (evitando o efeito bola de neve da dívida) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cartão Rotativo e Parcelamento de Fatura) por um **empréstimo com taxas de juros significativamente mais baixas**.

Essa abordagem de valor resulta na **mitigação imediata do risco (Recall 89%)**, na fidelização do cliente e na otimização do **Retorno Ajustado ao Risco (RAROC)**, alinhando concessão de crédito com a redução do custo de provisão.

---

### 1. A Tese de Valor Validada

O modelo automatiza a identificação de clientes no ciclo vicioso de linhas caras e não-core (Cartão de Crédito Rotativo e Cheque Especial). Ao oferecer uma consolidação de dívida proativa, o projeto valida a seguinte melhoria estratégica:

* **De Reativo para Proativo:** Intervenção acionada pela probabilidade de risco ($y\_proba$), em vez de esperar o default.
* **Decisão Otimizada:** Utilização do **Threshold 0.20** para garantir o máximo retorno ajustado ao risco, em conformidade com as regras de PECLD (IFRS 9).
* **Vantagem Competitiva:** O custo do Falso Positivo ($\mathbf{68\%}$ no Threshold 0.20) é transformado em uma **oportunidade de fidelização** através de um atendimento consultivo de valor.

---

### 2. Arquitetura do Modelo e Validação

O projeto utiliza um modelo **LightGBM** (Machine Learning em Árvores de Decisão) com as seguintes características:

| Característica | Detalhe | Impacto |
| :--- | :--- | :--- |
| **Feature Engineering** | Foco em **Sinais Dinâmicos** (Janelas Móveis de 3 meses). | Validação da tese: o estresse agudo é o maior preditor de risco. |
| **Feature Top 1** | **`num__utilizacao_limite_media_3m`** | O esgotamento do limite do cartão é o principal sinal de alerta. |
| **Validação** | **Out-of-Time (OOT)** | Simulação do ambiente de produção (testado em período futuro), garantindo a robustez do modelo na prática. |

---

## 3. Resultados Finais Validados (ROI e Métricas de Negócio)

Os resultados abaixo representam a performance do modelo em produção, utilizando o **Threshold de Intervenção Otimizado ($0.20$)**:

| Métrica de Negócio | Valor Validado (Modelo Final) | O Ganho Real (Impacto Estratégico) |
| :--- | :--- | :--- |
| **Poder Preditivo (AUC)** | **0.7281** | Poder de discriminação realista e robusto para modelos de risco de crise. |
| **Recall da Classe de Risco** | **89%** | **MITIGAÇÃO DE RISCO:** O modelo identifica e permite **salvar 9 em cada 10 clientes** que entrariam no rotativo. |
| **Threshold de Ação** | **0.20** | Ponto de corte que maximiza o Retorno Ajustado ao Risco (RAROC). |
| **Viabilidade Operacional** | **Precision 32%** | O custo de **68% de Falsos Positivos** é convertido em uma Estratégia de Fidelização (Ofertas Consultivas). |

---

## 4. Estrutura de Operacionalização (MLOps)

O modelo está pronto para ser implementado em um pipeline de **Processamento em Lote (Batch)** para scoring diário:

1.  **Inferência:** Modelo gera a probabilidade ($y\_proba$) para toda a carteira.
2.  **Decisão:** Sistema aplica a regra $y\_proba \ge 0.20$.
3.  **Engajamento:** Clientes acionados via canais digitais ($0.20 \le y\_proba < 0.50$) ou Gerentes de Carteira ($y\_proba \ge 0.50$).
4.  **Monitoramento:** Acompanhamento contínuo da estabilidade do AUC e das *Features* para garantir que o **RAROC realizado** se mantenha próximo do **RAROC otimizado**.

---

### Navegação nos Notebooks

| Notebook | Título | Foco Principal |
| :--- | :--- | :--- |
| `01_fundamentacao_comportamental.ipynb` | Fundamentação e Feature Engineering | Tese do Estresse Agudo e Dicionário de Variáveis. |
| `02_sustentabilidade_financeira.ipynb` | Sustentabilidade Financeira | Cálculo e Otimização do **RAROC** para definir o **Threshold 0.20**. |
| `04_operacionalizacao_modelo.ipynb` | Operacionalização do Modelo | Fluxo de MLOps, Engajamento Proativo e Lógica de Decisão. |
| `07_glossário.ipynb` | Glossário do Projeto | Definição dos termos-chave com os valores finais validados. |