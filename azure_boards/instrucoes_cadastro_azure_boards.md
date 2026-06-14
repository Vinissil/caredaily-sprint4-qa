# Instruções para Cadastro de Testes no Azure Boards

Este guia descreve o procedimento passo a passo para cadastrar, organizar e registrar os testes manuais mapeados para a Sprint 4 do Care Daily no **Azure Boards**.

---

## 🚀 Passo a Passo para Configuração

### 1. Criar Projeto no Azure DevOps
1. Acesse sua conta no [Azure DevOps](https://dev.azure.com/).
2. Clique no botão **"New Project"** no canto superior direito da tela inicial.
3. Preencha as informações do projeto:
   - **Project Name:** `Care Daily`
   - **Description:** `Gerenciamento de QA, Compliance e Testes - Sprint 4`
   - **Visibility:** Escolha entre *Private* ou *Public* de acordo com as diretrizes da equipe.
4. Clique em **"Create"** para inicializar o repositório e as ferramentas de gerenciamento do projeto.

---

### 2. Criar Board
1. No menu lateral esquerdo do projeto recém-criado, navegue até a opção **Boards** $\rightarrow$ **Boards**.
2. O sistema criará automaticamente um Board padrão baseado no template do projeto (geralmente contendo colunas como *To Do*, *Doing* e *Done*).
3. Personalize as colunas se necessário para refletir a esteira de validação (ex: adicionar colunas para *A Testar*, *Em Homologação*, *Bugs Identificados*).

---

### 3. Criar Work Items do Tipo Task ou Test Case
1. No menu lateral esquerdo, vá para **Boards** $\rightarrow$ **Work Items**.
2. Clique no botão **"New Work Item"** e selecione a opção **Task** ou **Test Case** (caso a extensão Azure Test Plans esteja ativa no projeto).
3. *Nota:* Para times sem a licença do Azure Test Plans, recomenda-se criar Work Items do tipo **Task** (Tarefa) ou criar um tipo customizado para representar os casos de teste.

---

### 4. Cadastrar Título
1. No campo de título do Work Item, insira a identificação padronizada do caso de teste (ex: `CTB001 - Login do administrador` ou `CTB014 - Plano alimentar`).
2. Mantenha os títulos objetivos para facilitar a busca e indexação nas pesquisas do board.

---

### 5. Cadastrar Passos do Teste
1. No campo de descrição ou no bloco específico de **Steps** (caso esteja usando o tipo *Test Case*), detalhe o procedimento operacional de execução do teste.
2. Escreva em formato de lista ordenada numerada, indicando exatamente o que o analista deve fazer (ex: *"1. Acessar a tela de login; 2. Preencher e-mail (...)"*).

---

### 6. Cadastrar Dados de Entrada
1. No corpo do Work Item (ou em um campo customizado de dados), liste explicitamente as variáveis e valores predefinidos que o analista de testes usará na execução.
2. Exemplo: `E-mail: admin@caredaily.com | Senha: Admin@1234` ou `Paciente: Vali | Alimento: Banana`.

---

### 7. Cadastrar Resultado Esperado
1. No campo correspondente de **Expected Result** ou ao fim de cada passo, descreva a reação esperada do sistema.
2. Exemplo: *"Sistema autoriza o acesso e redireciona o usuário para a rota /admin/painel."*

---

### 8. Anexar Evidências de Teste
1. Quando os testes forem executados fisicamente no ambiente de Staging, gere o print da tela do resultado.
2. Certifique-se de que os dados pessoais sensíveis foram mascarados de acordo com a LGPD.
3. No Work Item correspondente, clique na aba **Attachments** (Anexos) e selecione o print de tela do seu dispositivo (ex: anexar `print_login_sprint4.png`).

---

### 9. Marcar Status de Execução
1. Atualize a coluna do Board ou o campo **State** (Estado) do Work Item para refletir a situação real do teste:
   - **To Do / Proposed:** Caso o teste ainda não tenha sido iniciado (equivalente a *Pendente*).
   - **Doing / In Progress:** Se a validação estiver sendo executada ou houver bug sob análise.
   - **Done / Completed:** Caso o teste tenha passado com sucesso e as evidências tenham sido anexadas.
   - **Resolved:** Usado para quando um bug associado à tarefa foi corrigido e aguarda reteste.
2. Salve e feche o item de trabalho.
