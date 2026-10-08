# 🏋️‍♂️ Qualidade de Software & Testes Manuais — Sistema SIFIT

[![Status](https://img.shields.io/badge/Status-Ciclo%2001%20(Em%20Evolu%C3%A7%C3%A3o)-yellow.svg)](#)
[![QA](https://img.shields.io/badge/QA-Manual%20Testing-blue.svg)](#)
[![Sistema](https://img.shields.io/badge/Sistema-SIFIT%20Academias-orange.svg)](#)
[![Doc](https://img.shields.io/badge/Doc-Markdown-lightgrey.svg)](#)
[![UniALFA](https://img.shields.io/badge/UniALFA-Extensão%20Curricular-green.svg)](#)

Repositório dedicado ao estudo, planejamento, especificação de cenários (BDD/Gherkin), execução de testes manuais e documentação de defeitos (Bugs) no sistema **SIFIT - Sistema para Academias** (Centrion Web).

Este projeto compõe as entregas práticas e evolutivas da disciplina de **Extensão - Qualidade de Software** (6º período de Sistemas para Internet / Ciência da Computação - UniALFA), sob orientação do **Prof. Adnys Lougan da Silva**.

---

## 🎯 Objetivo do Projeto

1. **Garantia da Qualidade Funcional (QA)**: Mapear, validar e auditar os principais fluxos operacionais e formulários do sistema SIFIT.
2. **Rastreabilidade Ponta a Ponta (Front-end $\leftrightarrow$ Banco de Dados)**: Validar se as regras de negócio disparadas nos formulários web refletem com integridade no banco de dados relacional (MySQL).
3. **Evolução Contínua**: O projeto está sendo construído e versionado em ciclos incrementais de testes, permitindo o acompanhamento docente da evolução da cobertura de QA.

---

## 🏢 Sobre o Sistema Avaliado: SIFIT

O **SIFIT** é uma plataforma web completa voltada para a gestão integrada de academias, boxes de crossfit e estúdios fitness.

### Ciclo Atual de Avaliação (Ciclo 01):
* **Autenticação & Controle de Acesso**: Validação de formulário de login, integridade de credenciais e segurança de sessão.
* **Cadastro e Gestão de Alunos (Clientes)**: Formulário cadastral completo (dados pessoais, validação de CPF, dados de contato e persistência).
* **Gestão de Matrículas e Planos**: Contratação de planos, cálculo de datas de vigência e associação de alunos.

> *Nota: Os módulos complementares (Fichas de Treino, Avaliações Físicas, Check-in na Catraca e Módulo Financeiro) serão adicionados nos próximos ciclos de entrega conforme cronograma da disciplina.*

---

## 🔒 Ambiente de Testes & Segurança

* **Ambiente Web**: Sistema SIFIT (ambiente acadêmico de homologação).
* **Ambiente de Banco de Dados**: Instância de banco MySQL para auditoria direta via MySQL Workbench.
* **Segurança da Informação**: Em conformidade com boas práticas de segurança para repositórios públicos, **credenciais de acesso, logins de homologação e senhas de banco de dados não são versionados neste repositório**. O acesso é restrito aos acadêmicos autorizados através das diretrizes institucionais da UniALFA.

---

## 🧱 Estrutura do Repositório

O repositório reproduz e adapta a arquitetura do modelo de documentação do professor ([Adnyslougansilva/extensao-qa](https://github.com/Adnyslougansilva/extensao-qa)):

```text
relatorio-qa/
├── README.md                                         # Documento principal do projeto
├── .gitignore                                        # Arquivos ignorados pelo controle de versão
└── SIFIT/                                            # Documentação do sistema SIFIT
    ├── 1-Analise de requisitos.md                    # Mapeamento dos requisitos funcionais e regras
    ├── 2-plano de testes.md                          # Escopo, metodologia, ferramentas e critérios
    ├── 3-Relatorio-de-Bugs.md                        # Registro detalhado das falhas identificadas no ciclo
    ├── 4- Relatorio dos testes.md                    # Relatório executivo com métricas e cobertura
    ├── Cenarios de testes/                           # Casos de teste especificados em BDD / Gherkin
    │   ├── CT_RF01_ Login na plataforma.md          # Testes de autenticação
    │   ├── CT_RF02_ Cadastro e Gestao de Alunos.md  # Testes de formulário de clientes
    │   └── CT_RF03_ Gerenciamento de Matriculas e Planos.md # Testes de matrícula e planos
    └── evidencias/                                   # Diretório para evidências de teste
        └── README.md
```

---

## 🧪 Metodologias & Técnicas de Teste

| Aspecto | Detalhes |
| :--- | :--- |
| **Tipos de Teste** | Testes Manuais Funcionais, Teste de Integração (Web $\leftrightarrow$ DB), Usabilidade e Regressão |
| **Técnicas de Caixa-Preta** | Particionamento de Equivalência, Análise de Valor Limite, Caminho Feliz (*Happy Path*) e Testes Negativos |
| **Linguagem de Especificação** | BDD / Gherkin (`DADO`, `QUANDO`, `ENTÃO`), Tabelas de Decisão e Checklists |
| **Ferramentas de Suporte** | Google Chrome DevTools, MySQL Workbench, [Extensão Jam](https://chromewebstore.google.com/detail/jam/iohjgamcilhbgmhbnllfolmkmmekfmci) (gravação de evidências) |
| **Classificação de Bugs** | Severidade (*Crítica, Alta, Média, Baixa*) e Prioridade (*Alta, Média, Baixa*) |

---

## 📊 Matriz de Rastreabilidade — Ciclo Inicial (3 Testes)

| Requisito | Funcionalidade SIFIT | Tabela(s) no Banco | Casos de Teste | Status de Execução | Defeitos |
| :---: | :--- | :---: | :---: | :---: | :---: |
| **RF01** | Autenticação & Sessão | `usuarios` | `CT_RF01` | ⏳ Especificado (Aguardando Execução) | *A registrar* |
| **RF02** | Cadastro de Alunos (Clientes) | `clientes` | `CT_RF02` | ⏳ Especificado (Aguardando Execução) | *A registrar* |
| **RF03** | Matrículas e Planos | `matriculas`, `planos` | `CT_RF03` | ⏳ Especificado (Aguardando Execução) | *A registrar* |

---

## 📌 Cronograma de Evolução do Projeto

- [ ] **Ciclo 01 (Atual)**:
  - [x] Estrutura base do repositório
  - [x] Plano de Testes inicial
  - [x] Especificação de CT_RF01 (Autenticação)
  - [x] Especificação de CT_RF02 (Cadastro de Alunos)
  - [x] Especificação de CT_RF03 (Matrículas e Planos)
  - [ ] Execução prática dos testes no SIFIT e coleta de evidências
  - [ ] Registro de bugs encontrados (se houver)
  - [ ] Preenchimento do Relatório de Execução do Ciclo 01
- [ ] **Ciclo 02 (Próxima Entrega)**:
  - [ ] CT_RF04: Fichas de Treino e Exercícios
  - [ ] CT_RF05: Avaliação Física e Antropometria
- [ ] **Ciclo 03 (Entrega Final)**:
  - [ ] CT_RF06: Controle de Presença e Check-in
  - [ ] CT_RF07: Módulo Financeiro e Baixa de Mensalidades
  - [ ] Relatório Consolidado Final de QA

---

## 👨‍💻 Autor & Informações Acadêmicas

* **Instituição**: UniALFA - Centro Universitário Alves Faria
* **Curso**: Sistemas para Internet / Ciência da Computação (6º Período)
* **Disciplina**: Extensão - Qualidade de Software
* **Docente**: Prof. Adnys Lougan da Silva
