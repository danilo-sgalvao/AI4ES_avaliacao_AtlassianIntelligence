## **Entrada 7 – Gerenciamento**

### **Plano de projeto**

#### “Proponha um cronograma baseado em sprints.”

Segue uma proposta de cronograma em sprints para o projeto KAN – Minha equipe com base nas issues atuais:

Visão geral do projeto:

Minha equipe | Lista

Todas as issues:

18 Issues

Vou assumir sprints de 2 semanas, equipe pequena (1–2 devs) e foco em entregar algo usável cedo.

Sprint 1 – Fundamentos de Arquitetura e UI

Objetivo: ter a base da aplicação web pronta, com identidade visual inicial.

Issues sugeridas:

KAN-1 – Arquitetura/UI (Tarefa macro)

KAN-1: Arquitetura/UI

A fazer

KAN-2 – Definir arquitetura do sistema de reservas (web)

KAN-2: Definir arquitetura do sistema de reservas (web)

A fazer

KAN-7 – Definir guideline visual (UI) e paleta de cores (verde/azul)

KAN-7: Definir guideline visual (UI) e paleta de cores (verde/azul)

A fazer

Resultado esperado da Sprint 1:

Projeto criado (backend \+ frontend) com camadas definidas.

Estrutura inicial de módulos (Quartos, Hóspedes, Reservas).

Paleta de cores e componentes básicos definidos (botões, inputs, layout base).

Sprint 2 – Gestão de Quartos (MVP)

Objetivo: permitir cadastrar e visualizar quartos.

Issues sugeridas:

KAN-3 – Gestão de Quartos

KAN-3: Gestão de Quartos

A fazer

KAN-13 – Implementar modelo de dados de Quartos e Camas

KAN-13: Implementar modelo de dados de Quartos e Camas 

A fazer

KAN-14 – Tela de cadastro/edição de Quartos

KAN-14: Tela de cadastro/edição de Quartos

A fazer

KAN-15 – Tela de listagem de Quartos

KAN-15: Tela de listagem de Quartos

A fazer

Resultado esperado da Sprint 2:

Banco/modelo de quartos funcionando.

Tela para cadastrar e editar quartos.

Tela de listagem com pelo menos filtros básicos por status.

Sprint 3 – Gestão de Hóspedes (MVP)

Objetivo: permitir cadastrar e buscar hóspedes.

Issues sugeridas:

KAN-4 – Gestão de Hóspedes

KAN-4: Gestão de Hóspedes

A fazer

KAN-16 – Implementar modelo de dados de Hóspede

KAN-16: Implementar modelo de dados de Hóspede

A fazer

KAN-17 – Tela de cadastro/edição de Hóspede

KAN-17: Tela de cadastro/edição de Hóspede

A fazer

KAN-18 – Tela de listagem de Hóspedes

KAN-18: Tela de listagem de Hóspedes

A fazer

Resultado esperado da Sprint 3:

Modelo de hóspede criado.

Cadastro/edição de hóspede funcional.

Lista com busca por nome/documento/telefone.

Sprint 4 – Gestão de Reservas (Modelo \+ Telas principais)

Objetivo: criar o fluxo básico de reserva.

Issues sugeridas:

KAN-5 – Gestão de Reservas

KAN-5: Gestão de Reservas

A fazer

KAN-19 – Implementar modelo de dados de Reserva e regras básicas

KAN-19: Implementar modelo de dados de Reserva e regras básicas

A fazer

KAN-20 – Tela de listagem de Quartos para Gestão de Reservas

KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

KAN-21 – Tela de criação/edição de Reserva

KAN-21: Tela de criação/edição de Reserva

A fazer

Resultado esperado da Sprint 4:

Modelo de reserva funcionando (com regras de disponibilidade básicas).

Tela de criação/edição de reserva usando hóspedes e quartos já cadastrados.

Tela de apoio para escolher quartos para a reserva.

Sprint 5 – Integração, Navegação e UX

Objetivo: integrar os módulos e melhorar usabilidade.

Issues sugeridas:

KAN-6 – Integração, Navegação e UX Geral

KAN-6: Integração, Navegação e UX Geral

A fazer

KAN-22 – Implementar navegação entre módulos

KAN-22: Implementar navegação entre módulos

A fazer

KAN-23 – Melhorias de UX e feedback ao usuário

