# 📊 Executive Sales Analytics Dashboard

Dashboard interativa de suporte à decisão comercial desenvolvida em ficheiro único (`index.html`), concebida para responder a perguntas estratégicas sobre receita, sazonalidade e canais de liquidez.

🔗 **Acesso à Dashboard Online:** [https://josecelsodelucas2-lgtm.github.io/dashboard-vendas/](https://josecelsodelucas2-lgtm.github.io/dashboard-vendas/)

---

## 🎯 Perguntas de Negócio Respondidas

A estrutura analítica foi planeada para separar a tomada de decisão do mero acúmulo de gráficos:

1. **Quais os produtos/modelos que concentram o maior volume de receita e sustentam a margem operacional?**
   - **Justificação:** A identificação da concentração de faturação (Princípio de Pareto) é essencial para otimizar a gestão de inventário e direcionar o esforço comercial para os itens de maior retorno financeiro.
   - **Indicador/Visual:** Gráfico de barras horizontais ordenado por volume de receita bruta.

2. **Como se comporta a curva temporal de vendas e quais os períodos de sazonalidade?**
   - **Justificação:** Permite visualizar padrões de pico e retração ao longo dos anos, facilitando o planeamento de fluxo de caixa e a antecipação de compras com fornecedores.
   - **Indicador/Visual:** Gráfico de linha/área temporal contínua com histórico consolidado.

3. **Qual é o perfil de liquidez e a dependência dos meios de pagamento?**
   - **Justificação:** A distribuição por métodos de pagamento (Pix, Cartão de Crédito, Boleto) impacta diretamente os prazos médios de recebimento (D+0 vs D+30), as taxas de intermediação e a mitigação de inadimplência.
   - **Indicador/Visual:** Gráfico de rosca (*donut*) com proporção percentual dos canais de pagamento.

---

## 🤖 Engenharia de Prompt e Refinamentos

* **Abordagem Adotada:** Desenvolvimento via **ChatGPT com Canvas** para geração iterativa de código front-end e componentização analítica.
* **Prompt Inicial:**
  > *"Crie uma dashboard executiva em arquivo único HTML usando Tailwind CSS e Chart.js. Preciso responder quais produtos faturam mais, a evolução temporal das vendas e os métodos de pagamento mais usados. A página deve conter filtros por ano, cidade, modelo e método de pagamento, além de 4 cards de KPIs no topo e uma tabela analítica."*
* **Evolução até à Versão Final:**
  * **Tratamento de Estado Vazio:** Adicionada rotina de proteção para que a ausência de dados após a combinação de filtros não provocasse erros na renderização dos gráficos.
  * **Formatação Monetária Localizada:** Implementada a formatação padronizada em Real (`R$`) com suporte nativo via `Intl.NumberFormat('pt-BR')`.
  * **Reatividade Global:** Garantida a atualização simultânea dos 4 cartões de KPI, dos 3 gráficos e da grelha de dados a cada interação nos controlos de filtro.
  * **Exportação Analítica:** Implementado o botão de descarregamento dinâmico para ficheiro `.csv` a partir dos dados filtrados no ecrã.

---

## 🧹 Tratamento e Sanitização da Base de Dados

Antes da integração no código da aplicação, a base de dados passou pelas seguintes etapas de higienização:

1. **Eliminação de Inconsistências:** Remoção de registos duplicados, linhas com valores nulos (`NULL`) e registos marcados como `INVALID`.
2. **Normalização Numérica:** Conversão das colunas de faturação, preços e margens em valores numéricos puros (sem símbolos de moeda agregados como texto) e anos como números inteiros, eliminando referências de fórmulas quebradas.
3. **Padronização Categórica:** Limpeza de espaços em branco (*trim*) e unificação da capitalização de texto para modelos, cidades e meios de pagamento.
4. **Privacidade e Embutimento:** Os dados foram convertidos num formato JSON estático integrado diretamente no ficheiro HTML, assegurando que nenhuma informação pessoal identificável (PII) ou sensível fosse exposta no repositório.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5 / JavaScript Moderno:** Arquitetura *single-file* sem dependência de ambientes de compilação ou servidores *backend*.
* **Tailwind CSS (via CDN):** Desenho de interface responsiva e paleta corporativa moderna em tons escuros (*Dark Slate/Indigo*).
* **Chart.js (via CDN):** Renderização vetorial e interativa de gráficos de barras, linhas e roscas.
* **FontAwesome (via CDN):** Iconografia para suporte visual aos cartões de KPI.

---

## 📸 Demonstração do Projeto

### Visão Geral da Dashboard
<img width="1920" height="1032" alt="Captura de tela 2026-09-29 153643 yu" src="https://github.com/user-attachments/assets/79cbfc9d-3895-4d71-b4ae-96e74b65ac0b" />
<img width="1920" height="1032" alt="imagem" src="https://github.com/user-attachments/assets/a4004f0b-15a8-4a23-b9ea-06e66edea853" />



### Aplicação de Filtros Combinados

<img width="1920" height="1032" alt="solap" src="https://github.com/user-attachments/assets/b0c8a819-81de-4972-95aa-43810dfbb6e9" />
<img width="1920" height="1032" alt="titan" src="https://github.com/user-attachments/assets/7c515692-cf6c-49f9-a2c9-a305afb61b1e" />
<img width="1920" height="1032" alt="Captura de tela 2026-09-29 154631" src="https://github.com/user-attachments/assets/bbfc2ab3-a233-4c6f-94d0-d11ed6bbba00" />
<img width="1920" height="1032" alt="imagem" src="https://github.com/user-attachments/assets/221b8583-7d0c-4971-b9ce-e8d0e250485b" />

---

## 💻 Como Executar Localmente

1. Clone o repositório:
   ```bash
   git clone [https://github.com/josecelsodelucas2-lgtm/dashboard-vendas.git](https://github.com/josecelsodelucas2-lgtm/dashboard-vendas.git)
