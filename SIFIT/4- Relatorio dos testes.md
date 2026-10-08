# ✅ Relatório de Execução de Testes — Ciclo 01 (SIFIT)

**Sistema Avaliado:** SIFIT - Sistema para Academias (Centrion Web)  
**Instituição:** UniALFA - Centro Universitário Alves Faria  
**Disciplina:** Extensão - Qualidade de Software  
**Orientador:** Prof. Adnys Lougan da Silva  
**QA Responsável:** Aluno QA  
**Ciclo de Entrega:** Ciclo 01 (Formulários Críticos Iniciais)  
**Status da Rodada:** ⏳ Casos Especificados — Aguardando Execução dos Testes  
**Data:** 2026-10-07  
**Ambiente:** Ambiente Web Homologação | DB MySQL Homologação  

---

## 📊 1. Resumo do Planejamento da Execução (Ciclo 01)

| Métrica de Qualidade | Quantidade Planejada | Status Atual |
| :--- | :---: | :---: |
| **Total de Casos de Teste Especificados** | 8 | Concluído (Especificação) |
| **Casos Aprovados (Passed)** | 0 | *Aguardando Execução* |
| **Casos Reprovados / Com Falha (Failed)** | 0 | *Aguardando Execução* |
| **Total de Bugs Identificados** | 0 | *Aguardando Execução* |
| **Cobertura Planejada dos 3 Módulos Iniciais** | 100% | *Pronto para Execução* |

---

## 🔍 2. Relação de Casos de Teste do Ciclo 01

| ID Caso | Módulo | Título Resumido | Tipo | Resultado da Execução |
| :---: | :--- | :--- | :---: | :---: |
| **C01-CT01** | Autenticação | Login com credenciais válidas | Positivo | ⏳ *Aguardando Execução* |
| **C01-CT02** | Autenticação | Tentativa de login com senha incorreta | Negativo | ⏳ *Aguardando Execução* |
| **C01-CT03** | Autenticação | Prevenção de duplo clique no botão | Negativo | ⏳ *Aguardando Execução* |
| **C02-CT01** | Clientes | Cadastro completo de novo aluno | Positivo | ⏳ *Aguardando Execução* |
| **C02-CT02** | Clientes | Validação de campos obrigatórios vazios | Negativo | ⏳ *Aguardando Execução* |
| **C02-CT03** | Clientes | Validação do algoritmo de CPF | Negativo | ⏳ *Aguardando Execução* |
| **C03-CT01** | Matrículas | Realização de nova matrícula para aluno | Positivo | ⏳ *Aguardando Execução* |
| **C03-CT02** | Matrículas | Validação de data de término anterior ao início | Negativo | ⏳ *Aguardando Execução* |

---

## 🗄️ 3. Plano de Auditoria no Banco de Dados (MySQL Workbench)

Durante a execução manual, as operações serão conferidas diretamente nas tabelas correspondentes:

* **Tabela `usuarios`**: Conferir integridade de acessos e logins de operadores.
* **Tabela `clientes`**: Conferir se os novos registros inseridos no formulário web são persistidos com os campos corretos (`SELECT * FROM clientes ORDER BY id DESC LIMIT 5`).
* **Tabela `matriculas`**: Conferir geração de vínculos entre aluno e plano e datas de vigência.

---

## 📝 4. Próximos Passos

1. **Executar a Rodada de Testes**: Preencher os resultados (`Passou` / `Falhou`) para cada um dos 8 casos.
2. **Coleta de Evidências**: Salvar prints na pasta `evidencias/` e links de gravações via extensão Jam.
3. **Registro de Bugs**: Caso haja divergências entre o esperado e o obtido, registrar no arquivo `3-Relatorio-de-Bugs.md`.
4. **Consolidação das Métricas**: Atualizar este relatório com os percentuais finais da rodada.