KAN-23: Melhorias de UX e feedback ao usuário

A fazer

Resultado esperado da Sprint 5:

Menu/navegação fluindo entre Quartos, Hóspedes e Reservas.

Mensagens de sucesso/erro e validações de formulário mais amigáveis.

Filtros/ordenação refinados nas listas.

Ordem geral dos sprints

Sprint 1 – Arquitetura \+ UI base (KAN-1, KAN-2, KAN-7)

Sprint 2 – Quartos (KAN-3, KAN-13, KAN-14, KAN-15)

Sprint 3 – Hóspedes (KAN-4, KAN-16, KAN-17, KAN-18)

Sprint 4 – Reservas (KAN-5, KAN-19, KAN-20, KAN-21)

Sprint 5 – Navegação \+ UX (KAN-6, KAN-22, KAN-23)

Se estiver ok para você, no próximo passo posso:

Sugerir metas (Sprint Goals) textuais para cada sprint, ou

Detalhar ordem sugerida de implementação dentro de cada sprint (por exemplo, KAN-13 → KAN-14 → KAN-15).

Qual dos dois você prefere que eu faça agora?

#### “Estime esforço em story points ou horas.”

Vou propor estimativas em story points para cada issue, assumindo:

Time de 1 dev full-stack júnior/pleno (você)

Story points em escala Fibonacci: 1, 2, 3, 5, 8, 13

1 SP ≈ 4 a 6h de trabalho focado para este contexto de projeto pessoal

Issues do projeto KAN:

https://versaocompleta.atlassian.net/issues/?jql=project%20%3D%20KAN%20ORDER%20BY%20created%20DESC

Board:

https://versaocompleta.atlassian.net/jira/software/projects/KAN/list?jql=project%20%3D%20KAN%20ORDER%20BY%20created%20DESC

1\. Arquitetura / UI

KAN-1 – Arquitetura/UI (Tarefa “guarda-chuva”) – 0 SP

https://versaocompleta.atlassian.net/browse/KAN-1

Use como epic/tarefa macro, não precisa de SP (os pontos ficam nas subtasks).

KAN-2 – Definir arquitetura do sistema de reservas (web) – 5 SP

https://versaocompleta.atlassian.net/browse/KAN-2

Escopo típico:

Definir camadas (API, domínio, persistência, frontend).

Definir tecnologias, estrutura de pastas, padrão de autenticação (mínimo).

Subir projeto base rodando.

KAN-7 – Definir guideline visual (UI) e paleta de cores (verde/azul) – 3 SP

https://versaocompleta.atlassian.net/browse/KAN-7

Escopo:

Definir paleta, tipografia, espaçamentos.

Criar componentes base (botão, input, títulos).

Documentar minimamente (README ou figma simples se quiser).

2\. Gestão de Quartos

KAN-3 – Gestão de Quartos (macro) – 0 SP

KAN-3: Gestão de Quartos

A fazer

KAN-13 – Implementar modelo de dados de Quartos e Camas – 3 SP

KAN-13: Implementar modelo de dados de Quartos e Camas 

A fazer

Criar entidades/tabelas, migrations, repositórios.

CRUD básico na camada de serviço.

KAN-14 – Tela de cadastro/edição de Quartos – 5 SP

KAN-14: Tela de cadastro/edição de Quartos

A fazer

Form de criação/edição.

Validações \+ mensagens de erro.

Integração com API de quartos.

KAN-15 – Tela de listagem de Quartos – 3 SP

KAN-15: Tela de listagem de Quartos

A fazer

Lista paginada ou simples.

Filtro por status.

Ação para editar / ver detalhes.

3\. Gestão de Hóspedes

KAN-4 – Gestão de Hóspedes (macro) – 0 SP

KAN-4: Gestão de Hóspedes

A fazer

KAN-16 – Implementar modelo de dados de Hóspede – 3 SP

KAN-16: Implementar modelo de dados de Hóspede

A fazer

Entidade/tabela de hóspede, migrations.

Serviços para criar/atualizar/buscar.

KAN-17 – Tela de cadastro/edição de Hóspede – 5 SP

KAN-17: Tela de cadastro/edição de Hóspede

A fazer

Form com campos obrigatórios, máscaras (se quiser) e validação.

Integração com API.

KAN-18 – Tela de listagem de Hóspedes – 3 SP

