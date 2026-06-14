# Casos de Teste Automatizados - Selenium IDE (Sprint 4)

Este documento apresenta o detalhamento dos 4 cenários de testes automatizados preparados para a validação da Sprint 4 do Care Daily usando o Selenium IDE.

---

## 🤖 Cenários de Teste Automatizados

### TA001 - Login com usuário válido
* **ID do Teste:** `TA001`
* **Nome do Teste:** Login com usuário válido (Nutricionista)
* **Objetivo:** Validar se o sistema permite o acesso de um nutricionista cadastrado usando credenciais corretas e redireciona ao painel clínico.
* **Dados de Entrada:**
  - URL Base: `http://localhost:3000` (ou URL de homologação correspondente)
  - E-mail: `nutri@caredaily.com`
  - Senha: `Nutri@1234`
* **Dados de Saída Esperada:** Sessão iniciada com sucesso e renderização da URL `/nutri/painel`.
* **Passos Automatizados:**
  1. `open` $\rightarrow$ `/login` (Abre a tela de login)
  2. `setWindowSize` $\rightarrow$ `1280x800` (Define a resolução da tela)
  3. `type` $\rightarrow$ `id=email` com valor `nutri@caredaily.com` (Insere o e-mail)
  4. `type` $\rightarrow$ `id=senha` com valor `Nutri@1234` (Insere a senha)
  5. `click` $\rightarrow$ `id=btn-entrar` (Clica no botão de submissão)
  6. `waitForElementVisible` $\rightarrow$ `id=painel-nutri` (Aguarda a carga do painel)
  7. `assertText` $\rightarrow$ `id=perfil-usuario` com valor `nutri@caredaily.com` (Valida o e-mail logado na interface)
* **Resultado Esperado:** Nutricionista autenticado e redirecionado para a tela principal de gestão de pacientes.
* **Evidência Esperada:** `video_execucao_ta001.mp4` ou print `print_ta001_sucesso.png`.

---

### TA002 - Login inválido
* **ID do Teste:** `TA002`
* **Nome do Teste:** Login inválido
* **Objetivo:** Validar se o sistema recusa a autenticação ao informar dados de e-mail e senha não cadastrados ou incorretos.
* **Dados de Entrada:**
  - E-mail: `invalido@caredaily.com`
  - Senha: `SenhaIncorreta123`
* **Dados de Saída Esperada:** Permanência na tela de login e exibição de alerta de erro.
* **Passos Automatizados:**
  1. `open` $\rightarrow$ `/login` (Abre a tela de login)
  2. `type` $\rightarrow$ `id=email` com valor `invalido@caredaily.com` (Insere o e-mail incorreto)
  3. `type` $\rightarrow$ `id=senha` com valor `SenhaIncorreta123` (Insere a senha incorreta)
  4. `click` $\rightarrow$ `id=btn-entrar` (Clica em entrar)
  5. `waitForElementVisible` $\rightarrow$ `class=mensagem-erro` (Aguarda a exibição da mensagem de erro)
  6. `assertText` $\rightarrow$ `class=mensagem-erro` com valor `Credenciais incorretas` (Valida a mensagem do alerta)
* **Resultado Esperado:** Acesso bloqueado, mensagem de erro exibida em tela e o usuário mantido no formulário de login.
* **Evidência Esperada:** `video_execucao_ta002.mp4` ou print `print_ta002_erro.png`.

---

### TA003 - Navegação até tela de plano alimentar
* **ID do Teste:** `TA003`
* **Nome do Teste:** Navegação até tela de plano alimentar (Paciente)
* **Objetivo:** Validar se um paciente logado consegue navegar pelas opções do painel e carregar a tela de visualização do plano alimentar.
* **Dados de Entrada:**
  - E-mail: `paciente@caredaily.com`
  - Senha: `Paciente@1234`
* **Dados de Saída Esperada:** Tela de plano alimentar exibida com sucesso na rota `/paciente/plano-alimentar`.
* **Passos Automatizados:**
  1. `open` $\rightarrow$ `/login` (Abre a página de login)
  2. `type` $\rightarrow$ `id=email` com valor `paciente@caredaily.com` (Insere e-mail de paciente)
  3. `type` $\rightarrow$ `id=senha` com valor `Paciente@1234` (Insere senha de paciente)
  4. `click` $\rightarrow$ `id=btn-entrar` (Clica em entrar)
  5. `waitForElementVisible` $\rightarrow$ `id=menu-dieta` (Aguarda o menu lateral do painel)
  6. `click` $\rightarrow$ `id=menu-dieta` (Clica na opção 'Plano Alimentar')
  7. `waitForElementPresent` $\rightarrow;` `id=refeicoes-container` (Aguarda o carregamento das refeições)
  8. `assertElementPresent` $\rightarrow` `id=refeicoes-container` (Confirma que os dados da dieta foram mostrados)
* **Resultado Esperado:** O paciente navega com sucesso até a tela do plano alimentar e visualiza a sua dieta sem erros.
* **Evidência Esperada:** `video_execucao_ta003.mp4` ou print `print_ta003_plano.png`.

---

### TA004 - Registro ou validação de alimento no plano alimentar
* **ID do Teste:** `TA004`
* **Nome do Teste:** Registro ou validação de alimento no plano alimentar
* **Objetivo:** Validar se o nutricionista consegue adicionar um alimento de teste a uma refeição (ex: Café da Manhã) no prontuário de um paciente.
* **Dados de Entrada:**
  - E-mail do nutricionista: `nutri@caredaily.com`
  - Senha: `Nutri@1234`
  - Paciente selecionado: `Vali`
  - Alimento: `Banana`
  - Quantidade: `1 unidade`
  - Calorias: `150`
* **Dados de Saída Esperada:** Inclusão e renderização do alimento na lista do café da manhã de Vali.
* **Passos Automatizados:**
  1. `open` $\rightarrow$ `/login` (Abre o login)
  2. `type` $\rightarrow$ `id=email` com valor `nutri@caredaily.com`
  3. `type` $\rightarrow$ `id=senha` com valor `Nutri@1234`
  4. `click` $\rightarrow$ `id=btn-entrar`
  5. `waitForElementVisible` $\rightarrow$ `id=busca-paciente`
  6. `type` $\rightarrow$ `id=busca-paciente` com valor `Vali` (Filtra por Vali)
  7. `click` $\rightarrow$ `id=btn-ver-paciente` (Acessa o prontuário de Vali)
  8. `click` $\rightarrow$ `id=aba-plano-alimentar` (Acessa a aba do plano)
  9. `click` $\rightarrow$ `id=btn-add-alimento` (Clica em Adicionar Alimento)
  10. `type` $\rightarrow$ `id=input-alimento` com valor `Banana`
  11. `type` $\rightarrow$ `id=input-quantidade` com valor `1 unidade`
  12. `type` $\rightarrow$ `id=input-calorias` com valor `150`
  13. `select` $\rightarrow$ `id=select-refeicao` com valor `label=Café da Manhã`
  14. `click` $\rightarrow$ `id=btn-salvar-alimento` (Confirma a inclusão)
  15. `waitForElementVisible` $\rightarrow$ `xpath=//td[contains(.,'Banana')]` (Aguarda exibição do alimento)
  16. `assertText` $\rightarrow$ `xpath=//td[contains(.,'Banana')]` com valor `Banana` (Valida o cadastro)
* **Resultado Esperado:** O alimento "Banana" é inserido com sucesso na refeição e exibido em tela de forma consistente.
* **Evidência Esperada:** `video_execucao_ta004.mp4` ou print `print_ta004_alimento_salvo.png`.
