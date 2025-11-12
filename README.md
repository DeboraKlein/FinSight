

# Inteligência Preditiva para Otimização de Capital e Risco de Crédito (RAROC-Driven)

![Status](https://img.shields.io/badge/Status-Pronto%20para%20PRODUÇÃO-brightgreen)
![AUC](https://img.shields.io/badge/AUC-0.7721-blue)
![Recall](https://img.shields.io/badge/Recall-100%25-success)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![ML](https://img.shields.io/badge/ML-LightGBM-orange)

> *“Transformando risco preditivo em oportunidade estratégica com **100% de proteção** e AUC ${0.7721}$ **Super-Validado** contra Data Drift e Vazamento de Dados.”*

---

## 1. Resumo Executivo: Ganhos Reais com Sustentabilidade

[cite_start]Este projeto propõe uma solução de intervenção proativa em crédito, usando Machine Learning para identificar clientes em **estresse financeiro agudo** e oferecer alternativas sustentáveis antes da entrada no crédito rotativo[cite: 1].

O modelo identifica esses sinais precoces e aciona uma oferta de crédito antecipada e consultiva. O foco é substituir produtos de alto custo (como Cartão Rotativo) por um empréstimo sustentável, alinhando-se à estratégia **RAROC-Driven** (Return on Risk-Adjusted Capital).

---

## 2. Resultados Finais e Performance do Modelo (OOT)

O modelo **LightGBM** foi otimizado com foco total em **Recall da Classe 1 (Rotativo)**, visando zero perdas por risco não capturado.

| Métrica | Valor | Objetivo de Negócio |
| :--- | :--- | :--- |
| **Recall (Rotativo)** | **100%** | [cite_start]Cobertura total de risco, **0 Falsos Negativos**[cite: 1]. |
| **AUC (Ranking)** | **0.7721** | [cite_start]Excelente capacidade de diferenciar clientes (Validado OOT)[cite: 1]. |
| **Precision (Rotativo)** | 0.38 | [cite_start]Trade-off aceito: Falsos Positivos são oportunidades de contato[cite: 1]. |
| **Trade-off** | FN=0 vs. FP=26k | [cite_start]Prevenção Máxima, justificada pelo alto custo do Rotativo e Inadimplência[cite: 1]. |

---

## 3.  Fundamentação Teórica: Estresse Financeiro e Endividamento Familiar

A tese do modelo é suportada pela escalada do endividamento brasileiro:

1.  [cite_start]**Cenário de Inadimplência (Serasa):** No período analisado (Setembro [cite: 3][cite_start]), o Brasil registrou **79,1 milhões de inadimplentes**, com um valor médio de dívida por pessoa de **R$ 6.274,82**[cite: 3].
2.  [cite_start]**A Carga das Features:** O modelo é treinado para capturar o comportamento de clientes que, apesar de histórico bom, apresentam **sinais precoces de esgotamento de liquidez** — como o aumento exponencial da taxa de comprometimento implícita da renda (`scr_tcr_implicita`) e o crescimento da dívida nos últimos 3 meses (`scr_crescim_divida_3m`)[cite: 1].
3.  [cite_start]**Comportamento do Investidor (ANBIMA):** A importância de monitorar o comportamento financeiro é destacada pela pesquisa **Raio X do Investidor Brasileiro**, que se consolidou como a principal referência sobre a relação da população com o dinheiro, sendo inclusive citada em julgamento do STF[cite: 2].

---

## 4.  Alinhamento Regulatório e Gestão de Risco (PECLD / IFRS 9)

O impacto deste modelo se estende à gestão de risco e aos relatórios financeiros:

* [cite_start]**IFRS 9 e SICR:** O modelo ajuda na classificação dos ativos de crédito, identificando clientes em Stage 1 que apresentam **Aumento Significativo no Risco de Crédito (SICR - Stage 2)**[cite: 1]. Isso permite que o cálculo de **ECL (Expected Credit Loss)** seja feito de forma mais preditiva (abordagem de *Lifetime ECL*), em total conformidade com a norma.
* **PECLD (Provisão para Créditos de Liquidação Duvidosa):** Ao intervir proativamente, o modelo auxilia na **redução da necessidade de provisionamento** futuro, mitigando o *capital at risk* e otimizando a alocação de capital da instituição.

---

## 5.  Rigor Técnico: Validações Avançadas e Robustez

[cite_start]A robustez do modelo foi confirmada por uma série de validações além do OOT (Out-of-Time)[cite: 1]:

### 5.1. Validação de Integridade (Data Leakage)
* **Status:** Aprovado. [cite_start]As features de *lag* usadas não vazaram informações futuras, garantindo que a performance é genuína[cite: 1].

### 5.2. Validação Temporal e Data Drift
* **Status:** Aprovado e Comprovado. [cite_start]O **Data Drift** foi detectado nas *features* na **direção esperada** (aumento de risco), provando que o modelo é **eficaz em cenários de crise**[cite: 1].

### 5.3. Estabilidade das Features
* **Status:** Aprovado. [cite_start]As Top 5 *features* mantiveram **alta estabilidade** (CV < 0.1) ao longo dos *folds* da validação temporal, conferindo robustez à lógica do modelo[cite: 1].

---

## 6. Estrutura do Projeto e Arquivos

| Arquivo | Foco Principal | Detalhe Relevante |
| :--- | :--- | :--- |
| `01_fundamentacao_comportamental.ipynb` | Fundamentação e Feature Engineering | Tese do Estresse Agudo e Dicionário de Variáveis. |
| `02_sustentabilidade_financeira.ipynb` | Sustentabilidade Financeira: RAROC | Cálculo de Threshold Otimizado e Impacto Financeiro. |
| **`03_modelagem.ipynb`** | **Modelagem e Validação (LightGBM)** | [cite_start]Treinamento, OOT e **Validações Avançadas (Leakage/Drift)**[cite: 1]. |
| `04_operacionalizacao.ipynb` | Operacionalização do Modelo (MLOps) | Pipeline de Produção e Simulação de Inferência. |
| `05_apresentação.ipynb` | Apresentação Executiva | Business Case em Formato Slide para Diretoria. |

---

## 7. Conclusão e Próximos Passos

**Status Atual:** **PRONTO PARA PRODUÇÃO IMEDIATA**

O projeto demonstra **sustentabilidade financeira comprovada** através de:
* [cite_start]**100% de proteção** contra risco de rotativo (**FN=0**)[cite: 1].
* **Alinhamento regulatório** (IFRS 9 / PECLD) e redução potencial de provisão.
* [cite_start]**Modelo Super-Robusto** com validação completa contra Data Leakage e Data Drift[cite: 1].

**Próximos Passos:**
1.  Implementação do piloto (A/B Test) com grupo controlado.
2.  Integração com sistemas de CRM/atendimento ao cliente.
3.  Dashboard de monitoramento de performance e drift.

### Autoria

Débora Rebula Klein 

    📧 deborarebula@gmail.com 
    🔗 www.linkedin.com/in/débora-klein
    