KAN-18: Tela de listagem de Hóspedes

A fazer

Lista com filtros por nome, documento, telefone.

Link para editar/visualizar detalhes.

4\. Gestão de Reservas

KAN-5 – Gestão de Reservas (macro) – 0 SP

KAN-5: Gestão de Reservas

A fazer

KAN-19 – Implementar modelo de dados de Reserva e regras básicas – 5 SP

KAN-19: Implementar modelo de dados de Reserva e regras básicas

A fazer

Entidade/tabela de reserva \+ status.

Regras mínimas de disponibilidade (sem overbooking).

Serviços para criar/atualizar/cancelar.

KAN-20 – Tela de listagem de Quartos para Gestão de Reservas – 3 SP

KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

Lista voltada para escolha em reserva, com estado de disponibilidade.

KAN-21 – Tela de criação/edição de Reserva – 8 SP

KAN-21: Tela de criação/edição de Reserva

A fazer

Form com seleção de hóspede, datas, quarto/tipo, número de pessoas.

Chamada para verificação de disponibilidade.

Fluxo de edição/cancelamento.

5\. Integração, Navegação e UX Geral

KAN-6 – Integração, Navegação e UX Geral (macro) – 0 SP

KAN-6: Integração, Navegação e UX Geral

A fazer

KAN-22 – Implementar navegação entre módulos – 3 SP

KAN-22: Implementar navegação entre módulos

A fazer

Menu lateral/topo ligando Quartos, Hóspedes, Reservas.

Estados ativos, rotas protegidas.

KAN-23 – Melhorias de UX e feedback ao usuário – 5 SP

KAN-23: Melhorias de UX e feedback ao usuário

A fazer

Mensagens de sucesso/erro padronizadas.

Tratamento de erros da API.

Pequenas melhorias de layout/validações nos formulários já criados.

6\. Visão de esforço total

Somando só subtasks (onde está o trabalho real):

KAN-2: 5

KAN-7: 3

KAN-13: 3

KAN-14: 5

KAN-15: 3

KAN-16: 3

KAN-17: 5

KAN-18: 3

KAN-19: 5

KAN-20: 3

KAN-21: 8

KAN-22: 3

KAN-23: 5

Total ≈ 54 story points

Se 1 SP ≈ 0,5 dia de trabalho focado (4h), então:

54 SP ≈ 27 dias de trabalho focado

Com 5 dias úteis/semana → \~5 a 6 semanas, o que bate bem com as 5 sprints de 2 semanas que desenhamos, considerando que você nem sempre vai estar 100% dedicado.

7\. Se você preferir em horas

Usando uma média de 1 SP ≈ 5h:

3 SP ≈ 15h

5 SP ≈ 25h

8 SP ≈ 40h

Você pode anotar isso em cada issue como referência, mas manter o planejamento em story points é melhor para ajustes futuros de velocidade.

Se quiser, no próximo passo eu posso:

Sugerir quantos SP colocar em cada sprint com base nesse total, ou

Gerar uma tabela (CSV) com Issue, Summary, Story Points pronta para você copiar/colar no Jira (campo SP). O que te ajuda mais agora?

### **Gestão de riscos**

#### “Liste os riscos técnicos e gerenciais com planos de mitigação.”

Abaixo estão os principais riscos do seu projeto KAN – sistema de gestão hoteleira, separados em técnicos e gerenciais, com plano de mitigação prático para você aplicar no seu dia a dia (como dev solo).

Projeto (para referência):

https://versaocompleta.atlassian.net/jira/software/projects/KAN/list?jql=project%20%3D%20KAN%20ORDER%20BY%20created%20DESC

1\. Riscos Técnicos

Risco T1 – Arquitetura mal definida / difícil de evoluir

Descrição: decisões apressadas na arquitetura (camadas, modelos, autenticação) podem dificultar evolução de módulos como Quartos, Hóspedes e Reservas.

Impacto: alto – retrabalho grande, código difícil de manter.

Probabilidade: média.

Mitigação:

Dedicar de fato uma parte da Sprint 1 para KAN-2 (arquitetura) com foco em:

Separação clara frontend / backend.

Camadas mínimas (API, domínio/serviço, persistência).

Módulos separados para Quartos, Hóspedes, Reservas.

