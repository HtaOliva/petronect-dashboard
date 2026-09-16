# 🚀 MVP Petronect: Customer Success e Reengajamento B2B

## 📌 Visão Geral do Projeto

Este projeto é um MVP (Produto Mínimo Viável) desenvolvido durante o **Hackathon Conexão Ancestral** da KODIE Academy, em parceria com a Petronect, para resolver os principais atritos de usabilidade e suporte do Portal Petronect.

Focamos em transformar uma experiência de **"SAC reativo e lento"** em um **reengajamento proativo**, garantindo que fornecedores PMEs não percam prazos de editais por falhas de sistema ou bloqueios de e-CNPJ/CPF.

A solução combina **design de jornada**, **captura de comportamento** e **motor de regras** para identificar travamentos e agir antes que o fornecedor desista.

---

## 🎯 O Problema

A Petronect não consegue identificar quais são os gargalos dos usuários do seu Portal. Nossa pesquisa, baseada em relatórios públicos sobre a Petronect, documentação institucional e reclamações públicas de fornecedores em canais como o Canal Fornecedor Petrobras, indicou três problemas principais:

1. **Bloqueios de cadastro** por lentidão na validação do e-CNPJ;
2. **Travamento de acesso** devido a CPFs vinculados a contas inativas;
3. **Falta de transparência e demora (SAC no escuro)**, o que gera abandono do funil de licitações.

Essas dores estão documentadas em fontes públicas e afetam especialmente pequenas e médias empresas, que não possuem departamentos de TI dedicados.

---

## 💡 A Solução

Desenvolvemos uma jornada de usuário redesenhada e inteligente, composta por **quatro pilares**:

### 1. Autonomia e Clareza
Telas limpas, responsivas e com identidade visual corporativa, dando ao usuário a opção de resolver seus vínculos de CPF com um clique.

### 2. Assistência Proativa (WhatsApp)
Acionamento imediato de suporte humano para intervir no erro antes que o cliente desista.

### 3. Transparência de Chamados
Uma interface de acompanhamento de status em tempo real (stepper de resolução).

### 4. Radar de Abandono (Motor de Regras)
Detecção automática de padrões de travamento (ex.: rage clicks no botão de validação) e disparo proativo de atendimento, sem que o fornecedor precise abrir chamado.

---

## 🚧 Status Atual do Desenvolvimento (Roadmap)

Nossa equipe dividiu o desenvolvimento em três frentes para garantir entregas ágeis:

### ✅ Fase 1: Prototipagem e UX/UI (Concluído)
- Criação de fluxos de Alta Fidelidade no Figma.
- Tela de Credenciamento Simplificado PME.
- Tela de Tratamento de Erro de Vínculo de CPF com opções de autonomia.
- Tela de Acompanhamento de Chamados (Status Proativo).
- Tela 4: Painel Interno — Radar de Abandono com Motor de Regras.

*Responsável: Design e Estruturação de Produto.*

### ✅ Fase 2: Monitoramento de Dados Comportamentais (Concluído)
- Configuração do ambiente PostHog (camada gratuita).
- Envio de eventos `$rageclick` simulados com propriedades reais (`$el_text`, `$current_url`, `click_count`, `time_span_seconds`).
- Validação da captura de rage clicks no dashboard do PostHog.
- Mapeamento de eventos de clique (ex.: acionamento do botão do WhatsApp e erros de CPF) para geração do Funil de Conversão e Abandono.

*Responsável: Integração e Análise de Dados.*

### ✅ Fase 3: Motor de Regras e Acionamento (Concluído)
- Definição da lógica: `SE $rageclick no botão "Validar e Prosseguir" E frequência > 5 cliques em 3 minutos ENTÃO acionar atendimento proativo`.
- Integração com a Tela 4 (Radar de Abandono) para visualização do sinal capturado.
- Timeline de resolução: 14:02 (detecção) → 14:07 (chamado aberto) → 14:09 (especialista atribuído) → 14:20 (previsão de resolução).

*Responsável: Integração e Análise de Dados.*

---

## 📊 Prova Técnica: Captura de Rage Clicks no PostHog

Para validar a viabilidade técnica da solução, enviamos eventos `$rageclick` simulados para o PostHog, reproduzindo o comportamento de um fornecedor travado no botão "Validar e Prosseguir".

**Evidência capturada:**

![Atividade no PostHog com eventos de rage click](https://github.com/HtaOliva/petronect-dashboard/blob/main/tela-rageclick.png)

*Figura 1 — Atividade no PostHog exibindo os eventos `$rageclick` capturados do `fornecedor_123`.*

**O que a evidência mostra:**
- 6 eventos `$rageclick` capturados do mesmo fornecedor (`fornecedor_123`);
- Propriedade `$el_text: "Validar e Prosseguir"` visível no detalhe do evento;
- Janela de aproximadamente 3 minutos entre os eventos (padrão de travamento);
- URL de origem: `https://www.petronect.com.br/irj/portal/anonymous/pt`.

Implicação: o PostHog detecta rage clicks nativamente e fornece os dados necessários para o motor de regras disparar o atendimento proativo. A camada de captura é real e validada.


---

## 🌱 Impacto Esperado

**Para o fornecedor:**
- Menos abandono por travamento sistêmico;
- Mais contratos concluídos dentro do prazo do edital;
- Transparência total no acompanhamento de chamados.

**Para a Petronect:**
- Redução de chamados manuais no SAC;
- Melhor priorização do time de atendimento;
- Dados comportamentais para decisões de produto.

**Para o ecossistema:**
- Maior inclusão de fornecedores PMEs;
- Conexão com a história de diversidade e sustentabilidade da Petronect.

---

## 🛠️ Tecnologias Utilizadas

- **Design:** Figma (protótipo de alta fidelidade e interativo);
- **Análise de Comportamento:** PostHog (captura de rage clicks e eventos personalizados);
- **Documentação:** GitHub (README e versionamento);
- **Apresentação:** Google Slides (pitch de até 10 minutos).

---

## 🔗 Links Importantes

- **Protótipo Interativo:** [Acessar MVP no Figma](https://sl1nk.com/uwsi63b)
- **Repositório GitHub:** [Link do repositório](https://github.com/HtaOliva/petronect-dashboard)
- **Vídeo de Apresentação:** [Link do YouTube não listado]
- **Documento do Projeto:** [Link do Google Drive](https://drive.google.com/drive/folders/1nVUW6xbnnW3-nLqua9US8xjjSzgBkiaX?usp=sharing)

---

## 👩‍💻 Equipe

Projeto desenvolvido pela **Equipe 1**:

- Ágata de Oliveira
- Mellyssa Stephanny de Jesus Mendes
- Rayane Climaco
- Vivian Cristyelly Santos dos Santos
- Alexsandra Joice Chaves dos Santos

---

*"O Portal que não só registra cliques, mas entende pessoas"*
