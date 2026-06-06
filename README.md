# 🖥️ Banco de Dados — Inteligência Operacional para Assistência Técnica

Este projeto apresenta o desenvolvimento e a modelagem de um banco de dados relacional para um sistema de ordens de serviço. O objetivo principal é estruturar os dados operacionais de forma eficiente para garantir a integridade das transações e permitir a posterior **extração de indicadores analíticos de performance (KPIs)**.

---

## 📋 Contexto do Negócio e Objetivos

O sistema foi desenhado para resolver dores operacionais de uma empresa de assistência técnica, permitindo o rastreamento completo da jornada do cliente e a eficiência da equipe técnica. 

**Foco analítico do modelo:**
* Monitorar o tempo de atendimento desde a abertura até a finalização.
* Avaliar a produtividade e carga de trabalho por técnico.
* Identificar o faturamento por tipo de serviço e categorias mais demandadas.

---

## 🗂️ Arquitetura e Modelagem de Dados

O banco foi estruturado seguindo as regras de normalização para evitar redundâncias e garantir consistência na escrita dos dados.

### Dicionário de Entidades (Transacionais e Cadastrais)

| Tabela | Tipo de Dado | Função no Ecossistema |
| :--- | :--- | :--- |
| **Cliente** | Cadastro (Dimensão) | Identificação, localização e contato dos clientes. |
| **Tecnico** | Cadastro (Dimensão) | Controle da equipe interna operacional e especialidades. |
| **Servico** | Cadastro (Dimensão) | Tabela preço e catálogo de serviços disponíveis. |
| **OrdemServico** | Transacional (Fato) | Registro central da operação, status, datas e vínculos principais. |
| **Finalizacao** | Transacional (Fato) | Histórico de encerramento, métricas de tempo e feedback/laudo. |
| **OrdemServico_Servico** | Relacionamento (N:M) | Tabela associativa que permite múltiplos serviços em uma mesma OS. |

---

## 🚀 Consultas Analíticas (SQL)

O script `empresa.sql` foi desenvolvido em **MySQL** e inclui, além da criação das tabelas e chaves (PK/FK), consultas prontas com foco em responder perguntas de negócio, utilizando:
* **Joins** Para consolidação de relatórios unificados.
* **Funções de Agregação (`SUM`, `COUNT`, `AVG`):** Para cálculo de faturamento e volumetria.
* **Manipulação de Datas (`DATEDIFF`):** Para cálculo automático de tempo de atendimento.

---

## 🛠️ Stack Tecnológica

* **SGBD:** MySQL 8.0
* **Ferramenta de Modelagem:** MySQL Workbench
* **Paradigma:** Banco de Dados Relacional (SQL)

---

## ⚙️ Como Executar e Explorar

1. Certifique-se de ter um servidor **MySQL** ativo na sua máquina.
2. Importe e execute o arquivo `empresa.sql` no seu client de preferência.
3. O script criará automaticamente a estrutura, aplicará as restrições de integridade e populará o banco com dados fictícios para testes de volumetria.
