# Plano de Testes Manuais - Azure Boards (Sprint 4)

Este documento descreve o Plano de Testes Manuais no nível de sistema para a Sprint 4 do projeto **Care Daily**. Este planejamento visa validar a qualidade operacional, regras de negócio e limites da aplicação através do mapeamento de casos de teste estruturados no **Azure Boards**.

---

## 📋 Relação de Casos de Teste Planejados

Abaixo está o detalhamento individual de cada um dos 20 casos de teste manuais que compõem este ciclo de homologação:

### 1. Login do administrador
* **Teste Planejado:** Validar o acesso seguro de um perfil com privilégios de Administrador global.
* **Dados de Entrada:** 
  - E-mail: `admin@caredaily.com`
  - Senha: `Admin@1234`
* **Dados de Saída Esperados:** Sessão de administrador autorizada e redirecionamento de tela.
* **Procedimento / Passos do Teste:**
  1. Acessar a URL inicial do aplicativo Care Daily.
  2. Inserir `admin@caredaily.com` no campo de e-mail.
  3. Inserir `Admin@1234` no campo de senha.
  4. Clicar no botão "Entrar".
  5. Verificar se a tela exibe o menu "Clínicas" e "Nutricionistas".

---

### 2. Login do nutricionista
* **Teste Planejado:** Validar o acesso de um perfil profissional de nutrição vinculado a clínicas.
* **Dados de Entrada:** 
  - E-mail: `nutri@caredaily.com`
  - Senha: `Nutri@1234`
* **Dados de Saída Esperados:** Login efetuado com sucesso e token de sessão armazenado localmente.
* **Procedimento / Passos do Teste:**
  1. Acessar a página de login.
  2. Preencher o e-mail com `nutri@caredaily.com`.
  3. Preencher a senha com `Nutri@1234`.
  4. Clicar em "Entrar".
  5. Confirmar que a listagem de pacientes vinculados é carregada na tela inicial.

---

### 3. Login do paciente
* **Teste Planejado:** Validar o login de um usuário paciente para visualização do seu painel próprio.
* **Dados de Entrada:** 
  - E-mail: `paciente@caredaily.com`
  - Senha: `Paciente@1234`
* **Dados de Saída Esperados:** Painel inicial do paciente carregado na tela.
* **Procedimento / Passos do Teste:**
  1. Acessar a página de login.
  2. Informar o e-mail `paciente@caredaily.com`.
  3. Informar a senha `Paciente@1234`.
  4. Clicar em "Entrar".
  5. Verificar se os cartões de plano alimentar diário e próxima consulta são renderizados.

---

### 4. Login inválido
* **Teste Planejado:** Validar a recusa do sistema a tentativas de acesso com credenciais incorretas.
* **Dados de Entrada:** 
  - E-mail: `invalido@caredaily.com`
  - Senha: `SenhaIncorreta123`
* **Dados de Saída Esperados:** Sistema exibe alerta "Credenciais incorretas" e mantém o usuário na tela de login.
* **Procedimento / Passos do Teste:**
  1. Ir para a página de login.
  2. Preencher o e-mail com `invalido@caredaily.com`.
  3. Preencher a senha com `SenhaIncorreta123`.
  4. Pressionar o botão "Entrar".
  5. Verificar a exibição da mensagem de erro e certificar que a sessão não foi iniciada.

---

### 5. Convite de nutricionista
* **Teste Planejado:** Validar o fluxo de convite de novos profissionais pelo Administrador.
* **Dados de Entrada:** 
  - E-mail do Nutricionista: `novo.nutri@caredaily.com`
  - Clínica parceira: `Clínica Central`
* **Dados de Saída Esperados:** Registro de convite ativado no banco e mensagem de sucesso exibida.
* **Procedimento / Passos do Teste:**
  1. Logar com o perfil de Administrador.
  2. Clicar em "Nutricionistas" no menu lateral.
  3. Clicar no botão "Convidar Profissional".
  4. Inserir o e-mail `novo.nutri@caredaily.com` e selecionar a `Clínica Central` no seletor.
  5. Clicar em "Enviar Convite".

---

### 6. Aceite de convite por e-mail
* **Teste Planejado:** Validar a resposta do sistema ao link de convite recebido pelo profissional por e-mail.
* **Dados de Entrada:** 
  - URL de ativação contendo token criptografado seguro de ativação.
* **Dados de Saída Esperados:** Redirecionamento correto para a tela de definição de senha.
* **Procedimento / Passos do Teste:**
  1. Acessar o cliente de e-mail e abrir a mensagem recebida.
  2. Clicar no link de ativação contido na mensagem.
  3. Validar se a página aberta no navegador é a tela `/criar-senha`.

