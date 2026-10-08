# 🧪 Cenários de Testes — RF01: Autenticação na Plataforma SIFIT

---

## 📋 Cenário 01: Login no Sistema SIFIT (Academias)

### Caso de Teste 01: Login com Credenciais Válidas (Caminho Feliz)

| Campo | Valor |
| :--- | :--- |
| **ID** | C01-CT01 |
| **Título** | Autenticação bem-sucedida do operador/administrador da academia |
| **Módulo** | RF01 - Autenticação (`/login`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Positivo / Funcional |

* **Pré-condições**:
  1. O usuário de homologação deve estar ativo na base de dados.
  2. Acesso à tela de login do sistema SIFIT.

* **Passos de Execução**:
  1. Acessar a tela inicial de login do SIFIT.
  2. No campo "Usuário", digitar as credenciais válidas de homologação.
  3. No campo "Senha", digitar a senha válida correspondente.
  4. Clicar no botão **"Entrar"**.

* **Resultado Esperado (BDD / Gherkin)**:
  ```gherkin
  DADO que o operador está na tela de login do SIFIT
  QUANDO informar usuário válido e senha correspondente
  E clicar no botão "Entrar"
  ENTÃO o sistema deve autenticar o usuário com sucesso
  E redirecionar para a tela inicial do Dashboard (/dashboard)
  E exibir os indicadores gerais da academia (Alunos ativos, aniversariantes, etc.)
  ```

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print em evidencias/EXEC_CT01_login.png ou link do Jam]`

---

### Caso de Teste 02: Tentativa de Login com Senha Incorreta

| Campo | Valor |
| :--- | :--- |
| **ID** | C01-CT02 |
| **Título** | Validação de credenciais inválidas no formulário de login |
| **Módulo** | RF01 - Autenticação (`/login`) |
| **Prioridade** | Alta |
| **Tipo de Teste** | Negativo / Segurança |

* **Passos de Execução**:
  1. Acessar a tela de login.
  2. Digitar um usuário válido.
  3. Digitar uma senha deliberadamente incorreta.
  4. Clicar em "Entrar".

* **Resultado Esperado (BDD / Gherkin)**:
  ```gherkin
  DADO que o operador preenche um usuário válido e uma senha incorreta
  QUANDO clicar no botão "Entrar"
  ENTÃO o sistema não deve permitir o acesso
  E deve exibir notificação de erro: "Usuário ou senha inválidos"
  E manter o operador na página de login
  ```

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print em evidencias/EXEC_CT02_login_invalido.png]`

---

### Caso de Teste 03: Prevenção de Duplo Clique no Formulário de Login

| Campo | Valor |
| :--- | :--- |
| **ID** | C01-CT03 |
| **Título** | Desativação do botão durante processamento da requisição |
| **Módulo** | RF01 - Autenticação (`/login`) |
| **Prioridade** | Média |
| **Tipo de Teste** | Negativo / Resiliência |

* **Passos de Execução**:
  1. Preencher credenciais de teste.
  2. Clicar repetidamente no botão "Entrar" várias vezes de forma rápida.

* **Resultado Esperado**:
  O botão deve ser desabilitado após o 1º clique (`disabled`), impedindo múltiplos envios de requisição à API.

* **Status da Execução**: ⏳ *[Aguardando Execução]* ( ) Passou  ( ) Falhou
* **Evidência**: `[A preencher: salvar print/vídeo em evidencias/]`