Criar um doc simples de arquitetura (pode ser um README ou página num doc) com:

Tecnologias usadas.

Estrutura de pastas.

Padrões de naming.

Revisar esse doc antes de começar KAN-13/16/19 (modelos de dados).

Risco T2 – Modelo de dados inconsistente ou rígido

Descrição: entidades de Quartos, Hóspedes e Reservas mal pensadas (campos faltando, relacionamentos ruins) podem gerar gambiarras futuramente.

Impacto: alto – impacto em todo o sistema.

Probabilidade: média.

Mitigação:

Tratar KAN-13, KAN-16 e KAN-19 como “design de domínio”, não só tabelas:

Desenhar rapidamente diagramas de entidade-relacionamento (pode ser papel mesmo) antes de codar.

Validar regras básicas no começo:

Uma reserva sempre tem 1 hóspede e 1 quarto/tipo.

Regras de status (criada, confirmada, em estadia, finalizada, cancelada).

Manter migrações pequenas e frequentes, evitando mudanças gigantes.

Risco T3 – Regras de disponibilidade e overbooking mal implementadas

Descrição: lógica de disponibilidade de quartos é delicada (datas, status, sobreposição). Implementar de forma ingênua pode permitir reservas conflitantes.

Impacto: alto – principal valor do sistema.

Probabilidade: média.

Mitigação:

Em KAN-19 (modelo de Reserva):

Escrever cenários de teste mental (ou testes automatizados simples) para:

Reserva exata sobre período já ocupado.

Reserva que começa no dia de saída de outra (permitido).

Mudança de datas em reserva existente.

Implementar uma única função de verificação de disponibilidade usada em:

Criação de reserva.

Edição de reserva.

Documentar em texto claro a regra de negócio:

“Um quarto está disponível se não houver reserva com interseção entre data\_entrada e data\_saida-1”.

Risco T4 – Acoplamento forte entre telas e APIs

Descrição: front acoplado diretamente às estruturas internas do backend (sem DTOs/contratos claros) dificulta mudanças futuras.

Impacto: médio.

Probabilidade: média/alta.

Mitigação:

Definir contratos de API simples para:

Quartos (GET/POST/PUT).

Hóspedes.

Reservas.

Evitar expor diretamente o modelo interno (por exemplo, campos técnicos) nas respostas; usar objetos de resposta mais “limpos”.

Criar uma pequena camada de serviços no frontend (por ex. roomsService, guestsService, reservationsService) para isolar chamadas HTTP do resto da UI.

Risco T5 – UX confusa e navegação ruim

Descrição: navegação pouco intuitiva entre Quartos, Hóspedes e Reservas vai deixar o fluxo de trabalho travado.

Impacto: médio.

Probabilidade: alta (é comum em projetos solo).

Mitigação:

Priorizar KAN-22 (navegação) e KAN-23 (UX) na Sprint 5, mas já:

Definir um menu lateral padrão desde a Sprint 1 (placeholder) com seções fixas.

Criar wireframes simples das telas principais (pode ser rascunho no papel):

Lista de Quartos → ações (Detalhar/Editar).

Lista de Hóspedes → ações.

Lista de Reservas \+ criar reserva.

Revisitar mensagens de erro/sucesso ao final de cada sprint (check rápido).

Risco T6 – Falta de testes mínimos (quebra silenciosa de regras)

Descrição: sem testes básicos, pequenas mudanças podem quebrar regras de reserva, cálculos de datas, etc.

Impacto: médio/alto.

Probabilidade: média.

Mitigação:

Para cada caso crítico (ex.: criar reserva, cancelar reserva, checar disponibilidade), fazer pelo menos:

Testes manuais roteirizados anotados em um checklist simples,

Ou alguns testes unitários/integration leves para a função de disponibilidade.

No fim de cada sprint, rodar um mini smoke test:

Criar quarto → criar hóspede → criar reserva → editar → cancelar.

2\. Riscos Gerenciais / de Projeto

Risco G1 – Escopo crescer demais (scope creep)

Descrição: vontade de adicionar muitos detalhes (relatórios avançados, integrações externas, dashboard sofisticado) antes de fechar o básico.

Impacto: alto – projeto nunca “termina”.

Probabilidade: alta (especialmente em projeto pessoal).

Mitigação:

Tratar o que já está em KAN-1 a KAN-6 como MVP fechado.

