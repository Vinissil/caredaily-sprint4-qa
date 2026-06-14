# Plano de Validação Final - Care Daily (Sprint 4)

## 1. Objetivo da Validação Final
O objetivo principal deste plano é estabelecer a estratégia, metodologia e critérios para a homologação final da **Sprint 4** do sistema Care Daily. A validação final visa garantir que todos os fluxos críticos de negócio, as regras de controle de acesso (RBAC), a segurança da informação e a privacidade de dados (em conformidade com a LGPD) funcionem de maneira correta e integrada em ambiente de homologação (Staging), sem acarretar impactos negativos nas funcionalidades herdadas das sprints anteriores.

---

## 2. Escopo da Sprint 4
O escopo de desenvolvimento e validação da Sprint 4 abrange:
- **Fluxos de Onboarding:** Cadastro e ativação de contas a partir de links seguros enviados por e-mail, criação e complexidade de senhas para novos perfis.
- **Mapeamento de Perfis (RBAC):** Restrições e ações autorizadas para Administradores, Nutricionistas e Pacientes.
- **Gestão Operacional:** Gerenciamento de clínicas, nutricionistas e cadastro de pacientes.
- **Funcionalidades Clínicas Avançadas:** Agendamento de consultas com prevenção de conflitos, evolução antropométrica do paciente e gráficos históricos.
- **Prescrição Nutricional Dinâmica:** Atualização do plano alimentar em tempo real com adição, edição e remoção de alimentos.
- **Engajamento e Gamificação:** Registro de refeições consumidas e ranking geral de pacientes da clínica.
- **Logs de Auditoria e LGPD:** Rastreabilidade de alterações cadastrais e de dados de saúde, gestão de consentimento de uso de dados e conformidade legal.

---

## 3. Relação com a Sprint 3
A Sprint 3 foi o marco inicial de qualidade do Care Daily, estabelecendo a base da estrutura do plano nutricional (dietas divididas por refeições) e a visualização simples de consultas e calendário pelo paciente. A **Sprint 4 estende este escopo**, transformando as interações estáticas em processos dinâmicos. A criação de dietas agora é editável em tempo real (adição, edição e remoção de itens) pelo nutricionista, as consultas são geridas por uma agenda com validação de horários, e a segurança foi elevada com a inclusão de um fluxo de onboarding estruturado por e-mail e termos de consentimento da LGPD. Além disso, a Sprint 4 valida a não regressão dos fluxos da Sprint 3.

---

## 4. Funcionalidades Avaliadas
As seguintes funcionalidades são formalmente homologadas neste ciclo de testes:
* Login seguro de Administrador, Nutricionista e Paciente.
* Fluxo de convite enviado por e-mail para nutricionistas e pacientes.
* Aceite de convite e ativação de conta.
* Criação de senha inicial segura.
* Gestão e visualização de clínicas e nutricionistas no painel do Administrador.
* Agenda clínica com visualização de horários e agendamento de consultas.
* Criação, edição e remoção de alimentos no plano alimentar do paciente.
* Registro de refeição consumida pelo paciente.
* Lançamento de evolução física e geração de gráficos antropométricos.
* Cálculo e exibição do ranking de engajamento dos pacientes da clínica.
* Edição e visualização do perfil pessoal de usuário.
* Restrição de segurança RBAC e proteção a dados sensíveis de saúde.
* Auditoria interna por meio do histórico de logs do sistema.
* Termos de consentimento e revogação de dados (LGPD).

---

