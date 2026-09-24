# 📈 Simulador e Projeção de Índice de Perda (Fundo Garantidor)

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-00599C?style=for-the-badge&logo=microsoft&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Governance](https://img.shields.io/badge/Data_Governance-LGPD-green?style=for-the-badge)

🌐 **Idioma / Language:** [Português](README.md) | [English](README_EN.md)

## 📌 Visão Geral do Projeto

Este projeto consiste em uma solução analítica e simuladora desenvolvida em **Power BI** para monitoramento e projeção do **Índice de Perda (IP)** de um Fundo Garantidor de Crédito. 

O objetivo principal é permitir que gestores de risco avaliem o impacto de novos aportes, estimativas de honras (inadimplência) e recuperação de ativos nos próximos **8 meses**, garantindo que a carteira permaneça dentro dos limites operacionais de *Stop Loss*.

> 🔒 **Nota de Governança e Compliance:** Para preservar a confidencialidade das instituições financeiras parceiras e dos volumes financeiros do Fundo, os dados passaram por um rigoroso processo de anonimização (desvinculação de nomes de bancos para chaves genéricas como *Banco 01, Banco 02*) e aplicação de fatores de escala nas métricas numéricas.

---

## 🛠️ Solução Técnica & Arquitetura DAX

O painel foi estruturado sobre um modelo de dados dinâmico, utilizando conceitos avançados de **janela móvel de 60 meses**, **expurgo rolante de dados históricos** e **parâmetros de simulação (What-If)**.

### 💡 Principais Destaques de Implementação:

* **Janela Móvel Temporal (60 Meses):** Cálculo contínuo dos últimos 5 anos de operação para determinar a taxa de sinistralidade real por instituição.
* **Algoritmo de Expurgo e Projeção:** À medida que a simulação avança nos meses ($Mês +1$ até $Mês +8$), a lógica DAX expurga os meses mais antigos do histórico real e adiciona os novos fluxos simulados.
* **Stop Loss Híbrido:** Regra de negócio que alterna dinamicamente a régua de limite regulamentar de acordo com a seleção do usuário (Visão Individual do Banco vs. Visão Consolidada do Fundo).
* **Parâmetros What-If Dinâmicos:** Interface interativa que permite simular em tempo real os volumes de *Garantia Mensal*, *Honra Mensal* e *Recuperação Mensal*.

---

## 📂 Estrutura das Medidas DAX

As regras de negócio e fórmulas de projeção foram documentadas e consolidadas no repositório. A arquitetura divide-se nas seguintes categorias:

| Categoria | Descrição / Lógica de Negócio | Medidas Chave |
| :--- | :--- | :--- |
| **Métricas Base** | Apuração dos volumes históricos de Garantia, Honra e Recuperação na janela de 60 meses. | `vlr-garantido_60meses`, `vlr-honrado_60meses`, `vlr-recuperado_60meses` |
| **Régua de Risco** | Identificação dinâmica do teto tático de *Stop Loss* por instituição financeira. | `StopLoss_Dinamico_Hibrido`, `dt_corte` |
| **Motor de Projeção** | Cálculo de expurgo retroativo + incremento dos parâmetros *What-If* para o horizonte de 8 meses. | `IP_Linha_Tendencia`, `index_IP_simulado-1` a `8` |
| **UX & Dinâmica** | Formatação condicional de títulos e avisos de interface com base na interação do usuário. | `Titulo_Grafico_Historico`, `Titulo_Grafico_Simulacao` |

## 📂 Medidas DAX
* 📄 **Versão em Português:** [`dax/medidas_simulador.dax`](./dax/medidas_simulador.dax)
* 📄 **Versão em Inglês:** [`dax/measures_simulator.dax`](./dax/measures_simulator.dax)

## 💻 Visualização do Painel

*(Insira aqui os prints do seu dashboard higienizado)*

* **Visão Histórica:** Acompanhamento do comportamento da carteira frente à linha de *Stop Loss*.
* **Painel de Simulação:** Projeção da linha de tendência nos cenários de $Mês +1$ a $Mês +8$ conforme variação dos seletores.

---

## 🎯 Impacto para o Negócio

1. **Prevenção de Desenquadramento:** Permite identificar previamente se uma instituição atingirá o limite de sinistralidade antes do fechamento oficial.
2. **Tomada de Decisão Baseada em Dados:** Suporta o comitê de crédito na aprovação de novos limites de garantia com base em cenários simulados.
3. **Maturidade em Governança:** Demonstração prática de manipulação de dados sensíveis com segurança e conformidade corporativa.
