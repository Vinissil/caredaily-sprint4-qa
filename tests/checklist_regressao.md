# Checklist de Testes de Regressão - Care Daily (Sprint 4)

Este checklist contém a lista de cenários críticos que devem ser revalidados para garantir que as novas implementações da Sprint 4 não causaram impactos colaterais ou quebras em funcionalidades já consolidadas na Sprint 3.

---

## 🔑 1. Validação de Login
- [ ] Validar que logins pré-existentes de pacientes, nutricionistas e administradores continuam autenticando sem problemas.
- [ ] Confirmar que a expiração de sessão (logout) desativa o token e impede acesso futuro pelo botão "voltar".
- [ ] Verificar que tentativas de login com dados corrompidos ou senhas antigas são bloqueadas com avisos de erro.

---

## ✉️ 2. Validação de Convite
- [ ] Garantir que o envio de novos convites não cancela ou inutiliza tokens de convites enviados anteriormente que continuam válidos.
- [ ] Certificar-se de que a listagem de convites pendentes no banco/painel é mantida atualizada sem perda de histórico.

---

## 🔒 3. Validação de Senha
- [ ] Garantir que a alteração ou criação de senha nova invalida os tokens de redefinição antigos gerados para o mesmo usuário.
- [ ] Verificar se as regras de complexidade de senha continuam sendo exigidas tanto no onboarding quanto na alteração de perfil.

---

## 👔 4. Validação do Perfil Administrador
- [ ] Validar que o Administrador não sofreu regressões e continua visualizando as listagens de clínicas e profissionais cadastrados.
- [ ] Atentar se o Administrador não ganhou acesso indevido às tabelas restritas de prontuários com as alterações da Sprint 4.

---

## 🩺 5. Validação do Perfil Nutricionista
- [ ] Garantir que o nutricionista logado mantém o vínculo correto exclusivo com a sua clínica.
- [ ] Certificar que o profissional continua visualizando exclusivamente os pacientes sob seus cuidados.

---

## 👤 6. Validação do Perfil Paciente
- [ ] Validar que o paciente logado continua impedido de alterar qualquer parâmetro do sistema (RBAC restrito).
- [ ] Confirmar que o painel do paciente continua exibindo as porções corretas descritas pelo profissional.

---

## 🍎 7. Validação de Plano Alimentar
- [ ] Confirmar se a exibição do plano alimentar e calendário de refeições se mantém estável para o paciente.
- [ ] Validar que a adição ou edição de novos alimentos não altera porções de outros alimentos cadastrados na mesma refeição.

---

## 📈 8. Validação de Evolução
- [ ] Garantir que o cálculo do IMC histórico do paciente permanece íntegro e condizente com a evolução das medidas.
- [ ] Certificar que novos registros de peso e medidas não apagam ou corrompem os dados históricos anteriores.

---

## 🏆 9. Validação de Ranking
- [ ] Validar que a atualização de pontos do ranking não interfere na contagem acumulada de pontos históricos de outros pacientes.
- [ ] Verificar que o ranking de engajamento permanece isolado por clínica (um paciente da clínica A não aparece na lista da clínica B).

---

## 📅 10. Validação de Agenda
- [ ] Garantir que a marcação de novas consultas mantém na agenda os dados corretos de reuniões passadas para fins de auditoria.
- [ ] Validar que o cancelamento de uma consulta libera o respectivo slot de horário de forma imediata.

---

## ⚙️ 11. Validação de Perfil de Usuário
- [ ] Certificar que a edição de e-mail e telefone do usuário na tela de perfil atualiza as referências no banco e não quebra a integridade de login.
- [ ] Garantir que a foto de perfil seja renderizada corretamente em todas as telas em que é exibida.

---

## 🛡️ 12. Validação de Permissões (RBAC)
- [ ] Executar testes de injeção de URL em rotas sensíveis para assegurar que o bloqueio a usuários desautorizados (403 Forbidden) continua ativo.
- [ ] Garantir que dados de tráfego de API retornam erro ao tentar buscar dados sensíveis sem token portador válido.

---

## ⚖️ 13. Validação de LGPD e Privacidade
- [ ] Validar que usuários antigos com aceite de termos de consentimento registrado não são forçados a aceitar novamente os termos, a menos que haja alteração na política.
- [ ] Certificar de que dados de pacientes que revogaram o consentimento se mantêm completamente inacessíveis e anonimizados.
