# Compliance e LGPD Revisado - Care Daily (Sprint 4)

Este documento detalha as diretrizes de compliance regulatório e conformidade com a Lei Geral de Proteção de Dados (LGPD - Lei nº 13.709/2018) aplicadas à Sprint 4 do Care Daily, fornecendo orientações práticas sobre o tratamento de informações e a proteção de dados na geração de relatórios de QA.

---

## 1. Dados Tratados
Durante a operação dos novos fluxos e cadastros da Sprint 4, a plataforma gerencia dados pessoais de diferentes perfis. Esses dados são divididos em:
- **Dados Cadastrais Comuns:** Nome completo, e-mail (usado para envio de convites e login), número de telefone móvel e CPF (chave primária de identificação).
- **Dados Organizacionais:** Razão social da clínica, CNPJ, dados de endereçamento físico e vínculos comerciais entre clínicas e profissionais de nutrição.

---

## 2. Dados Sensíveis
Em conformidade com a definição legal do Art. 5º, II da LGPD, o Care Daily realiza o tratamento de **dados pessoais sensíveis relacionados à saúde**:
- Histórico antropométrico do paciente (peso, altura, percentual de gordura, dobras cutâneas e IMC calculado).
- Prescrição nutricional (plano alimentar, horários de refeição, quantidade em gramas e restrições alimentares específicas).
- Histórico clínico e observações de evolução registradas no prontuário eletrônico pelo profissional.
- Logs de adesão ao plano alimentar (registro de refeições marcadas como consumidas).

---

## 3. Controle de Acesso por Perfil (RBAC)
Para assegurar que dados de saúde só fiquem acessíveis a pessoas de direito, a aplicação estabelece barreiras rígidas de acesso baseado em papéis:
- **Administrador:** Acesso exclusivo a dados corporativos de clínicas e cadastro de profissionais. O Administrador não possui permissão para ler prontuários, planos alimentares ou históricos de evolução de pacientes.
- **Nutricionista:** Permissão para criar, editar e excluir planos alimentares e evoluções de pacientes sob seus cuidados. É vetado o acesso a pacientes vinculados a outros nutricionistas ou clínicas diferentes.
- **Paciente:** Acesso em nível de leitura para sua própria dieta, agenda e evolução. O paciente é incapaz de alterar registros médicos ou visualizar dados de outros pacientes da clínica.

---

## 4. Minimização de Dados
Seguindo o princípio da necessidade (Art. 6º, III da LGPD), o Care Daily limita a coleta de dados de saúde ao mínimo estritamente necessário para prestar o serviço de acompanhamento nutricional. Campos que não tenham relação direta com a elaboração de dietas ou monitoramento físico (como dados bancários, religião ou posicionamento político) não são coletados pelo sistema.

---

## 5. Cuidados com Evidências
As capturas de tela geradas durante o processo de testes e salvas na pasta `evidencias/` constituem material de auditoria técnica. Contudo, imagens não mascaradas contendo dados reais ou rastreáveis criam riscos de não conformidade legal. As evidências devem retratar os fluxos funcionais do Care Daily sem comprometer a confidencialidade de testadores ou usuários fictícios que possuam semelhança com dados reais.

---

## 6. Necessidade de Mascarar CPF, Telefone e E-mail
É **obrigatório** mascarar, tarjar ou desfocar todas as informações pessoais identificáveis de qualquer print de tela antes do envio final.
- **CPF:** Ocultar completamente os dígitos ou aplicar formato fictício (ex: `***.***.***-**`).
- **Telefone:** Tarjar os dígitos centrais do telefone (ex: `(11) 9****-1234`).
- **E-mail:** Borrar o endereço de e-mail utilizado nos fluxos de login ou onboarding (ex: `u***o@dominio.com`).

*Recomendação:* Sempre que possível, utilize dados puramente fictícios de teste na origem (como CPF `000.000.000-00` e nomes genéricos) para mitigar a necessidade de edição de imagem posterior.

---

## 7. Auditoria de Alterações
O sistema implementa logs de auditoria automáticos para registrar ações críticas de gravação ou exclusão na base de dados (especialmente adição, edição e remoção de alimentos, e agendamento de consultas). Cada registro de auditoria registra de forma imutável:
1. O ID do usuário que efetuou a alteração.
2. A data e hora exatas da ação (formato UTC/ISO 8601).
3. O tipo de alteração (ex: *Exclusão de Alimento*).
4. Os dados anteriores e posteriores para rastreabilidade.

---

## 8. Recomendações Finais
1. **Revisão Periódica de Acessos:** Recomenda-se realizar auditorias nos tokens de acesso (JWT) expirados para garantir o tempo de expiração seguro.
2. **Anonimização pós-revogação:** Ao testar a revogação de consentimento do paciente, assegure que o sistema execute a inativação imediata da conta e aplique a anonimização irreversível dos dados históricos de saúde, deixando de vincular o CPF do paciente aos seus registros antropométricos.
3. **Auditoria de Imagens:** Realizar um double-check visual na pasta `evidencias/` antes da compactação e entrega do repositório de QA da Sprint 4.
