# 🐞 Relatório de Bugs e Não Conformidades — Sistema SIFIT

**Sistema Avaliado:** SIFIT - Sistema para Academias  
**Ambiente:** Homologação Web SIFIT | DB: MySQL Homologação  
**QA Responsável:** Aluno QA  
**Ciclo:** Ciclo 01 (Formulários Iniciais)  
**Status do Ciclo:** ⏳ Em Planejamento / Aguardando Execução dos Testes  
**Data:** 2026-10-07  

---

## 📌 Tabela de Defeitos Identificados

> *Esta tabela será preenchida durante a execução dos casos de teste conforme falhas ou comportamentos inesperados forem identificados no sistema.*

| ID | Título do Bug | Módulo Afetado | Severidade | Prioridade | Status |
| :---: | :--- | :---: | :---: | :---: | :---: |
| *BUG-001* | *[A preencher após identificação de falha]* | *Autenticação* | - | - | *Pendente* |
| *BUG-002* | *[A preencher após identificação de falha]* | *Clientes* | - | - | *Pendente* |
| *BUG-003* | *[A preencher após identificação de falha]* | *Matrículas* | - | - | *Pendente* |

---

## 📋 Modelo Padrão de Registro de Bug (Template para Preenchimento)

Ao identificar um bug durante a execução dos testes no SIFIT, utilize a estrutura abaixo para documentá-lo:

```markdown
### 🐞 BUG-XXX: [Título Resumido da Não Conformidade]

| Atributo | Detalhe |
| :--- | :--- |
| **ID** | BUG-XXX |
| **Título** | [Descrição sucinta da falha] |
| **Severidade** | Crítica / Alta / Média / Baixa |
| **Prioridade** | Alta / Média / Baixa |
| **Status** | Aberto / Em Análise / Resolvido |
| **Módulo** | [Ex.: RF01 - Autenticação / RF02 - Clientes / RF03 - Matrículas] |
| **Caso de Teste Relacionado** | [Ex.: CT_RF01_ Login na plataforma.md] |

#### 📋 Passos para Reprodução:
1. Acessar a tela [nome da tela].
2. Preencher os campos com [dados utilizados].
3. Executar a ação [clique/submissão].
4. Observar o comportamento ocorrido.

#### 🎯 Comportamento Esperado:
[Descrever o que a regra de negócio determina que deveria acontecer.]

#### ⚠️ Comportamento Obtido:
[Descrever detalhadamente a falha, erro em tela, exceção ou comportamento inconsistente.]

#### 🗄️ Validação no Banco de Dados (MySQL Workbench):
```sql
-- Query executada para checar a persistência ou inconsistência no banco
SELECT * FROM [tabela] WHERE [condicao];
```

#### 📷 Evidência(s):
* Print da tela: `evidencias/BUG-XXX_descricao.png`
* Vídeo gravado no Jam: `[Inserir link do Jam ou caminho do vídeo]`
```
