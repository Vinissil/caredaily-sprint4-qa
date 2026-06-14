# Automação de Testes - Care Daily (Sprint 4)

Este diretório contém a estrutura de testes de automação preparados para a Sprint 4 do projeto **Care Daily** usando o **Selenium IDE**.

---

## 1. Ferramenta Escolhida
A ferramenta adotada para a automação deste ciclo foi o **Selenium IDE** (Record and Playback), integrado como extensão no navegador de internet. Essa escolha viabiliza a rápida simulação de ações do usuário (cliques, preenchimento de campos e asserções visuais) diretamente na camada do navegador, facilitando a validação das interfaces web e responsivas sem demandar infraestrutura complexa de código.

---

## 2. Objetivo dos Testes Automatizados
O objetivo dos testes automatizados da Sprint 4 é validar a regressão rápida dos fluxos mais críticos de acesso, navegação e escrita no banco de dados do sistema, especificamente:
* Login seguro de usuários profissionais (Nutricionistas) e pacientes.
* Recusa e segurança contra credenciais inválidas.
* Integridade na navegação por links internos do painel.
* Cadastro e exibição em tempo real de novos alimentos no plano nutricional de pacientes.

---

## 3. Pré-requisitos
Para executar o roteiro automatizado contido neste repositório, você precisará de:
1. Um navegador baseado no motor Chromium (Google Chrome, Microsoft Edge) ou Mozilla Firefox.
2. A extensão do **Selenium IDE** instalada no navegador. O download oficial pode ser obtido na Chrome Web Store ou Firefox Add-ons.
3. A aplicação Care Daily em execução em ambiente local ou staging.

---

## 4. URL do Sistema
A URL base configurada nos testes automatizados é:
* `http://localhost:3000`

> [!WARNING]
> **Ajuste da URL:**
> Caso sua aplicação esteja rodando em uma porta diferente (ex: `http://localhost:8080`, `http://localhost:5173`) ou em um servidor remoto de homologação (ex: `https://staging.caredaily.com`), **você deve atualizar o campo "URL" no Selenium IDE** antes de iniciar a execução da suite.

---

## 5. Como Importar o Arquivo `.side` no Selenium IDE
1. Abra seu navegador de internet e clique no ícone da extensão do **Selenium IDE**.
2. Na janela aberta da ferramenta, selecione a opção **"Open an existing project"** (Abrir um projeto existente).
3. Navegue nos diretórios do seu computador até a pasta desta entrega e selecione o arquivo:
   - `CareDaily_Sprint4_QA_Entrega/automacao/selenium_ide_caredaily.side`
4. O Selenium IDE carregará o projeto e listará os 4 casos de teste (`TA001` a `TA004`) no painel esquerdo.

---

## 6. Como Executar os Testes
1. Para executar todos os testes em lote (suite): clique no botão **"Run all tests"** (ícone de duas setas de play no topo da janela).
2. Para executar um teste isoladamente: selecione o caso de teste desejado na listagem lateral esquerda e clique no botão **"Run current test"** (ícone de uma seta de play).
3. Acompanhe a execução automática da janela do navegador controlada pelo Selenium IDE.
4. Verifique a aba **"Log"** na parte inferior da ferramenta para certificar-se de que todos os comandos (open, type, click, assert) retornaram sucesso (cor verde).

---

## 7. Como Gravar Evidência em Vídeo
Como as evidências de teste em vídeo são obrigatórias para homologação dos cenários automatizados:
1. Abra um software de gravação de tela de sua preferência (ex: *OBS Studio*, *Loom*, ferramenta nativa de gravação do Windows `Win + Alt + R`, ou extensão de browser).
2. Configure a gravação para capturar a tela inteira (Desktop) contendo tanto a janela do navegador onde o teste roda quanto a janela do Selenium IDE exibindo o progresso dos logs em tempo real.
3. Inicie a gravação, execute os testes na suite do Selenium IDE e aguarde a finalização com sucesso de todas as etapas.
4. Pare a gravação e salve o vídeo em formato estável (preferencialmente `.mp4`).

---

## 8. Onde Salvar as Evidências
* **Vídeos de Execução:** Devem ser salvos no diretório:
  - `CareDaily_Sprint4_QA_Entrega/automacao/evidencias_automacao/`
* **Nomenclatura do Vídeo:** Salve preferencialmente com o nome `video_execucao_sprint4.mp4` ou grave vídeos individuais denominados `video_execucao_ta001.mp4`, `video_execucao_ta002.mp4` etc.
* **Prints Adicionais:** Caso deseje anexar capturas estáticas adicionais do log de sucesso do Selenium IDE, armazene-as na mesma pasta.

> [!IMPORTANT]
> **Alerta de LGPD:**
> Não esqueça de revisar os vídeos e prints antes de realizar o envio final. Dados de identificação de usuários reais (CPF, e-mails pessoais, telefones) não devem ser exibidos de forma desprotegida.

---

## 9. 🔗 Link do Vídeo de Execução
Link do vídeo de execução: A preencher
