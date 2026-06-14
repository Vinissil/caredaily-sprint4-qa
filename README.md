# Care Daily - Plano Nutricional e Calendário

## 1. Nome do Projeto
**Care Daily** — Sistema de Gestão Nutricional, Calendário e Evolução Clínica.

---

## 2. Disciplina
**Testing, Compliance and Quality**

---

## 3. Sprint
**Sprint 4** — Validação Final, Qualidade e Automação de Testes.

---

## 4. Objetivo da Entrega
O objetivo desta entrega é apresentar a validação final da plataforma Care Daily através de duas frentes de Quality Assurance:
* **Parte A (Manual):** Estruturação do plano e dos 20 casos de testes manuais em nível de sistema integrados ao **Azure Boards** com dados de entrada e saída controlados.
* **Parte B (Automatizada):** Automação de 4 fluxos críticos da aplicação utilizando o **Selenium IDE**, acompanhado de guias de importação, execução e gravação de vídeo comprobatório.

Esta entrega consolida a qualidade do onboarding (convites e senhas), permissões RBAC, gestão clínica e a aderência completa do projeto às diretrizes de conformidade regulatória da LGPD.

---

## 5. Parte A — Testes Manuais no Azure Boards
A Parte A consiste na modelagem do plano de testes de sistema para execução manual. Foram mapeados **20 casos de teste manuais** contendo entradas de dados controladas e resultados esperados bem definidos. Os testes abrangem autenticação, fluxos de convites e criação de senhas de múltiplos perfis (Admin, Nutri, Paciente), prontuários, planos alimentares, evolução física, ranking de engajamento e a segurança de isolamento de dados pessoais.

---

## 6. Parte B — Testes Automatizados
A Parte B engloba a automação funcional dos fluxos essenciais utilizando o **Selenium IDE**. Foram desenvolvidos 4 testes automatizados cobrindo:
* `TA001` - Login com usuário válido (Nutricionista).
* `TA002` - Login inválido (tratamento de erro).
* `TA003` - Navegação até tela de plano alimentar (Paciente).
* `TA004` - Registro ou validação de alimento no plano alimentar (Nutricionista prescrevendo alimento).

---

## 7. Estrutura de Pastas
A entrega está estruturada no diretório conforme a árvore abaixo:
```text
CareDaily_Sprint4_QA_Entrega/
├── README.md                           # Este documento (Guia principal da Sprint 4)
├── ENTREGA_FINAL.md                    # Checklist de verificação antes do envio
├── azure_boards/                       # Casos de teste e plano no Azure Boards (Parte A)
│   ├── plano_testes_manuais_azure_boards.md # Detalhamento dos 20 testes manuais
│   ├── casos_de_teste_azure_boards.csv      # 20 testes manuais estruturados com dados controlados
│   └── instrucoes_cadastro_azure_boards.md   # Tutorial de cadastro no Azure Boards
├── automacao/                          # Automação de testes em navegador (Parte B)
│   ├── README_AUTOMACAO.md             # Guia de execução e gravação da automação
│   ├── casos_automatizados.md          # 4 casos de teste automatizados descritos
│   ├── selenium_ide_caredaily.side     # Projeto contendo a automação do Selenium IDE
│   └── evidencias_automacao/
│       └── README.md                   # Orientações sobre vídeos e prints de automação
├── docs/                               # Documentação estratégica de qualidade
│   ├── plano_validacao_final.md        # Planejamento geral das validações em Staging
│   ├── relatorio_execucao_testes.md    # Consolidação das métricas de testes (Pendentes)
│   ├── relatorio_bugs_e_correcoes.md   # Registro e ciclo de vida de defeitos
│   ├── matriz_riscos_atualizada.md     # Análise de riscos técnicos e de LGPD
│   ├── checklist_validacao_final.md    # Checklist antes da liberação (Go-Live)
│   ├── compliance_revisado.md          # Análise de conformidade legal e LGPD
│   └── parecer_final_qa.md             # Parecer técnico condicional sobre a release
├── tests/                              # Casos de teste e checklists gerais
│   ├── casos_de_teste_sprint4.csv      # Planilha com 43 casos de teste gerais de Staging
│   ├── resumo_execucao_testes.csv      # Quadro numérico de status dos testes
│   └── checklist_regressao.md          # Lista de verificação técnica da Sprint 3
└── evidencias/
    └── README.md                       # Diretrizes de organização das imagens de teste
```

---

## 8. Como Acessar os Testes Manuais
Os 20 testes manuais planejados podem ser consultados diretamente no arquivo [casos_de_teste_azure_boards.csv](azure_boards/casos_de_teste_azure_boards.csv) ou detalhados na forma de planejamento em [plano_testes_manuais_azure_boards.md](azure_boards/plano_testes_manuais_azure_boards.md). Eles servem de referência exata para o cadastro de itens de trabalho no Azure DevOps.

---

## 9. Como Cadastrar ou Visualizar os Testes no Azure Boards
O guia completo de importação e gerenciamento no Azure DevOps está contido no arquivo [instrucoes_cadastro_azure_boards.md](azure_boards/instrucoes_cadastro_azure_boards.md).
Resumo do procedimento:
1. Criar um projeto chamado `Care Daily` no Azure DevOps.
2. Criar um Board e adicionar os cartões (Work Items) do tipo **Task** ou **Test Case**.
3. Preencher o título, descrição/passos, dados de entrada e resultado esperado em cada item de acordo com a planilha de testes.
4. Conforme os testes forem executados, mover os cartões e atualizar o status (**State**) no board, anexando as capturas de tela correspondentes.

---

## 10. Como Executar os Testes Automatizados
O guia detalhado para execução da automação está descrito em [README_AUTOMACAO.md](automacao/README_AUTOMACAO.md).
Resumo do procedimento:
1. Instale a extensão **Selenium IDE** no Google Chrome, Microsoft Edge ou Mozilla Firefox.
2. Abra o Selenium IDE e importe o projeto [selenium_ide_caredaily.side](automacao/selenium_ide_caredaily.side).
3. Ajuste a URL padrão no campo "Playback Base URL" para apontar para o servidor em execução (ex: `http://localhost:3000`).
4. Selecione a Suite de Testes `CareDaily_Sprint4_TestSuite` e clique no botão **"Run all tests"** para iniciar a execução automática no navegador.

---

## 11. Evidências
As evidências devem ser organizadas nas seguintes pastas:
* **Evidências de Testes Manuais/Gerais:** Salvas em `/evidencias` conforme os nomes indicados na planilha.
* **Evidências de Automação (Gravação em Vídeo):** Salvas em `/automacao/evidencias_automacao` em formato `.mp4`.
* **⚠️ Importante (LGPD):** Todos os prints e gravações contendo dados de identificação pessoal (CPF, e-mail, telefone real) devem ser borrados ou tarjados antes de serem compartilhados ou commitados no repositório.

---

## 12. Links de Entrega

> [!IMPORTANT]
> **Orientações para o Aluno:**
> Antes de realizar a entrega definitiva ao professor, **todos os arquivos deste projeto devem ser enviados para um repositório público no GitHub na branch `develop`**. Preencha os campos abaixo com os links correspondentes após o envio.

* **Link do repositório GitHub:** https://github.com/Vinissil/caredaily-sprint4-qa/tree/develop
* **Branch utilizada:** develop
* **Link do Azure Boards:** https://dev.azure.com/caredaily-sprint4-qa/CareDaily%20Sprint%204%20QA/_workitems/recentlycreated/
* **Link do vídeo de automação:** A preencher

