# 🧪 Cenários de Testes — RF03: Matrículas e Planos

---

## 📋 Cenário 03: Contratação e Gestão de Matrículas

### Caso de Teste 01: Realização de Nova Matrícula para Aluno Ativo (Caminho Feliz)

| Campo | Valor |
| :--- | :--- |
| **ID** | C03-CT01 |
| **Título** | Matrícula de aluno em plano com geração de faturas |
| **Módulo** | Matrículas (`/matriculas`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Positivo / Funcional |

* **Pré-condições**:
  1. Aluno cadastrado no sistema.
  2. Plano ativo cadastrado (ex.: Mensal, Trimestral).

* **Passos de Execução**:
  1. Acessar o menu **Matrículas > Nova Matrícula**.
  2. Selecionar o Aluno.
  3. Selecionar o Plano desejado.
  4. Informar a Data de Início.
  5. Verificar se a Data de Término é calculada automaticamente.
  6. Selecionar a Forma de Pagamento inicial.
  7. Clicar em **"Confirmar Matrícula"**.

* **Resultado Esperado (BDD / Gherkin)**:
  ```gherkin
  DADO que um aluno ativo é selecionado no formulário de matrícula
  QUANDO vincular o plano e confirmar a operação
  ENTÃO a matrícula deve ser criada com status "Ativa"
  E o registro deve ser inserido na tabela `matriculas`
  E uma fatura correspondente deve ser gerada na tabela `contas_receber`
  ```

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print em evidencias/EXEC_CT03_matricula.png]`

---

### Caso de Teste 02: Validação de Coerência entre Data de Início e Término

| Campo | Valor |
| :--- | :--- |
| **ID** | C03-CT02 |
| **Título** | Tentativa de cadastro com data de término retroativa |
| **Módulo** | Matrículas (`/matriculas`) |
| **Prioridade** | Crítica |
| **Tipo de Teste** | Negativo / Validação |

* **Passos de Execução**:
  1. Acessar **Matrículas > Nova Matrícula**.
  2. Selecionar aluno e plano.
  3. No campo "Data de Término", selecionar uma data anterior à Data de Início.
  4. Clicar em "Confirmar Matrícula".

* **Resultado Esperado**:
  O sistema deve impedir a submissão e exibir alerta indicando que a data de término não pode ser anterior à data de início.

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print em evidencias/]`
