# Relatório de Bugs e Correções - Care Daily (Sprint 4)

## 1. Objetivo
O objetivo deste documento é fornecer uma estrutura formal para registrar, acompanhar e detalhar a resolução de todos os bugs e defeitos identificados durante a execução dos testes da Sprint 4 do Care Daily. A finalidade é assegurar que toda inconformidade seja tratada, corrigida e retestada antes do envio para o ambiente produtivo.

---

## 2. Classificação de Severidade
Os bugs identificados são classificados em quatro níveis de gravidade para priorização de correção pela equipe de desenvolvimento:

* **Crítica (Bloqueador):** Falhas que causam interrupção total do sistema (crash), corrupção de dados ou violações graves de segurança e controle de acesso (ex: paciente conseguindo visualizar dados de outro paciente). Bloqueia a liberação imediata.
* **Alta:** Falha em funcionalidade chave que impede o fluxo normal de trabalho do usuário, sem um plano de contorno óbvio (ex: e-mail de convite não disparar, impossibilidade de criar novas senhas). Bloqueia a liberação.
* **Média:** Defeito em funcionalidades secundárias ou fluxos que possuem caminho alternativo funcional (ex: erro estético no gráfico evolutivo, atraso na atualização do ranking). Pode liberar mediante acordo e inclusão em hotfix planejado.
* **Baixa:** Problemas cosméticos de layout, espaçamento, pequenos erros de digitação na interface que não impactam a usabilidade. Não bloqueia a liberação.

---

## 3. Tabela de Bugs Identificados

*Nota: Devido à natureza pendente da execução dos testes na Sprint 4, a tabela de controle de defeitos encontra-se vazia, aguardando preenchimento à medida que as rodadas de homologação forem executadas.*

| ID Bug | Caso Relacionado | Funcionalidade | Descrição do Bug | Severidade | Status | Resolução / Comentários |
| :---: | :---: | :--- | :--- | :---: | :---: | :--- |
| *A preencher* | *A preencher* | *A preencher* | *A preencher* | *A preencher* | *A preencher* | *A preencher* |

---

## 4. Bugs Pendentes
Até a presente data, não existem bugs pendentes de correção técnica, dado que o processo de execução de QA não identificou falhas em decorrência da pendência de deploy final e início dos testes em homologação. 

*Status Atual: **Nenhum bug reportado (Aguardando rodada de testes).***

---

## 5. Validação Pós-Correção
Ao ser notificado da correção de um defeito pelo time de desenvolvimento, o analista de QA executará a validação seguindo as seguintes etapas:
1. **Implantação:** Verificar se o build correspondente à correção foi devidamente aplicado no ambiente de homologação.
2. **Reteste:** Repetir exatamente o caso de teste associado ao bug que falhou anteriormente.
3. **Teste de Regressão Adjacente:** Validar se os componentes que se relacionam com o trecho de código modificado não foram afetados colateralmente pela correção.
4. **Mascaramento de Evidência:** Registrar a nova evidência de sucesso com mascaramento de dados (e-mail, CPF, telefone).
5. **Atualização de Status:** Mudar o status do bug para `Fechado` na tabela de controle de defeitos e o caso de teste correspondente na planilha para `Passou`.

---

## 6. Conclusão
O fluxo de logging e correção de erros da Sprint 4 do Care Daily está totalmente mapeado. A validação prática e a abertura de bugs reais ocorrerão em sincronia com o avanço da execução das planilhas de testes em homologação.
