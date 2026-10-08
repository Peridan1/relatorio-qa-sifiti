# 🧪 Plano de Testes — Sistema SIFIT (Academias)

---

### 📌 1. Identificação do Projeto

* **Sistema Avaliado**: SIFIT - Sistema para Academias (Centrion Web)
* **Ambiente de Testes Web**: Ambiente de homologação do SIFIT
* **Credenciais de Acesso**: Disponibilizadas institucionalmente em sala de aula (restritas a acadêmicos autorizados)
* **Ambiente de Banco de Dados**: Instância MySQL de homologação para auditoria via MySQL Workbench
* **Tipo de Teste**: Testes Manuais Funcionais, Validação de Formulários, Usabilidade e Integridade de Dados
* **Instituição**: UniALFA - Centro Universitário Alves Faria
* **Disciplina**: Extensão - Qualidade de Software (6º Período)
* **Docente**: Prof. Adnys Lougan da Silva
* **Data**: 2026-10-07

---

### 🎯 2. Objetivos do Plano de Testes

1. **Validação Funcional dos Formulários (Ciclo 01)**: Garantir que as validações de campos obrigatórios, máscaras e regras de negócio nos cadastros de autenticação, alunos e matrículas estejam funcionando conforme o esperado.
2. **Auditoria de Integridade Front-End $\rightarrow$ Banco de Dados**: Confirmar se os registros criados nos formulários web refletem com fidelidade nas respectivas tabelas do MySQL (`usuarios`, `clientes`, `matriculas`).
3. **Mapeamento de Falhas e Risco Operacional**: Detectar comportamentos anômalos que possam causar prejuízos à operação da academia (ex.: duplicação de requisições, cadastros de CPFs inconsistentes, vigência negativa de contratos).
4. **Geração de Evidências Claras**: Gravar o passo a passo com vídeos (extensão Jam) e capturas de tela para compor o portfólio acadêmico e técnico.

---

### 🧩 3. Escopo de Testes

#### ✅ Em Escopo — Ciclo 01 (Entrega Inicial):
* **Autenticação**: Fluxo de login e logout com credenciais válidas e inválidas, e teste de debounce no botão.
* **Módulo de Clientes**: Formulário de inclusão de alunos, validação de campos obrigatórios e integridade do CPF.
* **Módulo de Matrículas & Planos**: Vinculação de aluno a planos e validação de consistência entre data de início e término.

#### ⏳ Escopo Futuro (Próximos Ciclos em Planejamento):
* **Ciclo 02**: Fichas de Treino e Avaliações Físicas Antropométricas.
* **Ciclo 03**: Controle de Presença / Check-in e Módulo Financeiro (Contas a Receber).

#### ❌ Fora de Escopo (Excluído):
* Testes de carga e estresse de hardware/servidor em alta concorrência.
* Integração física com hardware de catraca eletrônica (validação realizada via interface de check-in web).
* Processamento real de cartão de crédito em gateway de pagamento bancário em produção.

---

### 🔧 4. Ferramentas & Ambiente de Suporte

* **Navegador Principal**: Google Chrome (versão estável mais recente).
* **Gravação de Evidências em Vídeo**: [Extensão Jam](https://chromewebstore.google.com/detail/jam/iohjgamcilhbgmhbnllfolmkmmekfmci) (indicada em aula pelo Prof. Adnys Lougan).
* **Validador de Banco de Dados**: MySQL Workbench conectado à instância MySQL de homologação.
* **Depuração Front-End**: Google Chrome DevTools (Console para capturar erros JS e Network para inspecionar requisições da API).

---

### 🧪 5. Técnicas de Teste Aplicadas

1. **Particionamento de Equivalência**: Divisão de dados em classes válidas (ex.: CPF com 11 dígitos válidos) e inválidas (letras no campo numérico, CPF com menos de 11 dígitos, CPF repetido).
2. **Análise de Valor Limite**: Teste de valores extremos em avaliações físicas (peso 0 kg, peso 350 kg; altura 50 cm, altura 250 cm) e datas de matrícula.
3. **Caminho Feliz (*Happy Path*)**: Execução fluida de cada formulário preenchendo todos os dados perfeitamente.
4. **Testes Negativos**: Submissão de formulários vazios, datas retroativas incompatíveis e caracteres especiais não sanitizados.
5. **Testes Exploratórios**: Navegação livre no SIFIT para detectar quebras de layout, botões sem ação e inconsistências de UX.

---

### 📄 6. Critérios de Aceitação e Saída

* **Critério de Entrada**: Acesso web ao SIFIT disponível, credenciais ativas de homologação e banco de dados acessível via Workbench.
* **Critério de Aceitação**: Todos os casos de teste planejados executados; ausência de falhas críticas impeditivas sem a respectiva notificação no relatório de bugs.
* **Critério de Saída**: Conclusão da matriz de testes com 100% dos cenários executados, bugs catalogados com evidências (prints e vídeos) e elaboração do relatório final.