---

### 7. Criação de senha
* **Teste Planejado:** Validar a criação de senha inicial por um usuário convidado, aplicando critérios de segurança.
* **Dados de Entrada:** 
  - Nova Senha: `NovaSenha@2026`
  - Confirmação de Senha: `NovaSenha@2026`
* **Dados de Saída Esperados:** Registro de senha gravado no banco de dados e ativação da conta.
* **Procedimento / Passos do Teste:**
  1. Estando na tela de ativação de conta.
  2. Digitar a senha `NovaSenha@2026` nos campos de senha e confirmação.
  3. Clicar no botão de salvamento.
  4. Confirmar o aviso de conta ativada com sucesso.

---

### 8. Convite de paciente
* **Teste Planejado:** Validar o envio de convites de novos pacientes pelo nutricionista.
* **Dados de Entrada:** 
  - E-mail do paciente: `paciente.vali@caredaily.com`
* **Dados de Saída Esperados:** Geração de convite no banco e envio do e-mail de onboarding do paciente.
* **Procedimento / Passos do Teste:**
  1. Logar com o perfil do Nutricionista.
  2. Acessar o menu "Pacientes".
  3. Clicar no botão "Convidar Novo Paciente".
  4. Inserir o e-mail `paciente.vali@caredaily.com` e clicar em "Enviar".

---

### 9. Visualização de pacientes
* **Teste Planejado:** Validar o carregamento da listagem de pacientes no perfil do nutricionista.
* **Dados de Entrada:** 
  - Profissional autenticado: `nutri@caredaily.com`
* **Dados de Saída Esperados:** Tabela populada com pacientes vinculados a esse profissional.
* **Procedimento / Passos do Teste:**
  1. Logar como nutricionista.
  2. Clicar na aba "Pacientes" no menu lateral.
  3. Confirmar se a listagem exibe todos os pacientes vinculados ao profissional.

---

### 10. Agenda
* **Teste Planejado:** Validar a exibição da agenda de consultas do nutricionista.
* **Dados de Entrada:** 
  - Profissional autenticado: `nutri@caredaily.com`
  - Filtro de Data: `12/06/2026`
* **Dados de Saída Esperados:** Calendário exibindo slots e agendamentos existentes na data.
* **Procedimento / Passos do Teste:**
  1. Logar como nutricionista.
  2. Acessar o item de menu "Agenda".
  3. Selecionar a data `12/06/2026` no calendário e verificar a exibição de horários.

---

### 11. Perfil do administrador
* **Teste Planejado:** Validar a integridade da exibição do perfil do Administrador.
* **Dados de Entrada:** 
  - E-mail logado: `admin@caredaily.com`
* **Dados de Saída Esperados:** Exibição detalhada com nome, e-mail e cargo do administrador.
* **Procedimento / Passos do Teste:**
  1. Logar como Administrador.
  2. Acessar o menu do usuário no cabeçalho e clicar em "Meu Perfil".
  3. Validar se os dados mostrados correspondem à conta ativa.

---

### 12. Perfil do nutricionista
* **Teste Planejado:** Validar a integridade da exibição do perfil do Nutricionista.
* **Dados de Entrada:** 
  - E-mail logado: `nutri@caredaily.com`
* **Dados de Saída Esperados:** Exibição com especialidade do profissional e clínica de atuação.
* **Procedimento / Passos do Teste:**
  1. Logar como Nutricionista.
  2. Clicar no ícone de perfil no canto superior direito e escolher "Perfil".
  3. Confirmar a exatidão das informações cadastrais do profissional.

---

### 13. Perfil do paciente
* **Teste Planejado:** Validar a integridade da exibição do perfil do Paciente.
* **Dados de Entrada:** 
  - E-mail logado: `paciente@caredaily.com`
* **Dados de Saída Esperados:** Exibição de preferências alimentares e dados cadastrais básicos.
* **Procedimento / Passos do Teste:**
  1. Logar como Paciente.
  2. Clicar no menu lateral em "Meu Perfil".
  3. Verificar se as informações pessoais de contato aparecem corretas.

---

### 14. Plano alimentar
* **Teste Planejado:** Validar a criação e prescrição de um plano alimentar pelo profissional.
* **Dados de Entrada:** 
  - Paciente: `Vali`
  - Alimento: `Banana`
  - Quantidade: `1 unidade`
  - Calorias: `150`
  - Refeição: `Café da Manhã (08:00)`