Criar uma coluna “Backlog Futuro” ou um Epic “Melhorias Futuras” para ideias extras.

Só mover algo para o escopo das sprints se:

O básico de Quartos/Hóspedes/Reservas estiver estável, ou

For realmente necessário para demos.

Risco G2 – Estimativas muito otimistas

Descrição: story points subestimados geram frustração (“era para ter terminado essa sprint e não deu”).

Impacto: médio.

Probabilidade: alta na primeira sprint.

Mitigação:

Considerar a Sprint 1 como “calibração de velocidade”:

Ver quantos SP de fato você consegue entregar (ex.: 10, 15…).

Nas próximas sprints, planejar 70–80% do que você acha que daria e manter um pequeno buffer.

Ao final de cada sprint, anotar:

“SP planejados x SP concluídos” → isso vira sua “velocidade” real.

Risco G3 – Falta de disciplina de sprint (mudanças no meio)

Descrição: mudar o que está planejado no meio da sprint diminui foco e torna o cronograma irrelevante.

Impacto: médio.

Probabilidade: média.

Mitigação:

Ao início de cada sprint, registrar explicitamente:

Objetivo da sprint (ex.: “conseguir cadastrar e listar quartos e hóspedes”).

Issues selecionadas (com SP).

Durante a sprint:

Só troque issue se for realmente necessário; se entrar algo novo, anote que foi “scope added”.

No fim da sprint, registrar rapidamente:

O que foi feito / o que faltou / por quê.

Risco G4 – Falta de rastreabilidade entre requisitos, histórias e código

Descrição: com o tempo, fica difícil saber se um requisito já foi atendido, em qual issue, por qual commit.

Impacto: médio, mas crescente.

Probabilidade: média.

Mitigação:

Já fizemos o mapeamento Requisito → História → Issue (KAN-xx); agora:

Em cada issue, manter na descrição algo como:

Requisitos atendidos: R4, R5, R6

Usar o campo de “Links” no Jira para associar:

Tarefas macro (KAN-1… KAN-6) com as subtasks.

Se estiver usando Git:

Colocar a chave da issue no commit: KAN-14: implementa cadastro de quartos.

Risco G5 – Perda de motivação / interrupções longas

Descrição: como é um projeto próprio, é fácil ficar semanas sem mexer e depois perder o contexto.

Impacto: alto – dificuldade de retomar.

Probabilidade: média/alta.

Mitigação:

Trabalhar em blocos pequenos e fechados:

Ex.: terminar completamente a parte de Quartos (KAN-13/14/15) antes de começar Reservas.

No final de cada sessão de trabalho, escrever uma nota rápida (pode ser em um comentário na issue ou README):

“Próximo passo: implementar X / revisar Y”.

Revisar rapidamente essas notas quando voltar ao projeto.

Risco G6 – Falta de validação com usuário real (ou cenário real)

Descrição: você implementa tudo “no papel”, mas não testa com casos realistas de hotel, então regras importantes podem faltar.

Impacto: médio/alto.

Probabilidade: média.

Mitigação:

Criar 2 ou 3 “personas de hotel” fictícias:

Pequeno hotel com 10 quartos.

Pousada com tipos de quarto diferentes.

Testar o sistema simulando 1 semana típica:

Reservas de fim de semana, feriados, cancelamentos de última hora.

Se possível, conversar com alguém que já trabalhou em recepção/gestão de hotel para validar fluxos principais.

Risco G7 – Falta de documentação mínima

Descrição: depois de alguns meses, você esquece decisões importantes (por que usou tal regra, qual é o fluxo de check-in/out).

Impacto: médio.

Probabilidade: alta.

Mitigação:

Manter documentação extremamente enxuta, mas viva:

1 doc para Arquitetura/Decisões Técnicas.

1 doc para Regras de Negócio principais (reservas, status, disponibilidade).

Atualizar esse doc sempre que uma regra mudar.

Se você quiser, no próximo passo posso:

Montar uma tabela de riscos (ID, descrição, impacto, probabilidade, mitigação) em formato que você possa colar direto num doc ou planilha, ou

Sugerir qual risco atacar primeiro e como colocar isso explicitamente no seu board do Jira (ex.: tasks específicas de mitigação ligadas às sprints). Qual dos dois você prefere?

### **Governança e qualidade**

