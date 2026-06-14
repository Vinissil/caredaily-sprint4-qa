# Checklist de Validação Final - Care Daily (Sprint 4)

Este checklist consolida os itens técnicos e operacionais que devem ser testados e atestados pela equipe de Quality Assurance antes da homologação final do sistema.

---

## 🔑 1. Validação de Login
- [ ] Validar login com credenciais válidas do perfil Administrador.
- [ ] Validar login com credenciais válidas do perfil Nutricionista.
- [ ] Validar login com credenciais válidas do perfil Paciente.
- [ ] Validar comportamento ao tentar logar com credenciais inválidas (e-mail incorreto, senha incorreta).
- [ ] Testar encerramento de sessão (logout) e certificar que o usuário não consegue retornar à área logada pelo botão voltar do navegador.

---

## ✉️ 2. Validação de Convite
- [ ] Testar envio de convite de nutricionista por e-mail pelo perfil Administrador.
- [ ] Testar envio de convite de paciente por e-mail pelo perfil Nutricionista.
- [ ] Validar recebimento de e-mail e integridade do link enviado (deve conter token único de segurança).
- [ ] Testar tentativa de aceite de convite contendo link expirado ou token modificado.

---

## 🔒 3. Validação de Senha
- [ ] Validar redirecionamento automático ao clicar em aceitar convite para a página de criação de senha.
- [ ] Testar criação de senha atendendo a todos os critérios exigidos (maiúsculas, minúsculas, números, caracteres especiais, comprimento mínimo).
- [ ] Testar tentativa de criação de senha fraca, garantindo o bloqueio do sistema e exibição das diretrizes de segurança.

---

## 👔 4. Validação do Perfil Administrador
- [ ] Validar acesso administrativo exclusivo para gerenciamento de clínicas parceiras.
- [ ] Validar acesso administrativo exclusivo para listagem e vinculação de nutricionistas a clínicas.
- [ ] Testar se o Administrador é incapaz de acessar informações de planos alimentares particulares de pacientes sem autorização/log.

---

## 🩺 5. Validação do Perfil Nutricionista
- [ ] Validar que o nutricionista logado visualiza exclusivamente os pacientes vinculados a ele ou à sua clínica.
- [ ] Validar o cadastro de novos pacientes pelo nutricionista.
- [ ] Testar o bloqueio de acesso do nutricionista a registros de pacientes de clínicas terceiras.

---

## 👤 6. Validação do Perfil Paciente
- [ ] Validar acesso do paciente às suas informações diárias de dieta e agenda pelo painel.
- [ ] Garantir que o paciente não tenha acesso a botões, links ou APIs de criação ou edição de dietas.
- [ ] Validar a segurança de isolamento lateral para impedir que o paciente A acesse registros do paciente B.

---

## 🍎 7. Validação do Plano Alimentar
- [ ] Validar a criação do plano alimentar com divisões corretas das refeições diárias pelo nutricionista.
- [ ] Testar a adição de novos alimentos com suas respectivas gramaturas ao plano alimentar.
- [ ] Validar se as alterações efetuadas no plano pelo profissional refletem instantaneamente no painel do paciente.
- [ ] Testar validação de campos obrigatórios vazios na submissão de novos alimentos ou refeições.

---

## ❌ 8. Validação de Remoção de Alimento
- [ ] Testar a remoção (exclusão) de alimentos cadastrados em refeições pelo nutricionista.
- [ ] Confirmar que o alimento removido deixa de ser renderizado no painel e calendário do paciente.
- [ ] Validar que a remoção do alimento não gera registros fantasmas no banco de dados.

---

## 📈 9. Validação de Evolução
- [ ] Validar o lançamento de dados antropométricos (peso, altura) e o cálculo automático do IMC pelo nutricionista.
- [ ] Testar o bloqueio de dados inválidos (como pesos e alturas negativos).
- [ ] Validar a renderização correta de gráficos de evolução física no painel do paciente.

---

## 🏆 10. Validação de Ranking
- [ ] Validar exibição do ranking de engajamento da clínica para nutricionistas e pacientes.
- [ ] Testar a atualização automática da pontuação do ranking após o paciente registrar refeições diárias consumidas.
- [ ] Certificar que o ranking exibe apenas dados autorizados dos pacientes participantes (respeitando a anonimização de sobrenomes).

---

## 📅 11. Validação de Agenda
- [ ] Validar acesso à agenda do nutricionista e exibição de horários livres e ocupados.
- [ ] Testar agendamento de nova consulta vinculada a um paciente.
- [ ] Validar bloqueio de agendamento de consultas com datas retroativas ou inválidas.
- [ ] Validar detecção de conflitos ao tentar marcar duas consultas no mesmo horário para o mesmo profissional.

---

## ⚙️ 12. Validação do Perfil de Usuário
- [ ] Validar a visualização e edição de dados cadastrais (como foto e telefone) pelo próprio usuário em sua tela de perfil.
- [ ] Validar se dados modificados persistem no banco de dados e atualizam o painel de forma imediata.

---

## 📸 13. Validação de Evidências
- [ ] Confirmar se todas as evidências (prints de tela) descritas no plano foram geradas e salvas na pasta `/evidencias`.
- [ ] Validar que todos os prints gerados passaram por auditoria para garantir o mascaramento de CPFs, telefones e e-mails de homologação/reais.

---

## ⚖️ 14. Validação de LGPD e Privacidade
- [ ] Testar obrigatoriedade de aceite de termos de privacidade no primeiro acesso do usuário.
- [ ] Validar acesso facilitado aos termos de consentimento e políticas a partir do menu do usuário.
- [ ] Testar fluxo de revogação de consentimento de dados, garantindo a desativação da conta e anonimização de dados de saúde.
