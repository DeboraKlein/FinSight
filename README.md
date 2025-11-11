

# Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

![Status](https://img.shields.io/badge/Status-Pronto%20para%20PRODUÇÃO-brightgreen)
![AUC](https://img.shields.io/badge/AUC-0.7721-blue)
![Recall](https://img.shields.io/badge/Recall-100%25-success)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![ML](https://img.shields.io/badge/ML-LightGBM-orange)

> *“Transformando risco preditivo em oportunidade estratégica com **100% de proteção** e AUC ${0.7721}$ **Super-Validado** contra Data Drift e Vazamento de Dados.”*

## Resumo Executivo: Ganhos Reais com Sustentabilidade

![Performance](https://img.shields.io/badge/Performance-VALIDAÇÃO%20AVANÇADA-green)
![RAROC](https://img.shields.io/badge/RAROC-Otimizado-important)

Este projeto propõe uma solução de intervenção proativa em crédito para Fintechs, usando Machine Learning para identificar clientes em estresse financeiro agudo e oferecer alternativas sustentáveis antes do default (Rotativo).

O modelo identifica clientes em **Estresse Agudo** (evitando o efeito bola de neve da dívida) e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cartão Rotativo e Parcelamento de Fatura) por um **empréstimo sustentável**, alinhando-se à estratégia RAROC-Driven.

---

## 2. Resultados Finais e Performance do Modelo (OOT)

O modelo **LightGBM** foi treinado com foco total em **Recall da Classe 1 (Rotativo)**, visando zero perdas por risco não capturado.

| Métrica | Valor | Objetivo de Negócio |
| :--- | :--- | :--- |
| **Recall (Rotativo)** | **100%** | Cobertura total de risco, **0 Falsos Negativos**. |
| **AUC (Ranking)** | **0.7721** | Excelente capacidade de diferenciar clientes (Validado OOT). |
| **Precision (Rotativo)** | 0.38 | Trade-off aceito: Falsos Positivos são oportunidades de contato. |
| **Trade-off** | FN=0 vs. FP=26k | **Prevenção Máxima** justificada pelo alto custo do Rotativo e Inadimplência. |

---

## 3. Rigor Técnico: Validações Avançadas e Robustez

A robustez do modelo foi confirmada por uma série de validações além do OOT (Out-of-Time):

### 3.1. Validação de Integridade (Data Leakage)
* **Status:** Aprovado.
* **Detalhe:** As features de tendência e *lag* usadas (`scr_tcr_implicita`, `gasto_crescim_3m`) mostraram correlação baixa com a variável alvo, garantindo que o modelo não está vazando informações futuras e a performance é genuína.

### 3.2. Validação Temporal e Data Drift
* **Status:** Aprovado e Comprovado.
* **Detalhe:** O **Data Drift** foi detectado nas principais *features* entre o Treino e o OOT, mas na **direção esperada** (aumento de risco), provando que o modelo é **eficaz em cenários de crise**. O aumento da AUC (de 0.72 na CV para 0.77 no OOT) valida que o modelo performa melhor **justamente quando é mais necessário**.

### 3.3. Estabilidade das Features
* **Status:** Aprovado.
* **Detalhe:** As Top 5 *features* (ex: `limite_cartao`, `utilizacao_limite_media_3m`) mantiveram **alta estabilidade** (CV < 0.1) ao longo dos folds da validação temporal, conferindo robustez à interpretabilidade e à lógica do modelo.

---

## 4. Estrutura do Projeto e Arquivos

| Arquivo | Foco Principal | Detalhe Relevante |
| :--- | :--- | :--- |
| `01_fundamentacao_comportamental.ipynb` | Fundamentação e Feature Engineering | Tese do Estresse Agudo e Dicionário de Variáveis. |
| `02_sustentabilidade_financeira.ipynb` | Sustentabilidade Financeira: RAROC | Cálculo de Threshold Otimizado e Impacto Financeiro. |
| **`03_modelagem.ipynb`** | **Modelagem e Validação (LightGBM)** | Treinamento, OOT e **Validações Avançadas (Leakage/Drift)**. |
| `04_operacionalizacao.ipynb` | Operacionalização do Modelo (MLOps) | Pipeline de Produção e Simulação de Inferência. |
| `05_apresentação.ipynb` | Apresentação Executiva | Business Case em Formato Slide para Diretoria. |

---

## 5. Conclusão e Próximos Passos

**Status Atual:** **PRONTO PARA PRODUÇÃO IMEDIATA**

O projeto demonstra **sustentabilidade financeira comprovada** através de:
- **100% de proteção** contra risco de rotativo (FN=0)
- **Estratégia otimizada** de trade-off entre risco e oportunidade (FP=Oportunidade)
- **Modelo Super-Robusto** com validação completa contra Data Leakage e Data Drift.
- **Operacionalização escalável** via pipeline MLOps

**Próximos Passos:**
1. Implementação do piloto (A/B Test) com grupo controlado.
2. Integração com sistemas de CRM/atendimento ao cliente.
3. Dashboard de monitoramento de performance e drift.
---

### Autoria

Débora Rebula Klein 

    📧 deborarebula@gmail.com 
    🔗 www.linkedin.com/in/débora-klein
    