## 5. Estratégia de Testes
A validação de QA será baseada nas seguintes abordagens em ambiente de homologação (Staging):
1. **Testes Funcionais Manuais:** Execução passo a passo dos fluxos descritos na planilha de casos de teste, validando o comportamento das interfaces web e móveis.
2. **Testes Baseados em Perfis (RBAC):** Validação técnica das restrições de cada perfil, tentando forçar requisições a rotas de APIs não autorizadas.
3. **Testes de Validação e Limites (Negativos):** Inserção de dados nulos, formatos inválidos, valores negativos e datas no passado para certificar que o sistema impede a gravação e apresenta mensagens de erro instrutivas.
4. **Testes de Regressão:** Execução de checklist específico sobre a visualização e segurança do plano alimentar da Sprint 3.
5. **Auditoria de Logs:** Consulta manual à tabela de logs do banco de dados após ações de escrita e exclusão de alimentos.

---

## 6. Critérios de Aprovação
O sistema Care Daily será considerado **Aprovado** para liberação comercial quando:
- **100% dos testes planejados** tiverem sido executados em homologação.
- **Nenhum bug Crítico ou Alto** estiver aberto sem correção e reteste favorável.
- A taxa de sucesso dos testes executados for igual ou superior a **95%**.
- O checklist de regressão for concluído sem nenhuma falha operacional identificada.
- Todas as evidências (prints de tela) estiverem presentes na pasta `evidencias/` com os dados pessoais **completamente mascarados**.

---

## 7. Critérios de Reprovação
O sistema será considerado **Reprovado** e a liberação para produção suspensa se:
- Qualquer bug de severidade **Crítica** ou **Alta** for identificado e permanecer aberto (ex: falhas de login, vazamento de dados de outro paciente, exclusão de alimentos que quebre a visualização do plano).
- Qualquer print de evidência contiver dados pessoais reais expostos (CPF, e-mail ou telefone reais do analista de QA ou usuário), forçando a exclusão do repositório por violação da LGPD.
- A taxa de execução de testes for inferior a 100% ou a taxa de sucesso geral for inferior a 95%.

---

## 8. Evidências Obrigatórias
A homologação exige o upload das seguintes capturas de tela, com nomenclatura estrita e dados confidenciais mascarados:
1. `print_01_login_admin.png` — Login efetuado pelo Administrador.
2. `print_02_login_nutri.png` — Login efetuado pelo Nutricionista.
3. `print_03_login_paciente.png` — Login efetuado pelo Paciente.
4. `print_10_convite_nutri_email.png` — Confirmação de envio do convite pelo admin.
5. `print_12_criacao_senha_apos_convite.png` — Criação de nova senha pelo profissional convidado.
6. `print_15_nutri_convidando_paciente.png` — Envio de convite de paciente pelo nutricionista.
7. `print_18_paciente_criando_senha.png` — Criação de senha inicial pelo paciente.
8. `print_21_nutri_adicionando_alimento.png` — Alimento incluído no plano pelo profissional.
9. `print_22_nutri_editando_alimento.png` — Porção alterada no plano alimentar.
10. `print_23_nutri_removendo_alimento.png` — Alimento removido com sucesso.
11. `print_25_paciente_registrando_refeicao.png` — Registro de refeição consumida.
12. `print_26_paciente_visualizando_evolucao.png` — Tela de gráficos de evolução do paciente.
13. `print_31_ranking_atualizando_pontuacao.png` — Ranking atualizado.
14. `print_32_agenda_exibindo_horarios.png` — Slots de horários livres e ocupados na agenda.
15. `print_36_dados_mascarados_evidencia.png` — Tela de perfil com CPF, e-mail e telefone mascarados.
16. `print_37_auditoria_historico.png` — Log de alteração persistido no banco ou painel.

---

## 9. Riscos Residuais
* **Problemas de entrega de e-mails em produção:** Embora o disparo de convites funcione em homologação, restrições de servidores de e-mail e caixas de spam em produção podem atrasar o onboarding de usuários.
* **Instabilidade de gráficos móveis:** Gráficos antropométricos de evolução podem apresentar pequenos desvios de renderização em telas móveis muito pequenas (abaixo de 320px).
* **Desempenho da fila de auditoria:** O acúmulo massivo de logs de alteração e registros de refeição pode impactar a latência do banco de dados a longo prazo se não houver particionamento de logs.
