# simulador-indice-perda-fampestation
Simulador interativo de projeção do índice de perda e análise "What-If" para gestão de risco em fundo garantidor de crédito.

📊 Simulador e Projeção de Índice de Perda (Fundo Garantidor de Crédito)
⚠️ Aviso de Confidencialidade e Segurança de Dados:
Este projeto foi desenvolvido com base em cenários reais de análise de risco e concessão de crédito em fundos garantidores. Todos os dados, valores monetários, nomes de instituições parceiras e indicadores apresentados neste portfólio foram anonimizados e substituídos por dados sintéticos/fictícios, garantindo o sigilo das informações e a conformidade com as diretrizes de governança de dados.

1. Contexto
Em fundos garantidores de crédito, a manutenção de uma carteira saudável depende do monitoramento constante do volume de honras/inadimplência e do limite operacional aceitável por instituição financeira parceira. A ultrapassagem desse limite (Stop Loss) gera retrabalho, sanções operacionais e riscos à liquidez do fundo.

2. Problema
Os gestores de carteira necessitavam de uma ferramenta preditiva e de simulação em tempo real para avaliar o impacto das novas concessões e das estimativas de perda nos próximos 8 meses. Sem uma visão preditiva interativa, as negociações com as instituições financeiras operavam de forma reativa, aumentando a probabilidade de a carteira atingir a margem de Stop Loss.

3. Abordagem
Ferramenta Principal: Power BI (DAX Avançado, Parâmetros de Campos/O que acontece se, Power Query).

Modelagem: Integração do modelo semântico corporativo com tabelas de parâmetros customizadas para simulação de cenários.

Métricas-Chave: Saldo Devedor Projetado, Taxa Média de Inadimplência Histórica, Projeção de Perda Futura (8 meses), Margem até o Stop Loss.

4. Análise / Solução
Desenvolvimento de um Dashboard Simulador Interativo que permite aos gestores:

Inserir e alterar parâmetros de projeção de perda diretamente nos visuais.

Projetar dinamicamente a variação do índice de perda mês a mês para uma janela futura de 8 meses.

Comparar o índice projetado contra o teto do Stop Loss estabelecido no regulamento.

Simular diferentes cenários de ajuste na carteira junto às instituições parceiras antes do fechamento do ciclo.

5. Principais Achados / Impacto
Antecipação de Riscos: Capacidade de identificar potenciais estouros de limite (Stop Loss) com até 8 meses de antecedência.

Apoio a Negociações Estratégicas: Empoderamento dos gestores com dados simulados durante reuniões de alinhamento com instituições financeiras.

Redução da Inadimplência Potencial: Mudança de uma postura reativa para proativa na gestão de riscos de crédito garantido.

6. Aprendizados
Aplicação avançada de Tabelas de Parâmetros (What-If Analysis) no Power BI para cenários dinâmicos.

Importância da higienização e abstração de modelos de dados corporativos para prototipagem e apresentação de portfólio de forma segura.