#### “Defina KPIs e critérios de qualidade para o projeto.”

Abaixo estão KPIs e critérios de qualidade pensados especificamente para o seu projeto KAN – Minha equipe (sistema de gestão hoteleira), que você gerencia no Jira em:

https://versaocompleta.atlassian.net/jira/software/projects/KAN/list?jql=project%20%3D%20KAN%20ORDER%20BY%20created%20DESC

Vou separar em:

KPIs de produto (qualidade do sistema para o usuário)

KPIs de processo/projeto (como você está executando o trabalho)

Critérios de qualidade técnica

Critérios de qualidade funcional/UX

Use isso como “checklist” no final de cada sprint.

1\. KPIs de Produto (Sistema de Gestão Hoteleira)

KPI P1 – Tempo médio para criar uma reserva (Fluxo Reservas)

Definição: tempo médio (em segundos) que um usuário leva para criar uma reserva simples (hóspede já cadastrado, quarto disponível).

Meta inicial: ≤ 2 minutos do início ao fim.

Como medir:

Manualmente no começo: cronometre você mesmo o fluxo completo (abrir tela → selecionar hóspede → selecionar datas/quarto → salvar).

No futuro, pode ser feito via logs/eventos de UI.

KPI P2 – Taxa de erros ao salvar formulários

Definição: % de tentativas de salvar formulários (quartos, hóspedes, reservas) que resultam em erro de validação ou erro técnico.

Meta inicial: ≤ 10% de erros de validação e 0% de erros técnicos (500, null reference etc.).

Como medir:

Em logs ou, inicialmente, anotando durante testes:

nº de tentativas de salvar / nº de erros.

KPI P3 – Consistência de disponibilidade (zero overbooking conhecido)

Definição: número de casos detectados em que o sistema permite reservas conflitantes no mesmo quarto e período.

Meta inicial: 0 casos em testes manuais de regressão.

Como medir:

Criar uma pequena bateria de testes manuais para disponibilidade, e rodar a cada alteração em KAN-19/21.

KPI P4 – Cobertura de fluxo de negócio principal

Definição: % dos fluxos principais de negócio implementados e funcionando:

Cadastro de Quarto

Cadastro de Hóspede

Criação de Reserva

Check-in

Check-out

Meta inicial:

Ao final da Sprint 4/5: 100% desses fluxos executáveis de ponta a ponta.

Como medir:

Checklist de “fluxos críticos”, marcando o que já é possível executar no sistema real.

KPI P5 – Satisfação de usabilidade (autoavaliação)

Definição: nota de 1 a 5 que você (e qualquer pessoa que testar) dá para:

Facilidade de navegar entre Quartos, Hóspedes e Reservas.

Clareza das mensagens de erro/sucesso.

Meta inicial: ≥ 4/5 na média.

Como medir:

Curto questionário (duas perguntas simples) após uma rodada de testes.

2\. KPIs de Processo / Projeto (Trabalho no Jira KAN)

KPI PR1 – Velocidade da Sprint

Definição: total de story points concluídos em cada sprint no projeto KAN.

Meta inicial: apenas medir nas duas primeiras sprints, depois estabilizar:

Ex.: média de 10–15 SP / sprint, dependendo do seu ritmo.

Como medir no Jira:

Configurar o campo de story points nas issues.

Ao final da sprint, somar SP de issues em “Done”.

KPI PR2 – Taxa de conclusão da Sprint

Definição: % de story points planejados que foram concluídos na sprint.

Meta saudável: 70–90% (nem muito baixo, nem “100% forçado”).

Fórmula:

SP concluídos / SP planejados \* 100

Uso:

Se estiver sempre \< 50%, você está planejando demais.

Se sempre 100% e sobrando, pode planejar um pouco mais.

KPI PR3 – Lead Time de uma issue

Definição: tempo médio entre “To Do” → “Done” para issues relevantes (por exemplo, KAN-14, KAN-17, KAN-21).

Meta inicial: ficar na casa de 3–7 dias por issue de 3–5 SP.

Como medir:

Usar datas de início/fim das issues no Jira.

Mesmo que seja manual, anotar no comentário quando começou e quando terminou.

KPI PR4 – Taxa de retrabalho

Definição: nº de issues que precisam ser reabertas ou ter correções significativas após consideradas “Done”.