* **Dados de Saída Esperados:** Alimento inserido na tabela do plano de Vali.
* **Procedimento / Passos do Teste:**
  1. Logar como Nutricionista e acessar o prontuário de `Vali`.
  2. Clicar na aba "Plano Alimentar".
  3. Clicar em "Adicionar Alimento".
  4. Informar `Banana` no campo Alimento, `1 unidade` em Quantidade e `150` em Calorias.
  5. Escolher `Café da Manhã` e clicar em salvar.

---

### 15. Edição de alimento
* **Teste Planejado:** Validar a alteração de um alimento no plano de um paciente.
* **Dados de Entrada:** 
  - Paciente: `Vali`
  - Alimento: `Banana`
  - Nova Quantidade: `2 unidades`
  - Novas Calorias: `300`
* **Dados de Saída Esperados:** Atualização instantânea da quantidade na dieta.
* **Procedimento / Passos do Teste:**
  1. Logar como Nutricionista e acessar o plano alimentar de `Vali`.
  2. Clicar no ícone de edição (lápis) ao lado de `Banana`.
  3. Alterar os campos para `2 unidades` e `300` calorias.
  4. Clicar em "Confirmar Edição".

---

### 16. Remoção de alimento
* **Teste Planejado:** Validar a remoção de um alimento da prescrição alimentar de um paciente.
* **Dados de Entrada:** 
  - Paciente: `Vali`
  - Alimento: `Banana`
* **Dados de Saída Esperados:** Deleção lógica ou física do registro e atualização da tela.
* **Procedimento / Passos do Teste:**
  1. Logar como Nutricionista e acessar o plano alimentar de `Vali`.
  2. Localizar o item `Banana` e clicar no ícone de exclusão (lixeira).
  3. Confirmar a caixa de diálogo de exclusão.
  4. Certificar-se de que o item desapareceu do plano alimentar.

---

### 17. Registro de refeição pelo paciente
* **Teste Planejado:** Validar a confirmação de consumo alimentar do dia pelo paciente (gamificação).
* **Dados de Entrada:** 
  - Refeição: `Café da Manhã` (Checklist de consumo)
* **Dados de Saída Esperados:** Status da refeição alterado para verde (consumido) e adição de pontos.
* **Procedimento / Passos do Teste:**
  1. Logar como Paciente e acessar o painel de dieta.
  2. Encontrar o item do Café da Manhã do dia.
  3. Marcar a caixa de seleção de consumo.
  4. Verificar se a cor do cartão mudou e se a pontuação geral aumentou.

---

### 18. Evolução do paciente
* **Teste Planejado:** Validar o registro de medições antropométricas do paciente pelo profissional.
* **Dados de Entrada:** 
  - Paciente: `Vali`
  - Peso: `75kg`
  - Altura: `1.80m`
  - Gordura: `15%`
* **Dados de Saída Esperados:** IMC calculado em `23.15` exposto em tela e registrado em gráficos.
* **Procedimento / Passos do Teste:**
  1. Logar como Nutricionista e abrir o prontuário de `Vali`.
  2. Ir para a aba "Evolução Corporal".
  3. Informar Peso `75`, Altura `1.80` e Gordura `15` nos campos respectivos.
  4. Clicar em "Salvar Evolução".

---

### 19. Ranking
* **Teste Planejado:** Validar a visualização do ranking de engajamento da clínica.
* **Dados de Entrada:** 
  - Perfil logado: `paciente@caredaily.com`
* **Dados de Saída Esperados:** Carregamento ordenado de pontuação dos pacientes vinculados.
* **Procedimento / Passos do Teste:**
  1. Logar como Paciente.
  2. Clicar na aba de menu "Ranking de Engajamento".
  3. Confirmar se a listagem exibe a pontuação de forma decrescente de acordo com o consumo das dietas.

---

### 20. Proteção de dados pessoais/LGPD
* **Teste Planejado:** Validar a proteção contra acessos externos a prontuários confidenciais (RBAC).
* **Dados de Entrada:** 
  - Login ativo: `paciente@caredaily.com` (Paciente A)
  - ID da rota restrita de prontuário do Paciente B (`Vali`): `/prontuario/1234`
* **Dados de Saída Esperados:** Bloqueio do servidor com código HTTP 403 Forbidden e desvio para página de acesso negado.
* **Procedimento / Passos do Teste:**
  1. Logar como Paciente A.
  2. Digitar diretamente na barra de URL do navegador a rota `/prontuario/1234`.
  3. Pressionar Enter.
  4. Verificar que o sistema bloqueia a exibição de dados e mostra mensagem de erro de permissão.
