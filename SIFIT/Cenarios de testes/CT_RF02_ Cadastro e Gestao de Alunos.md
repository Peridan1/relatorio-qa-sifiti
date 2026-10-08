# 🧪 Cenários de Testes — RF02: Cadastro e Gestão de Alunos (Clientes)

---

## 📋 Cenário 02: Formulário de Cadastro de Novo Aluno

### Caso de Teste 01: Inclusão Completa de Aluno com Dados Válidos (Caminho Feliz)

| Campo | Valor |
| :--- | :--- |
| **ID** | C02-CT01 |
| **Título** | Cadastro de novo aluno na academia e persistência no banco |
| **Módulo** | Clientes (`/clientes`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Positivo / Funcional |

* **Pré-condições**:
  1. Operador logado no sistema com perfil de atendimento/administrador.

* **Passos de Execução**:
  1. Acessar o menu lateral **Clientes** e clicar no botão **"+ Novo Aluno"**.
  2. Preencher os campos obrigatórios com dados válidos:
     * **Nome**: Nome de teste do aluno
     * **CPF**: CPF válido com máscara
     * **Data de Nascimento**: Data válida
     * **Sexo**: Selecionar opção
     * **Telefone / WhatsApp**: Número válido
     * **E-mail**: E-mail válido
  3. Clicar em **"Salvar"**.
  4. Abrir o **MySQL Workbench** e executar a query:
     ```sql
     SELECT * FROM clientes WHERE nome LIKE '%Nome_do_Aluno%';
     ```

* **Resultado Esperado (BDD / Gherkin)**:
  ```gherkin
  DADO que o operador está no formulário de cadastro de alunos do SIFIT
  QUANDO preencher todos os dados obrigatórios válidos
  E clicar no botão "Salvar"
  ENTÃO o sistema deve emitir mensagem de sucesso: "Cliente cadastrado com sucesso!"
  E redirecionar para a listagem de clientes exibindo o novo aluno
  E o registro deve constar persistido na tabela `clientes` do banco de dados
  ```

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print do formulário e do banco em evidencias/EXEC_CT02_cliente.png]`

---

### Caso de Teste 02: Validação de Campos Obrigatórios em Branco

| Campo | Valor |
| :--- | :--- |
| **ID** | C02-CT02 |
| **Título** | Tentativa de submissão do formulário com campos em branco |
| **Módulo** | Clientes (`/clientes`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Negativo / Validação |

* **Passos de Execução**:
  1. Acessar **Clientes > Novo Aluno**.
  2. Deixar os campos obrigatórios em branco.
  3. Clicar diretamente no botão **"Salvar"**.

* **Resultado Esperado (BDD / Gherkin)**:
  ```gherkin
  DADO que o operador tenta salvar o formulário de cliente sem preenchimento
  QUANDO acionar o botão "Salvar"
  ENTÃO o sistema não deve salvar o registro
  E deve destacar os campos obrigatórios com avisos de validação
  ```

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print da validação em evidencias/]`

---

### Caso de Teste 03: Validação do Algoritmo de CPF

| Campo | Valor |
| :--- | :--- |
| **ID** | C02-CT03 |
| **Título** | Tentativa de cadastro com CPF inválido |
| **Módulo** | Clientes (`/clientes`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Negativo / Integridade |

* **Passos de Execução**:
  1. Preencher os dados do aluno.
  2. No campo CPF, inserir sequência inválida (ex.: `111.111.111-11` ou `123.456.789-00`).
  3. Clicar em "Salvar".

* **Resultado Esperado**:
  O sistema deve aplicar o algoritmo de validação e recusar o cadastro, informando que o CPF é inválido.

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print em evidencias/]`
