# 🖥️ Banco de Dados — Empresa de Assistência Técnica

Trabalho desenvolvido para a disciplina de Banco de Dados.

## 📋 Descrição
Sistema de gerenciamento de ordens de serviço para uma empresa de assistência técnica, contendo o controle de clientes, técnicos, serviços e ordens de serviço.

## 🗂️ Estrutura do Banco de Dados

| Tabela | Descrição |
|---|---|
| `Cliente` | Dados dos clientes cadastrados |
| `Tecnico` | Técnicos responsáveis pelos atendimentos |
| `Servico` | Catálogo de serviços oferecidos |
| `OrdemServico` | Ordens de serviço (abertas, em execução ou concluídas) |
| `Finalizacao` | Detalhes do encerramento de cada ordem |
| `OrdemServico_Servico` | Serviços vinculados a cada ordem |

## ⚙️ Como executar
1. Ter o **MySQL** instalado
2. Abrir o arquivo `empresa.sql` no MySQL Workbench ou similar
3. Executar o script completo

## 🛠️ Tecnologia
- MySQL