Meta inicial: ≤ 10–20% das issues.

Como medir:

Se você mudou o status para Done e depois descobriu que precisava corrigir regra de negócio ou layout importante, anote isso como retrabalho.

3\. Critérios de Qualidade Técnica

Estes são “checks” que você pode fazer ao final da sprint em cada área.

Qualidade Técnica Q1 – Organização de código e arquitetura

Critérios:

Camadas claras no backend (controller, serviço, repositório/modelo).

Módulos separados para Quartos, Hóspedes, Reservas (pastas, namespaces).

Nenhuma tela importante acessando diretamente o banco; sempre via serviços/API.

Como verificar:

Olhar rapidamente a estrutura do projeto:

Pastas por domínio (rooms, guests, reservations).

Pastas por camada (controllers, services, repositories).

Qualidade Técnica Q2 – Tratamento de erros e logs

Critérios:

Para cada erro esperado (validação), mensagem amigável para o usuário.

Para erros inesperados (ex.: exceções), log minimamente gravado (mesmo que num console/log simples).

Meta:

Nenhum erro técnico aparecer em formato “cru” na tela (stack trace, mensagem de banco etc.).

Onde encaixa no KAN:

Muito ligado a KAN-23 – Melhorias de UX e feedback ao usuário.

Qualidade Técnica Q3 – Testes mínimos em regras críticas

Regras críticas:

Verificação de disponibilidade de quarto.

Cálculo das diárias no check-out.

Critérios:

Ter ao menos testes manuais roteirizados (roteiro de passos) para esses casos, ou alguns testes automatizados nessas funções.

Meta:

Rodar esses testes a cada alteração relevante em KAN-19/KAN-21.

Qualidade Técnica Q4 – Manutenibilidade do código

Critérios:

Funções com responsabilidade única e nomes claros.

Pouca duplicação de lógica (por exemplo, a regra de disponibilidade centralizada).

Comentários só onde realmente necessário (evitar comentários redundantes).

Como medir no dia a dia:

Pergunta simples para você mesmo:

“Se eu voltar aqui daqui 3 meses, eu entendo o que isso faz em menos de 5 minutos?”

4\. Critérios de Qualidade Funcional / UX

Qualidade Funcional F1 – Completude dos fluxos principais

Critérios:

É possível executar, sem quebrar, os fluxos:

Cadastro de quarto

Cadastro de hóspede

Criação de reserva

Edição/cancelamento de reserva

Check-in

Check-out

Meta por sprint:

Até Sprint 2: fluxos de Quartos completos.

Até Sprint 3: fluxos de Hóspedes completos.

Até Sprint 4: fluxo criar/editar/cancelar reservas.

Até Sprint 5: navegação fluida entre tudo.

Qualidade UX U1 – Consistência visual

Critérios:

Mesma paleta (cores, fontes) em todas as telas principais.

Mesmo estilo para botões (primário, secundário), campos obrigatórios, mensagens.

Meta:

Nenhuma tela “fora do padrão” ao navegar entre módulos – tudo deve parecer parte do mesmo sistema.

Associado a:

KAN-7 – Guideline visual

KAN-23 – UX e feedback

Qualidade UX U2 – Clareza de navegação

Critérios:

Menu sempre visível com seções: Quartos / Hóspedes / Reservas.

Rótulos claros nos botões (ex.: “Criar Reserva”, “Salvar”, “Cancelar”).

Meta:

Em um mini-teste, alguém que nunca viu o sistema consegue:

Encontrar a tela de criar reserva sem ajuda.

Associado a:

KAN-22 – Navegação entre módulos

Qualidade UX U3 – Feedback imediato ao usuário

Critérios:

Sempre que uma ação é feita (salvar, excluir, erro), há feedback visual:

Toast, alerta, mensagem perto do formulário.

Campos com erro são destacados.

Meta:

Nenhuma ação deixa o usuário “no escuro” (sem saber se funcionou ou não).

Associado a:

KAN-23 – Melhorias de UX e feedback ao usuário

Se quiser, posso te ajudar no próximo passo a:

Transformar esses KPIs em campos/labels no Jira (por exemplo, criando um checklist de critérios de qualidade por issue), ou

Gerar um modelo de “Definição de Pronto (DoD)” para você colar na descrição das histórias, incluindo parte desses critérios. O que você prefere?
