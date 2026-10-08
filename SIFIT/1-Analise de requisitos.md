# 📦 Análise de Requisitos Funcionais — Sistema SIFIT (Academias)

Documento técnico de especificação dos Requisitos Funcionais (RF) e regras de negócio do sistema **SIFIT - Sistema para Academias** (desenvolvido pela Centrion Web). Serve como base para o planejamento e criação dos cenários de teste manuais.

---

### 🔐 RF01 - Autenticação e Controle de Sessão

**Descrição**: O sistema deve permitir que operadores, recepcionistas, instrutores e administradores acessem o painel da academia com suas credenciais de segurança.

* **Regras de Negócio e Comportamento**:
  * Autenticação via nome de usuário e senha.
  * Validação de campos obrigatórios no formulário de login.
  * Emissão de mensagem de aviso clara para credenciais inválidas (*"Usuário ou senha incorretos"*).
  * Controle de sessão ativa com encerramento seguro ao acionar logout.

---

### 📊 RF02 - Dashboard e Indicadores de Gestão

**Descrição**: Painel principal com visão analítica e indicadores chave da academia em tempo real.

* **Regras de Negócio e Comportamento**:
  * Exibição dos cards de indicadores: Alunos Ativos, Alunos Inativos, Matrículas Vencidas, Aniversariantes do Mês e Taxa de Retenção.
  * Alerta de "Alunos em Risco de Evasão" com base na frequência recente de check-ins.
  * Menu lateral dinâmico com navegação para todos os módulos operacionais.

---

### 👤 RF03 - Gestão de Alunos (Clientes)

**Descrição**: Formulário completo de cadastro, edição e consulta de alunos da academia.

* **Regras de Negócio e Comportamento**:
  * **Campos Obrigatórios**: Nome Completo, CPF (com validação de dígitos e máscara `000.000.000-00`), Data de Nascimento, Sexo, Telefone e E-mail.
  * **Campos Opcionais**: Endereço completo, Contato de Emergência, Foto de Perfil e Observações Médicas (Anamnese).
  * O sistema não deve permitir o cadastro de mais de um aluno com o mesmo número de CPF.
  * Listagem com filtros por Status (Ativo, Inativo, Bloqueado), Nome, CPF e Período de Cadastro.
  * Ao salvar o formulário, os dados devem ser persistidos na tabela `clientes` do banco de dados MySQL.

---

### 🏷️ RF04 - Cadastro de Planos e Modalidades

**Descrição**: Parametrização dos produtos e serviços comercializados pela academia.

* **Regras de Negócio e Comportamento**:
  * Definição do Nome do Plano (ex.: Musculação Mensal, Anual Fidelidade, Crossfit Livre).
  * Configuração de Valor Nominal (R$), Periodicidade (Mensal, Trimestral, Semestral, Anual), Taxa de Matrícula e Quantidade Máxima de Acessos por semana/mês.
  * Indicação se o plano permite renovação automática (recorrência no cartão).

---

### 📋 RF05 - Gerenciamento e Realização de Matrículas

**Descrição**: Formulário de associação entre o aluno e o plano escolhido, gerando os títulos financeiros correspondentes.

* **Regras de Negócio e Comportamento**:
  * Seleção do aluno previamente cadastrado.
  * Seleção do plano contratado e preenchimento da Data de Início.
  * Cálculo automático da Data de Término (Vigência) com base na periodicidade do plano.
  * Aplicação opcional de Desconto (Percentual ou Valor em R$).
  * Geração automática das parcelas a receber na tabela `contas_receber`.
  * Não permitir data de término anterior à data de início.

---

### 🏋️ RF06 - Fichas de Treino e Montagem de Exercícios

**Descrição**: Ferramenta para instrutores criarem rotinas de treinamento personalizadas para os alunos.

* **Regras de Negócio e Comportamento**:
  * Cadastro de Exercícios vinculados a Grupos Musculares (Peito, Costas, Quadríceps, Bíceps, Ombros, etc.).
  * Formulário de montagem de Ficha de Treino associando um aluno a divisões de treino (Treino A, B, C, D).
  * Campos por exercício: Nome do Exercício, Séries, Repetições, Carga (kg), Intervalo de Descanso (segundos) e Observações Técnicas.
  * Impressão ou visualização digital da ficha de treino ativa.

---

### 📏 RF07 - Avaliação Física e Antropometria

**Descrição**: Módulo para registro de parâmetros biométricos e composição corporal do aluno.

* **Regras de Negócio e Comportamento**:
  * **Dados Básicos**: Peso (kg), Estatura (cm), Pressão Arterial e Frequência Cardíaca de Repouso.
  * **Cálculo Automático de IMC**: $IMC = \frac{\text{peso}}{(\text{estatura})^2}$ com classificação (Abaixo do peso, Normal, Sobrepeso, Obesidade).
  * **Perimetria**: Circunferências corporais (Tórax, Cintura, Abdômen, Braços, Coxas, Panturrilhas).
  * **Composição Corporal**: Protocolos de dobras cutâneas (Jackson & Pollock 3 ou 7 dobras) com cálculo de percentual de gordura (%BF) e massa magra.

---

### 🚪 RF08 - Controle de Presença e Check-in

**Descrição**: Controle de fluxo de acesso físico e frequência dos alunos na academia.

* **Regras de Negócio e Comportamento**:
  * Registro de entrada por busca manual (Nome ou CPF) ou leitura de código/biometria.
  * Validação imediata da situação da matrícula:
    * Se Matrícula Ativa $\rightarrow$ Entrada autorizada e registro inserido na tabela `presencas`.
    * Se Matrícula Vencida ou Bloqueada por Inadimplência $\rightarrow$ Alerta visual impeditivo e bloqueio de acesso.

---

### 💰 RF09 - Contas a Receber e Baixa de Mensalidades

**Descrição**: Controle financeiro das mensalidades contratadas e fluxo de pagamentos.

* **Regras de Negócio e Comportamento**:
  * Listagem das faturas com filtros por Status (A Vencer, Pago, Vencido, Cancelado).
  * Ação de "Baixa Manual" de mensalidade com seleção da Forma de Pagamento (Dinheiro, PIX, Cartão Débito, Cartão Crédito).
  * Emissão de recibo de pagamento ao aluno.
  * Atualização imediata do status da parcela na tabela `contas_receber` e registro no caixa do dia.
