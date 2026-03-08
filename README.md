# Dashboard de Gestão de Sinistros e Segurança de Frota

## 📌 Sobre o Projeto

Este projeto consiste em uma solução de Business Intelligence desenvolvida no **Power BI** para o setor de Logística, focada no monitoramento e análise detalhada de sinistros (acidentes e ocorrências operacionais).

O dashboard permite que gestores de frota e segurança do trabalho identifiquem padrões de acidentes, analisem a severidade financeira das ocorrências e tomem decisões baseadas em dados para reduzir riscos e custos operacionais.

### 💡 Por que este projeto é importante?

A gestão de sinistros é vital para a sustentabilidade de qualquer operação logística. Este projeto agrega valor ao negócio através de:

* **Redução de Custos:** Identificação dos tipos de eventos que mais oneram a operação (ex: Tombamentos) para aplicação de treinamentos focados.
* **Segurança Viária:** Análise da "Km por Sinistro" para medir a eficiência das políticas de segurança da frota.
* **Cultura de Prevenção:** Visualização clara da árvore de causalidade, permitindo entender em quais dias e setores as falhas são mais recorrentes.
* **Gestão de Passivo:** Monitoramento detalhado do impacto financeiro entre custos próprios e de terceiros.

---

## 🛡️ Disclaimer e Privacidade (Dados Anonimizados)

Para fins de portfólio:
* **Privacidade:** Todos os nomes de funcionários, cidades e valores financeiros exatos foram totalmente **anonimizados**.
* **Integridade:** As métricas de performance e relações de causa/efeito foram preservadas para demonstrar a capacidade analítica da ferramenta.

---

## 🛠️ Detalhes das Visões

O dashboard está estruturado em quatro camadas principais de análise:

### 1. Visão Executiva e Tendências
Esta tela fornece o panorama macro da operação, mostrando o ranking de incidência por departamento e a evolução histórica da sinistralidade.

**Destaques:**
* Acompanhamento da tendência de 2021 a 2026.
* Sazonalidade semanal para identificar dias críticos.
* Atribuição de responsabilidade (Próprio vs. Terceiro).

<img width="1442" height="809" alt="panoramaExecutiva" src="https://github.com/user-attachments/assets/6c453271-046c-4fbb-8de7-20adacd65a01" />
*Figura 1: Panorama Executivo de Ocorrências.*

### 2. Performance e Eficiência da Frota
Focada nos veículos, esta visão utiliza indicadores de eficiência para comparar diferentes categorias (Caminhão, Carro e Moto).

**Destaques:**
* KPI de **Km por Sinistro** por categoria.
* Distribuição percentual da frota envolvida em sinistros.

<img width="1443" height="813" alt="performanceFrota" src="https://github.com/user-attachments/assets/29715a05-e2bd-47a2-a305-48741b366281" />
*Figura 2: Indicadores de Performance por Categoria de Veículo.*

### 3. Impacto Financeiro e Severidade
Uma análise profunda sobre onde o dinheiro está sendo gasto e qual a gravidade dos eventos.

**Destaques:**
* Passivo financeiro detalhado por departamento.
* Ranking de custos por tipo de evento (ex: Tombamentos e Queda de Carga).
* Correlação entre Volume de Sinistros e Gasto Total.

<img width="1443" height="812" alt="custos" src="https://github.com/user-attachments/assets/645a264b-02ca-45e1-9909-8a7e3b658e7b" />
*Figura 3: Análise de Custos e Severidade Financeira.*

### 4. Diagnóstico e Árvore de Causalidade
Ferramenta de drill-down para investigação de causas raiz, utilizando uma árvore de decomposição.

**Destaques:**
* Navegação por Setor -> Semana do Mês -> Dia da Semana.
* Identificação precisa de picos de ocorrência em turnos ou períodos específicos.

<img width="1446" height="811" alt="arvoreCausalidade" src="https://github.com/user-attachments/assets/ca44e45c-6d2f-4928-8b74-a9e51dd5b645" />
*Figura 4: Árvore de Causalidade para Investigação de Incidentes.*

---

## 🏗️ Estrutura de Dados e Relacionamentos

A arquitetura do projeto foi desenhada para suportar cruzamentos complexos entre quilometragem rodada e sinistros ocorridos.

<img width="842" height="503" alt="relacionamentos" src="https://github.com/user-attachments/assets/2a980c3c-0865-4efa-86dd-4b2e97d50317" />
*Figura 5: Modelo de Dados (Star Schema).*

### Entidades Principais:
* **fOcorrencias (Fato):** Registro detalhado de cada sinistro (Data, Tipo, Culpado, Valores).
* **fKmRodadoFrota (Fato):** Dados de quilometragem para cálculo de indicadores de exposição ao risco.
* **dFuncionarios / dCalendario / dOrdemSemana:** Dimensões que permitem a filtragem e segmentação das métricas.
* **_Medidas:** Tabela centralizada de cálculos DAX (Gasto Total, Km por Sinistro, etc.).
