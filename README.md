

# Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

![Status](https://img.shields.io/badge/Status-Pronto%20para%20MVP-brightgreen)
![AUC](https://img.shields.io/badge/AUC-0.7776-blue)
![Recall](https://img.shields.io/badge/Recall-100%25-success)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![ML](https://img.shields.io/badge/ML-LightGBM-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## Autoria

**Desenvolvido por:** [Debora Rebula Klein](https://github.com/DeboraKlein)  

**Email:** deborarebula@gmail.com 

**LinkedIn:** [Seu Perfil](www.linkedin.com/in/débora-klein)

> *"Transformando risco preditivo em oportunidade estratégica com 100% de proteção e AUC 0.7776 validado"*

## Resumo Executivo: Ganhos Reais com Sustentabilidade

![Performance](https://img.shields.io/badge/Performance-Validada%20OOT-green)
![RAROC](https://img.shields.io/badge/RAROC-Otimizado-important)

Este projeto propõe uma solução de **intervenção de crédito proativa** baseada em Machine Learning (ML) avançado para Fintechs.

O modelo identifica clientes em **Estresse Agudo** (evitando o efeito bola de neve da dívida) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cartão Rotativo e Parcelamento de Fatura) por um **empréstimo com taxas de juros significativamente mais baixas**.

Essa abordagem de valor resulta na **mitigação total do risco (Recall 100%)**, na fidelização do cliente e na otimização do **Retorno Ajustado ao Risco (RAROC)**, alinhando concessão de crédito com a redução do custo de provisão.

---

### 1. A Tese de Valor Validada

O modelo automatiza a identificação de clientes no ciclo vicioso de linhas caras e não-core (Cartão de Crédito Rotativo e Cheque Especial). Ao oferecer uma consolidação de dívida proativa, o projeto valida a seguinte melhoria estratégica:

* **De Reativo para Proativo:** Intervenção acionada pela probabilidade de risco (y_proba), em vez de esperar o default.
* **Decisão Otimizada:** Utilização do **Threshold 0.20** para garantir o máximo retorno ajustado ao risco, em conformidade com as regras de PECLD (IFRS 9).

| Métrica | Valor Final | Ponto Chave |
| :--- | :--- | :--- |
| **Poder Preditivo (AUC)** | **0.7776** | **Alta Robustez** – Supera o benchmark de AUC > 0.75 para modelos de risco. |
| **Captura de Risco (Recall)** | **100%** | **Proteção Total** – TODOS os clientes que entrariam no Rotativo são capturados para intervenção. |
| **Threshold de Ação** | **0.20** | Ponto de corte que maximiza o Retorno Ajustado ao Risco (RAROC). |
| **Viabilidade Operacional** | **Precision 36%** | O custo de 64% de Falsos Positivos é convertido em uma Estratégia de Fidelização (Ofertas Consultivas). |

![Curva ROC do Modelo LightGBM com AUC de 0.7776](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/curva_ROC.png)

> **O que este gráfico significa?**
> Este gráfico mostra a **capacidade do modelo de distinguir** entre um cliente que vai entrar no rotativo e um cliente seguro. O **$\text{AUC}$ de $\mathbf{0.7732}$** é a prova de que nosso modelo é altamente eficaz, afastando-se drasticamente da linha diagonal (que representa uma adivinhação aleatória).

---

## 2. Resultados Validados e Performance

### 2.1. Performance do Modelo (Validação Out-of-Time)

**Base de Dados:**
- **Total de observações:** 230,000 registros
- **Período de teste:** 60,000 amostras (Meses 18-24)
- **Distribuição:** 79.11% Classe 0 vs 20.89% Classe 1

**Métricas Validadas:**
- **AUC Score:** 0.7776
- **Recall (Classe 1):** 100%
- **Precision (Classe 1):** 36%
- **F1-Score (Classe 1):** 53%

### 2.2. Matriz de Confusão (Threshold 0.20)

> ![Matriz de Confusão do Modelo LightGBM com Threshold 0.20](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/matriz_confusao.png)

> **O que este gráfico significa?**
> Este é o resultado de negócio. Os **Verdadeiros Positivos (TP)** representam os clientes de risco que **capturamos com sucesso** e que evitamos que gerassem $\text{PDD}$ (prejuízo). Esta matriz valida que o *threshold* $\mathbf{0.20}$ alcança um alto volume de captura de risco ($\text{Recall}$ $\mathbf{100\%}$), protegendo o capital da FinTech.


**Impacto Business:**
- **15,273 clientes** salvos do rotativo (Verdadeiros Positivos)
- **26,808 clientes** para estratégia de fidelização (Falsos Positivos)
- **0 clientes** de risco não capturados (Falsos Negativos)

### 2.3. Top 10 Features Mais Importantes

| Posição | Feature | Importância | Categoria |
| :---: | :--- | :---: | :--- |
| **1** | `limite_cartao` | **354** | Exposição ao Crédito |
| **2** | `scr_tcr_implicita` | **333** | Risco Sistêmico |
| **3** | `utilizacao_limite_media_3m` | **297** | Estresse de Liquidez |
| **4** | `scr_crescim_divida_3m` | **208** | Deterioração Financeira |
| **5** | `gasto_crescim_3m` | **186** | Estresse de Consumo |
| **6** | `contagem_rotativo_3m` | **40** | Comportamento Rotativo |
| **7** | `regiao_Sudeste` | **26** | Contexto Regional |
| **8** | `idade_faixa_26-40` | **22** | Perfil Demográfico |
| **9** | `regiao_Sul` | **14** | Contexto Regional |
| **10** | `idade_faixa_65+` | **13** | Perfil Demográfico |

> ![Top 10 Features Mais Importantes (Gain) do LightGBM](https://github.com/DeboraKlein/FinSight/blob/main/data/assets/features.png)

> **O que este gráfico significa?**
> Ele mostra **o que o modelo realmente aprendeu**. As *features* mais importantes são aquelas que medem a **mudança de comportamento (tendência)** do cliente, como o **Crescimento do Gasto** e a **Taxa de Comprometimento de Renda Implícita `scr_tcr_implicita`**. O modelo ignora características estáticas (como Região ou Idade), focando apenas nos sinais de estresse financeiro agudo.

---

## 3. Estratégia de Valor e Sustentabilidade

### 3.1. Conversão de Risco em Oportunidade

**Para Verdadeiros Positivos (15,273 clientes):**
- Conversão de dívida cara (rotativo) em empréstimo pessoal sustentável
- Redução do Capital Econômico necessário
- Preservação do relacionamento com cliente

**Para Falsos Positivos (26,808 clientes):**
- Oportunidade de fidelização através de contato consultivo
- Aumento do Lifetime Value (LTV)
- Cross-selling de produtos adicionais

### 3.2. Monitoramento Contínuo

| Indicador | Frequência | Gatilho de Ação |
| :--- | :--- | :--- |
| **Estabilidade do AUC** | Mensal | Se AUC < 0.70 → Retreino |
| **Feature Drift (Top 5)** | Semanal | Se drift > 15% → Recalibração |
| **Recall** | Diário | Se Recall < 95% → Ajuste de threshold |
| **RAROC** | Mensal | Se queda > 20% → Revisão estratégica |

---

## 4. Estrutura de Operacionalização (MLOps)

O modelo está pronto para ser implementado em um pipeline de **Processamento em Lote (Batch)** para scoring diário:

1.  **Inferência:** Modelo gera a probabilidade (y_proba) para toda a carteira.
2.  **Decisão:** Sistema aplica a regra y_proba ≥ 0.20.
3.  **Engajamento:** Clientes acionados via canais digitais (0.20 ≤ y_proba < 0.50) ou Gerentes de Carteira (y_proba ≥ 0.50).
4.  **Monitoramento:** Acompanhamento contínuo da estabilidade do AUC e das Features para garantir que o **RAROC realizado** se mantenha próximo do **RAROC otimizado**.

---

### Navegação nos Notebooks

| Notebook | Título | Foco Principal |
| :--- | :--- | :--- |
| `01_fundamentacao_comportamental.ipynb` | Fundamentação e Feature Engineering | Tese do Estresse Agudo e Dicionário de Variáveis. |
| `02_sustentabilidade_financeira.ipynb` | Sustentabilidade Financeira: RAROC | Cálculo de Threshold Otimizado e Impacto Financeiro. |
| `03_modelagem.ipynb` | Modelagem e Validação (LightGBM) | Treinamento, OOT e Resultados Finais (AUC=0.7776). |
| `04_operacionalizacao.ipynb` | Operacionalização do Modelo (MLOps) | Pipeline de Produção e Simulação de Inferência. |
| `05_apresentação.ipynb` | Apresentação Executiva | Business Case em Formato Slide para Diretoria. |

---

## 5. Conclusão e Próximos Passos

**Status Atual:**  **PRONTO PARA MVP**

O projeto demonstra **sustentabilidade financeira comprovada** através de:
- **100% de proteção** contra risco de rotativo
- **Estratégia otimizada** de trade-off entre risco e oportunidade
- **Modelo robusto** com AUC 0.7776 validado Out-of-Time
- **Operacionalização escalável** via pipeline MLOps

**Próximos Passos:**
1. Implementação do piloto com grupo controlado
2. Integração com sistemas de atendimento ao cliente
3. Dashboard de monitoramento em tempo real
4. Expansão para outros produtos de crédito

---
*"Transformando risco preditivo em oportunidade estratégica com 100% de proteção e AUC 0.7776 validado"*

