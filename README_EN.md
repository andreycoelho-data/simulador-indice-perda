# 📈 Loss Index Simulator & Projection (Guarantor Fund)

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-00599C?style=for-the-badge&logo=microsoft&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Governance](https://img.shields.io/badge/Data_Governance-LGPD-green?style=for-the-badge)

🌐 **Language / Idioma:** [Português](README.md) | [English](README_EN.md)

---

## 📌 Project Overview

This project features an analytical solution and interactive simulator developed in **Power BI** to monitor and project the **Loss Index (LI / IP)** for a Credit Guarantor Fund.

The primary objective is to enable risk managers to simulate and evaluate the impact of new guarantee injections, honor/default estimates, and asset recoveries over a **8-month forward horizon**, ensuring the portfolio remains strictly within regulatory *Stop-Loss* thresholds.

> 🔒 **Governance & Compliance Note:** To safeguard proprietary data and comply with financial privacy standards, all partner institution names have been fully anonymized (e.g., *Bank 01, Bank 02*), and scaling factors were applied to financial metrics.

---

## 🛠️ Technical Solution & DAX Architecture

The dashboard is built upon a dynamic data model utilizing advanced analytics concepts, such as a **60-month rolling window**, **historical data offloading/expunging**, and **What-If simulation parameters**.

### 💡 Key Technical Highlights:

* **Rolling Time Window (60 Months):** Continuous calculation across the last 5 operational years to evaluate the true loss ratio per financial institution.
* **Offloading & Projection Algorithm:** As the simulation moves forward through time ($Month +1$ to $Month +8$), the DAX logic systematically offloads the oldest historical months while incorporating new simulated inflows and outflows.
* **Hybrid Dynamic Stop Loss:** Business logic that dynamically toggles the regulatory threshold between individual bank views and the fund’s consolidated portfolio level.
* **Dynamic What-If Parameters:** Interactive user input controls allowing real-time scenario modeling for *Monthly Guarantee Injections*, *Monthly Honors*, and *Monthly Asset Recoveries*.

---

## 📂 DAX Measures Architecture

All business rules, time intelligence patterns, and projection formulas are fully documented in the repository. The architecture is categorized as follows:

| Category | Description / Business Logic | Key Measures |
| :--- | :--- | :--- |
| **Base Metrics** | Aggregation of historical Guarantee, Honor, and Recovery volumes within the 60-month window. | `vlr-garantido_60meses`, `vlr-honrado_60meses`, `vlr-recuperado_60meses` |
| **Risk Thresholds** | Dynamic identification of tactical *Stop-Loss* limits per institution or consolidated view. | `StopLoss_Dinamico_Hibrido`, `dt_corte` |
| **Projection Engine** | Logic handling historical data offloading combined with *What-If* parameter increments up to Month +8. | `IP_Linha_Tendencia`, `index_IP_simulado-1` to `8` |
| **UX & Interface** | Conditional formatting for titles, tooltips, and dynamic UI alerts based on user interactions. | `Titulo_Grafico_Historico`, `Titulo_Grafico_Simulacao` |

👉 **View the fully documented DAX scripts:** 
* [Portuguese Version (`medidas_simulador.dax`)](./dax/medidas_simulador.dax)
* [English Version (`measures_simulator.dax`)](./dax/measures_simulator.dax)

---

## 💻 Dashboard Preview

*(Insert high-resolution screenshots of your anonymized report here)*

* **Historical View:** Portfolio behavior vs. regulatory Stop-Loss threshold.
* **Simulation Panel:** 8-month trend projections driven by dynamic What-If parameters.

---

## 🎯 Business Impact

1. **Proactive Non-Compliance Prevention:** Enables early detection of potential threshold breaches before official financial period closes.
2. **Data-Driven Decision Making:** Empowers credit committees to evaluate and adjust guarantee allocation limits based on simulated risk scenarios.
3. **Enterprise Data Governance:** Demonstrates expertise in handling sensitive financial records with safety and strict regulatory compliance.
