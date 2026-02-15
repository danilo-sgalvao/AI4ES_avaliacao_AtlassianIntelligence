## **Etapa 1 – Engenharia de Requisitos** 

### **Elicitação e estruturação de requisitos**

#### “Liste requisitos funcionais (RF) e não funcionais (RNF) para este sistema.”

Abaixo está uma primeira versão de requisitos funcionais (RF) e não funcionais (RNF) para o sistema de hotel que você vem detalhando (Gestão de Quartos, Hóspedes e Reservas), alinhado com o que já aparece nas tarefas do Jira, como:

KAN-3 – Gestão de Quartos: KAN-3: Gestão de Quartos

A fazer

KAN-5 – Gestão de Reservas: KAN-5: Gestão de Reservas

A fazer

KAN-20 – Tela de listagem de Quartos para Gestão de Reservas: KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

KAN-22 – Implementar navegação entre módulos: KAN-22: Implementar navegação entre módulos

A fazer

Vou separar por módulo e depois listar RNFs gerais.

Requisitos Funcionais (RF)

RF – Navegação e Estrutura Geral

RF01 – Menu de navegação entre módulos

O sistema deve oferecer um menu de navegação com, no mínimo, as seções:

Gestão de Quartos

Gestão de Hóspedes

Gestão de Reservas

(conforme KAN-22: KAN-22: Implementar navegação entre módulos

A fazer

RF02 – Rotas e URLs por módulo

O sistema deve configurar rotas/URLs específicas para cada módulo, permitindo acesso direto a cada tela via URL (KAN-22).

RF03 – Layout consistente entre módulos

Todas as telas dos módulos principais devem seguir o mesmo padrão de layout (tipografia, cores, espaçamentos, componentes de formulário e tabelas) para garantir consistência visual (KAN-22).

RF – Gestão de Quartos

RF04 – Cadastro de quarto

O sistema deve permitir cadastrar novos quartos com informações mínimas, como:

Número do quarto

Tipo do quarto (ex.: Standard, Luxo, Suíte, etc.)

Capacidade (número de hóspedes)

Status inicial (Livre, Ocupado, Manutenção, Limpeza)

RF05 – Edição de quarto

O sistema deve permitir editar dados de um quarto existente (tipo, capacidade, observações, etc.), exceto o identificador único (ex.: ID interno).

RF06 – Atualização de disponibilidade de quarto

O sistema deve permitir atualizar o status de disponibilidade de cada quarto entre: Livre, Ocupado, Manutenção, Limpeza (o mesmo conjunto usado como “Chip” em KAN-20: KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

RF07 – Listagem de quartos

O sistema deve exibir uma lista de todos os quartos com, pelo menos:

Número do quarto

Tipo do quarto

Status de disponibilidade

RF08 – Filtro e busca de quartos

O sistema deve permitir filtrar quartos por:

Tipo do quarto

Status de disponibilidade

Número do quarto (busca direta)

RF – Gestão de Hóspedes

RF09 – Cadastro de hóspede

O sistema deve permitir cadastrar hóspedes com, no mínimo:

Nome completo

Documento (CPF/Passaporte ou outro identificador)

Telefone

E-mail

RF10 – Edição de dados de hóspede

O sistema deve permitir alterar dados cadastrais de hóspedes.

RF11 – Listagem de hóspedes

O sistema deve listar hóspedes com, pelo menos:

Nome

Documento

Telefone

E-mail

RF12 – Busca de hóspedes

O sistema deve permitir busca de hóspedes por nome e/ou documento.

RF – Gestão de Reservas

RF13 – Criação de reserva

O sistema deve permitir criar reservas vinculando:

Quarto

Hóspede principal

Datas de check-in e check-out

Número de hóspedes

Status da reserva (Reservado, Em andamento, Concluído, Cancelado)

RF14 – Edição de reserva

O sistema deve permitir editar uma reserva existente (datas, hóspede, quarto, status), respeitando regras de negócio (ex.: não sobrepor reservas para o mesmo quarto).

RF15 – Cancelamento de reserva

O sistema deve permitir cancelar reservas, registrando a data do cancelamento e mantendo histórico.

RF16 – Associação reserva ↔ disponibilidade do quarto

Ao criar ou alterar uma reserva com status ativo (Reservado/Em andamento), o sistema deve atualizar automaticamente o status de disponibilidade do quarto (por exemplo, para Ocupado nas datas da reserva).

RF – Tela de listagem de Quartos para Gestão de Reservas (KAN-20)

Baseado em KAN-20: KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

RF17 – Tabela de quartos na área de Gestão de Reservas

Na tela de Gestão de Reservas, o sistema deve apresentar uma tabela de quartos contendo as colunas:

Número do quarto (Número)

Tipo do quarto (Texto)

Nome do hóspede (Texto – vazio se quarto livre)

Disponibilidade (Chip: Ocupado, Livre, Manutenção, Limpeza)

RF18 – Exibição condicional do nome do hóspede

Quando o quarto estiver livre (sem reserva ativa), a coluna “Nome do hóspede” deve ficar vazia ou com um indicativo de “Livre”.

RF19 – Exibição de chip de disponibilidade

A coluna “Disponibilidade” deve ser apresentada na forma de um chip com rótulos e cores diferentes para cada estado:

Ocupado

Livre

Manutenção

Limpeza

RF20 – Ação de edição de reserva por quarto

Para cada linha da tabela de quartos, o sistema deve exibir um botão ou ícone de lápis que, ao ser acionado, abra a tela de edição/criação de reserva correspondente ao quarto selecionado.

RF21 – Conexão com backend para reservas atuais

A listagem de quartos na tela de Gestão de Reservas deve se conectar ao backend para buscar a reserva atual associada a cada quarto e exibir corretamente o nome do hóspede e o status (conforme descrição em KAN-20).

RF – Fluxos gerais e regras de negócio

RF22 – Prevenção de conflito de reservas

O sistema não deve permitir a criação ou alteração de reservas que gerem sobreposição de períodos para o mesmo quarto.

RF23 – Histórico básico de reservas

O sistema deve manter o histórico de reservas (inclusive canceladas) para consultas futuras.

RF24 – Permitir visualização por data

O sistema deve permitir que o usuário visualize a ocupação dos quartos em uma data (ou intervalo de datas) específica, considerando as reservas ativas.

Requisitos Não Funcionais (RNF)

Abaixo estão RNFs gerais que fazem sentido para o estágio em que você está (MVP web):

RNF – Usabilidade e UX

RNF01 – Consistência visual entre módulos

Todas as telas devem manter padrões de cores, tipografia, componentes e espaçamento, conforme diretrizes definidas para o projeto (alinhado ao que você registrou em KAN-22).

RNF02 – Responsividade mínima

A interface deve ser utilizável em resoluções típicas de desktop e notebook, sem quebra de layout. (Se quiser podemos detalhar depois para mobile/tablet).

RNF03 – Feedback ao usuário

As principais ações (criar/editar/cancelar reserva, cadastrar quarto ou hóspede) devem exibir feedback claro de sucesso, erro ou validação (ex.: mensagens, toasts ou alertas).

RNF04 – Padrões de componentes reutilizáveis

Tabelas, formulários, botões, chips de status e campos de entrada devem reutilizar componentes padrão definidos pelo projeto de UI.

RNF – Desempenho

RNF05 – Tempo de resposta de listagens

As operações de listagem de quartos, hóspedes e reservas devem ter tempo de resposta inferior a 2 segundos em condições normais de uso e base de dados pequena/média (ex.: até algumas centenas de registros).

RNF06 – Eficiência de chamadas ao backend

As telas de listagem (como a de KAN-20) devem minimizar o número de chamadas ao backend (ex.: buscar dados paginados ou agregados em uma única chamada quando possível).

RNF – Segurança e Integridade

RNF07 – Integridade de dados de reserva

Transações de criação/edição/cancelamento de reserva devem garantir integridade entre reservas e status de quartos (evitar estados inconsistentes como quarto “Livre” com reserva ativa).

RNF08 – Validação de dados

Todos os formulários devem validar dados obrigatórios (nome de hóspede, datas, quarto, etc.) no frontend e no backend.

RNF09 – Controle de acesso (futuro)

O sistema deve ser projetado permitindo, no futuro, a inclusão de autenticação e perfis de acesso (por exemplo, recepcionista, gerente), mesmo que no MVP inicial tudo seja aberto.

RNF – Arquitetura e Manutenibilidade

RNF10 – Separação frontend/backend

O sistema deve ser desenvolvido com separação clara entre frontend e backend, consumindo APIs REST (ou GraphQL) para operações de gestão de quartos, hóspedes e reservas.

RNF11 – Padronização de APIs

As APIs devem seguir um padrão consistente de URLs, verbos HTTP e formatos de resposta (por exemplo, JSON com campos padronizados para dados e erros).

RNF12 – Versionamento básico de código

O código do sistema deve ser mantido em repositório com controle de versão (ex.: Git), com branches para desenvolvimento e produção.

RNF13 – Testabilidade

As principais regras de negócio (ex.: não sobrepor reservas, atualização de status de quartos) devem ser implementadas de forma a permitir testes automatizados.

RNF – Implantação e Ambiente

RNF14 – Ambiente de desenvolvimento e testes

O sistema deve poder ser executado em ambiente de desenvolvimento local (ex.: via Docker, ou stack simples com instruções claras) e ter ao menos um ambiente de testes/homologação.

RNF15 – Logs básicos de erro

O backend deve registrar erros em log com informações suficientes para diagnóstico (data/hora, endpoint, mensagem de erro, stack simplificada).

Se quiser, no próximo passo posso:

Transformar essa lista em issues/sub-tarefas novas no seu projeto KAN (seguindo o padrão de tasks \+ subtasks que você está usando), ou

Reorganizar os requisitos em formato de documento de especificação (SRS) pronto para colar em uma página do Confluence ou em um doc.

Qual dessas opções você prefere agora?

—---------------------------------------------------------------------------------------------------------------------------

#### “Classifique-os por prioridade (MoSCoW).”

Segue a classificação em MoSCoW dos requisitos que listei antes. Ajustei pensando em um MVP funcional para o sistema de reservas.

Legenda rápida:

M – Must have (essencial para o MVP)

S – Should have (importante, mas não bloqueia MVP)

C – Could have (legal ter, mas pode ficar para depois)

W – Won’t have now (fora de escopo do momento)

RF – Navegação e Estrutura Geral

RF01 – Menu de navegação entre módulos – M

RF02 – Rotas e URLs por módulo – M

RF03 – Layout consistente entre módulos – S

RF – Gestão de Quartos

RF04 – Cadastro de quarto – M

RF05 – Edição de quarto – M

RF06 – Atualização de disponibilidade de quarto – M

RF07 – Listagem de quartos – M

RF08 – Filtro e busca de quartos – S

RF – Gestão de Hóspedes

RF09 – Cadastro de hóspede – M

RF10 – Edição de dados de hóspede – M

RF11 – Listagem de hóspedes – M

RF12 – Busca de hóspedes – S

RF – Gestão de Reservas

RF13 – Criação de reserva – M

RF14 – Edição de reserva – M

RF15 – Cancelamento de reserva – S

RF16 – Associação reserva ↔ disponibilidade do quarto – M

RF – Tela de listagem de Quartos para Gestão de Reservas (KAN-20)

RF17 – Tabela de quartos na área de Gestão de Reservas – M

RF18 – Exibição condicional do nome do hóspede – M

RF19 – Exibição de chip de disponibilidade – S

RF20 – Ação de edição de reserva por quarto – M

RF21 – Conexão com backend para reservas atuais – M

RF – Fluxos gerais e regras de negócio

RF22 – Prevenção de conflito de reservas – M

RF23 – Histórico básico de reservas – S

RF24 – Permitir visualização por data – C

RNF – Usabilidade e UX

RNF01 – Consistência visual entre módulos – S

RNF02 – Responsividade mínima (desktop/notebook) – M

RNF03 – Feedback ao usuário (sucesso/erro) – M

RNF04 – Padrões de componentes reutilizáveis – S

RNF – Desempenho

RNF05 – Tempo de resposta de listagens \< 2s – S

RNF06 – Eficiência de chamadas ao backend – S

RNF – Segurança e Integridade

RNF07 – Integridade de dados de reserva – M

RNF08 – Validação de dados (front e back) – M

RNF09 – Controle de acesso (futuro) – W

RNF – Arquitetura e Manutenibilidade

RNF10 – Separação frontend/backend via APIs – M

RNF11 – Padronização de APIs – S

RNF12 – Versionamento básico de código (Git) – M

RNF13 – Testabilidade das regras de negócio – S

RNF – Implantação e Ambiente

RNF14 – Ambiente de desenvolvimento e testes – S

RNF15 – Logs básicos de erro no backend – S

Sugestão de próximo passo: quer que eu pegue só os itens Must have e transforme em uma lista de histórias/subtarefas prontas para você criar no projeto KAN (Minha equipe | Lista já com títulos e descrições em formato de Jira?

### **Histórias de usuário**

#### “Crie as histórias de usuário no formato padrão (Como \[tipo de usuário\], eu quero…, para que…).”

Vou criar um conjunto de histórias de usuário iniciais para o seu projeto “Minha equipe” (KAN), já seguindo o modelo que você prefere e alinhado com um sistema de gestão de hotel (quartos, hóspedes, reservas e UX), como conversamos antes.

Vou organizar por grandes temas, para você poder criar uma tarefa geral no KAN e depois adicionar subtarefas/tarefas filhas.

1\. Arquitetura / UI Geral

Definição da arquitetura do sistema

Como arquiteto de software, eu quero definir a arquitetura da aplicação (camadas, módulos e integrações), para que o sistema seja escalável, fácil de manter e permita evolução futura dos módulos de quartos, hóspedes e reservas.

Design do layout principal

Como usuário do sistema (recepcionista/gerente), eu quero um layout principal com menu lateral e área de conteúdo bem organizada, para que eu encontre rapidamente as funcionalidades de quartos, hóspedes e reservas sem me perder na interface.

Sistema de autenticação e perfis

Como administrador do hotel, eu quero controlar o acesso ao sistema por meio de login e perfis de usuário (admin, recepção, financeiro, etc.), para que cada colaborador veja apenas as funções necessárias às suas atividades.

2\. Gestão de Quartos

Cadastro de quartos

Como administrador do hotel, eu quero cadastrar e editar quartos com informações como número, tipo, capacidade, status e diária, para que eu mantenha um inventário atualizado e confiável dos quartos disponíveis.

Visualização da lista de quartos

Como recepcionista, eu quero visualizar uma lista de quartos com filtros por status (livre, ocupado, reservado, manutenção), para que eu identifique rapidamente quais quartos posso alocar para novos hóspedes.

Detalhes do quarto

Como recepcionista, eu quero abrir a tela de detalhes de um quarto com todas as informações relevantes (características, histórico recente de ocupação, observações), para que eu possa tomar decisões informadas ao atribuí-lo a um hóspede.

Gestão de status dos quartos

Como equipe de recepção, eu quero atualizar o status do quarto (ex.: de ocupado para limpeza, de limpeza para disponível), para que o estado operacional dos quartos reflita a situação real do hotel.

Tarifas e tipos de quarto

Como gerente do hotel, eu quero configurar tipos de quarto (standard, luxo, suíte, etc.) e suas diárias padrão, para que o sistema aplique automaticamente os valores corretos nas reservas.

3\. Gestão de Hóspedes

Cadastro de hóspedes

Como recepcionista, eu quero cadastrar hóspedes com dados pessoais (nome, documento, contato, endereço), para que o hotel mantenha um registro organizado para check-in, cobrança e obrigações legais.

Edição e consulta de hóspedes

Como recepcionista, eu quero editar dados de hóspedes e consultar rapidamente o histórico pelo nome ou documento, para que eu possa atualizar informações e recuperar registros com agilidade.

Histórico de estadias do hóspede

Como gerente do hotel, eu quero visualizar o histórico de estadias de um hóspede (datas, quartos, valores pagos), para que eu possa entender o comportamento do cliente e oferecer um atendimento personalizado.

Busca de hóspedes

Como recepcionista, eu quero buscar hóspedes por nome, documento ou telefone, para que eu encontre rapidamente o registro correto durante check-in, check-out ou contato.

4\. Gestão de Reservas

Criação de reservas

Como recepcionista, eu quero criar reservas informando hóspede, datas de entrada e saída, quarto (ou tipo de quarto) e número de pessoas, para que eu garanta a ocupação organizada dos quartos do hotel.

Verificação de disponibilidade

Como recepcionista, eu quero verificar automaticamente a disponibilidade de quartos para um período informado, para que eu evite conflitos de reservas e overbooking.

Visualização de reservas em lista

Como equipe de recepção, eu quero visualizar uma lista de reservas com filtros por data, status (confirmada, pendente, cancelada) e hóspede, para que eu gerencie facilmente a agenda do hotel.

Visualização de reservas em calendário

Como gerente do hotel, eu quero visualizar as reservas em um calendário (por quarto e por data), para que eu tenha uma visão clara da ocupação ao longo do tempo.

Edição e cancelamento de reservas

Como recepcionista, eu quero editar dados de reservas (datas, quarto, hóspede) e cancelar reservas quando necessário, para que eu mantenha as informações sempre atualizadas e consistentes com a realidade.

Check-in a partir da reserva

Como recepcionista, eu quero converter uma reserva em check-in no momento da chegada do hóspede, para que o processo de entrada seja rápido e sem retrabalho.

Check-out e fechamento de conta

Como recepcionista, eu quero realizar o check-out calculando automaticamente o valor da estadia com base nas diárias e períodos, para que eu consiga encerrar a estadia de forma correta e ágil.

5\. Melhorias de UX / Usabilidade

Feedback visual de ações

Como usuário do sistema, eu quero ver mensagens claras de sucesso ou erro ao salvar, editar ou excluir dados, para que eu tenha confiança de que minhas ações foram executadas corretamente.

Validações de formulário

Como usuário do sistema, eu quero ser avisado quando algum campo obrigatório estiver faltando ou inválido, para que eu possa corrigir rapidamente e evitar cadastros incompletos.

Navegação simples entre módulos

Como recepcionista, eu quero navegar facilmente entre Quartos, Hóspedes e Reservas a partir de um menu consistente, para que eu reduza o tempo gasto trocando de tela durante o atendimento.

Filtros e ordenação intuitivos

Como usuário do sistema, eu quero filtros e opções de ordenação claros nas listas (quartos, hóspedes, reservas), para que eu encontre rapidamente as informações mais relevantes para minha tarefa.

Responsividade da interface

Como usuário que pode acessar o sistema em telas diferentes (notebook, tablet), eu quero uma interface responsiva, para que eu consiga usar o sistema confortavelmente em diferentes dispositivos.

Se você quiser, no próximo passo posso:

Transformar cada um desses grupos (Arquitetura/UI, Quartos, Hóspedes, Reservas, UX) em tarefas “epic-like” para o seu projeto KAN, com uma lista de subtarefas sugeridas, já prontas para você copiar e colar no Jira. Quer que eu faça isso para algum desses módulos primeiro?

#### “Inclua critérios de aceitação no formato padrão (Given-When-Then).”

Perfeito, vou manter o mesmo conjunto de histórias e acrescentar critérios de aceitação em Given-When-Then. Você pode copiar e criar cada história em “Minha equipe | KAN”

URL do projeto: https://versaocompleta.atlassian.net/jira/software/projects/KAN/list?jql=project%20%3D%20KAN%20ORDER%20BY%20created%20DESC

1\. Arquitetura / UI Geral

1.1 Definição da arquitetura do sistema

História

Como arquiteto de software, eu quero definir a arquitetura da aplicação (camadas, módulos e integrações), para que o sistema seja escalável, fácil de manter e permita evolução futura dos módulos de quartos, hóspedes e reservas.

Critérios de aceitação

Cenário 1 – Documento de arquitetura criado

Given que o projeto do sistema de hotel está em fase inicial

When a arquitetura for definida

Then deve existir um documento de arquitetura descrevendo camadas, módulos e integrações principais

And o documento deve estar acessível para todos os membros da equipe

Cenário 2 – Módulos principais identificados

Given que a arquitetura foi documentada

When um desenvolvedor consultar o documento

Then ele deve conseguir identificar claramente os módulos de Quartos, Hóspedes e Reservas

And as responsabilidades de cada módulo devem estar descritas

1.2 Design do layout principal

História

Como usuário do sistema (recepcionista/gerente), eu quero um layout principal com menu lateral e área de conteúdo bem organizada, para que eu encontre rapidamente as funcionalidades de quartos, hóspedes e reservas sem me perder na interface.

Critérios de aceitação

Cenário 1 – Menu lateral com módulos principais

Given que estou autenticado no sistema

When acesso o layout principal

Then devo visualizar um menu lateral com opções para Quartos, Hóspedes e Reservas

Cenário 2 – Área de conteúdo destacada

Given que estou na tela principal

When seleciono um módulo no menu lateral

Then a área de conteúdo deve ser atualizada para exibir as funcionalidades do módulo escolhido

And o item selecionado no menu deve ficar visualmente destacado

1.3 Sistema de autenticação e perfis

História

Como administrador do hotel, eu quero controlar o acesso ao sistema por meio de login e perfis de usuário (admin, recepção, financeiro, etc.), para que cada colaborador veja apenas as funções necessárias às suas atividades.

Critérios de aceitação

Cenário 1 – Login com credenciais válidas

Given que o usuário possui um cadastro ativo

When ele informa usuário e senha válidos

Then deve ser autenticado e redirecionado para a tela principal

Cenário 2 – Login com credenciais inválidas

Given que o usuário não informa credenciais válidas

When ele tenta fazer login

Then deve ser exibida uma mensagem de erro informando que usuário ou senha são inválidos

And o acesso não deve ser permitido

Cenário 3 – Restrição por perfil

Given que o usuário está autenticado

And possui o perfil de recepção

When ele acessa o sistema

Then deve visualizar apenas as funções relacionadas a atendimento (Quartos, Hóspedes, Reservas)

And não deve visualizar funções administrativas restritas a administradores

2\. Gestão de Quartos

2.1 Cadastro de quartos

História

Como administrador do hotel, eu quero cadastrar e editar quartos com informações como número, tipo, capacidade, status e diária, para que eu mantenha um inventário atualizado e confiável dos quartos disponíveis.

Critérios de aceitação

Cenário 1 – Cadastro de quarto com dados válidos

Given que estou na tela de cadastro de quarto

And preenchi número, tipo, capacidade, status e diária

When clico em Salvar

Then o quarto deve ser gravado no sistema

And deve aparecer uma mensagem de sucesso

Cenário 2 – Campos obrigatórios não preenchidos

Given que estou na tela de cadastro de quarto

When tento salvar sem preencher todos os campos obrigatórios

Then deve ser exibida uma mensagem indicando quais campos precisam ser preenchidos

And o cadastro não deve ser concluído

Cenário 3 – Edição de quarto existente

Given que existe um quarto cadastrado

When acesso a tela de edição, altero algum campo e clico em Salvar

Then as novas informações devem ser atualizadas no sistema

And deve aparecer uma mensagem de sucesso

2.2 Visualização da lista de quartos

História

Como recepcionista, eu quero visualizar uma lista de quartos com filtros por status (livre, ocupado, reservado, manutenção), para que eu identifique rapidamente quais quartos posso alocar para novos hóspedes.

Critérios de aceitação

Cenário 1 – Exibição da lista de quartos

Given que existem quartos cadastrados

When acesso a tela de lista de quartos

Then devo ver uma lista com número, tipo, status e diária de cada quarto

Cenário 2 – Filtro por status

Given que estou na lista de quartos

When aplico um filtro por status “livre”

Then devem ser exibidos apenas os quartos com status livre

2.3 Detalhes do quarto

História

Como recepcionista, eu quero abrir a tela de detalhes de um quarto com todas as informações relevantes (características, histórico recente de ocupação, observações), para que eu possa tomar decisões informadas ao atribuí-lo a um hóspede.

Critérios de aceitação

Cenário 1 – Acesso aos detalhes

Given que estou na lista de quartos

When clico em um quarto específico

Then deve ser exibida uma tela com os detalhes completos do quarto

And devem aparecer, no mínimo, número, tipo, capacidade, status atual, diária e observações

2.4 Gestão de status dos quartos

História

Como equipe de recepção, eu quero atualizar o status do quarto (ex.: de ocupado para limpeza, de limpeza para disponível), para que o estado operacional dos quartos reflita a situação real do hotel.

Critérios de aceitação

Cenário 1 – Atualização de status

Given que estou na tela de detalhes ou edição de um quarto

When altero o status do quarto e salvo

Then o novo status deve ser gravado no sistema

And a lista de quartos deve refletir o status atualizado

2.5 Tarifas e tipos de quarto

História

Como gerente do hotel, eu quero configurar tipos de quarto (standard, luxo, suíte, etc.) e suas diárias padrão, para que o sistema aplique automaticamente os valores corretos nas reservas.

Critérios de aceitação

Cenário 1 – Cadastro de tipo de quarto

Given que estou na tela de gestão de tipos de quarto

When informo nome do tipo e diária padrão e clico em Salvar

Then o tipo de quarto deve ser gravado e ficar disponível para associação a quartos

Cenário 2 – Utilização da diária padrão em reservas

Given que existe um tipo de quarto com diária padrão configurada

And crio uma nova reserva selecionando esse tipo de quarto

When não informo uma diária específica

Then a diária da reserva deve ser preenchida automaticamente com a diária padrão do tipo de quarto

3\. Gestão de Hóspedes

3.1 Cadastro de hóspedes

História

Como recepcionista, eu quero cadastrar hóspedes com dados pessoais (nome, documento, contato, endereço), para que o hotel mantenha um registro organizado para check-in, cobrança e obrigações legais.

Critérios de aceitação

Cenário 1 – Cadastro com sucesso

Given que estou na tela de cadastro de hóspedes

And preenchi os campos obrigatórios (como nome e documento)

When clico em Salvar

Then o hóspede deve ser registrado no sistema

And deve ser exibida uma mensagem de sucesso

Cenário 2 – Dados obrigatórios ausentes

Given que estou na tela de cadastro de hóspedes

When tento salvar sem preencher os campos obrigatórios

Then deve ser exibida uma mensagem indicando quais campos são obrigatórios

And o cadastro não deve ser salvo

3.2 Edição e consulta de hóspedes

História

Como recepcionista, eu quero editar dados de hóspedes e consultar rapidamente o histórico pelo nome ou documento, para que eu possa atualizar informações e recuperar registros com agilidade.

Critérios de aceitação

Cenário 1 – Edição de hóspede

Given que existe um hóspede cadastrado

When abro seu cadastro, altero algum dado e salvo

Then as informações devem ser atualizadas no sistema

And deve ser exibida uma mensagem de sucesso

Cenário 2 – Consulta por documento

Given que existem hóspedes cadastrados

When informo um documento válido no campo de busca

Then deve ser exibido o hóspede correspondente ao documento informado

3.3 Histórico de estadias do hóspede

História

Como gerente do hotel, eu quero visualizar o histórico de estadias de um hóspede (datas, quartos, valores pagos), para que eu possa entender o comportamento do cliente e oferecer um atendimento personalizado.

Critérios de aceitação

Cenário 1 – Exibir histórico quando existem estadias

Given que o hóspede possui estadias anteriores registradas

When acesso a tela de detalhes do hóspede

Then deve ser exibida uma lista com datas de entrada e saída, quartos utilizados e valores pagos

Cenário 2 – Ausência de histórico

Given que o hóspede não possui estadias anteriores

When acesso a tela de detalhes do hóspede

Then deve ser exibida uma mensagem indicando que não há estadias registradas

3.4 Busca de hóspedes

História

Como recepcionista, eu quero buscar hóspedes por nome, documento ou telefone, para que eu encontre rapidamente o registro correto durante check-in, check-out ou contato.

Critérios de aceitação

Cenário 1 – Busca por nome

Given que existem hóspedes cadastrados

When informo um nome parcial ou completo no campo de busca

Then devem ser listados todos os hóspedes cujo nome corresponda ao texto informado

Cenário 2 – Busca por telefone

Given que existem hóspedes cadastrados com telefone

When informo um número de telefone no campo de busca

Then deve ser exibido o hóspede associado ao telefone informado

4\. Gestão de Reservas

4.1 Criação de reservas

História

Como recepcionista, eu quero criar reservas informando hóspede, datas de entrada e saída, quarto (ou tipo de quarto) e número de pessoas, para que eu garanta a ocupação organizada dos quartos do hotel.

Critérios de aceitação

Cenário 1 – Reserva criada com sucesso

Given que estou na tela de criação de reserva

And informei hóspede, datas e quarto ou tipo de quarto

When clico em Salvar

Then a reserva deve ser gravada no sistema com status padrão (por exemplo, “confirmada” ou “pendente”)

And deve ser exibida uma mensagem de sucesso

Cenário 2 – Dados obrigatórios ausentes

Given que estou criando uma reserva

When tento salvar sem informar hóspede ou datas

Then deve ser exibida uma mensagem indicando que hóspede e datas são obrigatórios

And a reserva não deve ser criada

4.2 Verificação de disponibilidade

História

Como recepcionista, eu quero verificar automaticamente a disponibilidade de quartos para um período informado, para que eu evite conflitos de reservas e overbooking.

Critérios de aceitação

Cenário 1 – Período disponível

Given que não existem reservas conflitantes para o período informado

When consulto a disponibilidade informando datas de entrada e saída

Then o sistema deve indicar que há quartos disponíveis e listar as opções

Cenário 2 – Período com conflito

Given que já existe reserva para o quarto nas mesmas datas

When tento criar uma nova reserva para o mesmo quarto e período

Then o sistema deve indicar que o quarto não está disponível no período selecionado

And não deve permitir gravar a reserva com conflito

4.3 Visualização de reservas em lista

História

Como equipe de recepção, eu quero visualizar uma lista de reservas com filtros por data, status (confirmada, pendente, cancelada) e hóspede, para que eu gerencie facilmente a agenda do hotel.

Critérios de aceitação

Cenário 1 – Lista de reservas

Given que existem reservas cadastradas

When acesso a tela de lista de reservas

Then deve ser exibida uma lista com hóspede, datas, quarto e status de cada reserva

Cenário 2 – Filtro por status

Given que estou na lista de reservas

When aplico filtro por status “confirmada”

Then devem ser exibidas apenas as reservas com status “confirmada”

4.4 Visualização de reservas em calendário

História

Como gerente do hotel, eu quero visualizar as reservas em um calendário (por quarto e por data), para que eu tenha uma visão clara da ocupação ao longo do tempo.

Critérios de aceitação

Cenário 1 – Exibição em calendário

Given que existem reservas cadastradas

When acesso a visualização em calendário

Then as reservas devem ser exibidas distribuídas pelas datas correspondentes

Cenário 2 – Detalhe a partir do calendário

Given que estou visualizando o calendário

When clico em uma reserva em um dia específico

Then devem ser exibidos os detalhes da reserva selecionada

4.5 Edição e cancelamento de reservas

História

Como recepcionista, eu quero editar dados de reservas (datas, quarto, hóspede) e cancelar reservas quando necessário, para que eu mantenha as informações sempre atualizadas e consistentes com a realidade.

Critérios de aceitação

Cenário 1 – Edição de reserva

Given que existe uma reserva cadastrada

When altero datas ou quarto e salvo

Then a reserva deve ser atualizada com as novas informações

And o sistema deve revalidar a disponibilidade do quarto no novo período

Cenário 2 – Cancelamento de reserva

Given que a reserva ainda não foi utilizada para check-in

When solicito o cancelamento e confirmo a ação

Then o status da reserva deve mudar para “cancelada”

And o quarto deve ser liberado para novas reservas no período

4.6 Check-in a partir da reserva

História

Como recepcionista, eu quero converter uma reserva em check-in no momento da chegada do hóspede, para que o processo de entrada seja rápido e sem retrabalho.

Critérios de aceitação

Cenário 1 – Check-in com reserva válida

Given que existe uma reserva confirmada para a data atual

When seleciono a reserva e aciono a opção de check-in

Then o status da reserva deve ser atualizado para “em estadia” (ou equivalente)

And o status do quarto deve ser atualizado para “ocupado”

4.7 Check-out e fechamento de conta

História

Como recepcionista, eu quero realizar o check-out calculando automaticamente o valor da estadia com base nas diárias e períodos, para que eu consiga encerrar a estadia de forma correta e ágil.

Critérios de aceitação

Cenário 1 – Cálculo automático da estadia

Given que o hóspede está em estadia com datas de entrada e saída definidas

When executo o processo de check-out

Then o sistema deve calcular o valor total com base na diária e no número de diárias utilizadas

Cenário 2 – Encerramento da estadia

Given que o valor total da estadia foi calculado

When confirmo o check-out

Then o status da reserva deve ser atualizado para “finalizada”

And o status do quarto deve ser atualizado para o próximo estado (por exemplo, “limpeza” ou “disponível”, conforme regra definida)

5\. Melhorias de UX / Usabilidade

5.1 Feedback visual de ações

História

Como usuário do sistema, eu quero ver mensagens claras de sucesso ou erro ao salvar, editar ou excluir dados, para que eu tenha confiança de que minhas ações foram executadas corretamente.

Critérios de aceitação

Cenário 1 – Mensagem de sucesso

Given que realizei uma operação válida (como salvar um cadastro)

When a operação é concluída com sucesso

Then deve ser exibida uma mensagem clara indicando que a ação foi realizada com sucesso

Cenário 2 – Mensagem de erro

Given que uma operação não pôde ser concluída (por exemplo, erro de validação)

When o sistema detectar o erro

Then deve ser exibida uma mensagem de erro explicando, em linguagem simples, o que deu errado e, se possível, como corrigir

5.2 Validações de formulário

História

Como usuário do sistema, eu quero ser avisado quando algum campo obrigatório estiver faltando ou inválido, para que eu possa corrigir rapidamente e evitar cadastros incompletos.

Critérios de aceitação

Cenário 1 – Indicação de campos obrigatórios

Given que estou preenchendo um formulário

When tento salvar sem preencher um campo obrigatório

Then o sistema deve destacar o campo em questão e exibir uma mensagem indicando que ele é obrigatório

Cenário 2 – Validação de formato

Given que um campo possui formato específico (por exemplo, e-mail ou documento)

When digito um valor em formato inválido

Then o sistema deve informar que o valor é inválido e impedir o salvamento até a correção

5.3 Navegação simples entre módulos

História

Como recepcionista, eu quero navegar facilmente entre Quartos, Hóspedes e Reservas a partir de um menu consistente, para que eu reduza o tempo gasto trocando de tela durante o atendimento.

Critérios de aceitação

Cenário 1 – Navegação via menu

Given que estou autenticado no sistema

When clico em Quartos, Hóspedes ou Reservas no menu

Then devo ser redirecionado para a tela correspondente, sem erros de navegação

5.4 Filtros e ordenação intuitivos

História

Como usuário do sistema, eu quero filtros e opções de ordenação claros nas listas (quartos, hóspedes, reservas), para que eu encontre rapidamente as informações mais relevantes para minha tarefa.

Critérios de aceitação

Cenário 1 – Aplicação de filtro

Given que estou em uma tela de lista com filtros disponíveis

When seleciono um filtro e aplico

Then a lista deve ser atualizada exibindo apenas os registros que atendem ao critério selecionado

Cenário 2 – Ordenação

Given que estou em uma tela de lista com opção de ordenação

When seleciono ordenar por um campo (por exemplo, data ou nome)

Then a lista deve ser reordenada de acordo com o critério escolhido

5.5 Responsividade da interface

História

Como usuário que pode acessar o sistema em telas diferentes (notebook, tablet), eu quero uma interface responsiva, para que eu consiga usar o sistema confortavelmente em diferentes dispositivos.

Critérios de aceitação

Cenário 1 – Ajuste em largura reduzida

Given que acesso o sistema em um dispositivo com tela menor

When abro qualquer tela principal do sistema

Then os elementos da interface devem se ajustar sem gerar barras de rolagem horizontais desnecessárias

And os componentes devem continuar legíveis e utilizáveis (botões, campos, textos)

Se quiser, no próximo passo posso:

Sugerir como agrupar essas histórias em épicos/tarefas gerais no Jira KAN (por exemplo, “Gestão de Quartos” com links para todas as histórias relacionadas),

Ou gerar uma versão pronta para importação em massa (CSV) para você subir direto no Jira. Qual dessas você prefere agora?

### **Casos de uso**

#### “Defina os casos de uso principais com atores, pré-condições e pós-condições.”

Abaixo estão os casos de uso principais do sistema de gestão hoteleira, alinhados às histórias que já definimos. Para cada um: nome, ator(es), pré-condições, pós-condições principais.

UC01 – Autenticar Usuário

Atores:

Usuário do sistema (Recepcionista, Gerente, Administrador, Financeiro)

Pré-condições:

O usuário está previamente cadastrado no sistema.

O sistema está em operação e a tela de login está disponível.

Pós-condições (sucesso):

O usuário é autenticado.

A sessão é criada.

O usuário é redirecionado para a tela principal, com permissões conforme o perfil.

Pós-condições (falha):

Nenhuma sessão é criada.

Uma mensagem de erro de credenciais inválidas é exibida.

UC02 – Gerenciar Quartos (Cadastrar/Editar/Visualizar)

UC02.1 – Cadastrar Quarto

Atores:

Administrador do hotel

Pré-condições:

Administrador autenticado no sistema.

Tela de “Cadastro de Quarto” acessível.

Pós-condições (sucesso):

Um novo quarto é criado com número, tipo, capacidade, status e diária.

O quarto passa a aparecer na lista de quartos.

Pós-condições (falha):

Nenhum registro novo é criado.

Mensagens de validação são exibidas indicando campos obrigatórios/ inválidos.

UC02.2 – Editar Quarto

Atores:

Administrador do hotel

Pré-condições:

Administrador autenticado.

Existe ao menos um quarto cadastrado.

Tela de detalhes/edição do quarto acessível.

Pós-condições (sucesso):

Os dados do quarto são atualizados (ex.: tipo, diária, status).

A lista e as consultas refletem as informações atualizadas.

Pós-condições (falha):

Nenhuma alteração é persistida.

O sistema informa o erro de validação ou de gravação.

UC02.3 – Consultar Lista de Quartos

Atores:

Recepcionista

Gerente do hotel

Pré-condições:

Usuário autenticado.

Existem quartos cadastrados.

Pós-condições (sucesso):

A lista de quartos é apresentada com dados básicos (número, tipo, status, diária).

Se filtros forem aplicados (ex.: status \= livre), a lista reflete o critério.

Pós-condições (falha):

Caso não haja quartos que atendam ao filtro, lista vazia é exibida com indicação apropriada.

UC03 – Gerenciar Hóspedes (Cadastrar/Editar/Buscar/Visualizar)

UC03.1 – Cadastrar Hóspede

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Tela de “Cadastro de Hóspede” acessível.

Pós-condições (sucesso):

Um novo hóspede é registrado com dados pessoais (nome, documento, contato, etc.).

O hóspede passa a poder ser selecionado em reservas e check-in.

Pós-condições (falha):

Nenhum hóspede é criado.

Mensagens de validação são exibidas para campos obrigatórios/ inválidos.

UC03.2 – Editar Hóspede

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Hóspede existente selecionado.

Pós-condições (sucesso):

Os dados do hóspede são atualizados.

Consultas futuras usam as informações já corrigidas.

Pós-condições (falha):

Nenhuma alteração é salva.

Mensagens de erro/validação são apresentadas.

UC03.3 – Buscar Hóspede

Atores:

Recepcionista

Gerente do hotel

Pré-condições:

Usuário autenticado.

Existem hóspedes cadastrados.

Tela de busca/consulta de hóspedes acessível.

Pós-condições (sucesso):

São exibidos um ou mais hóspedes que correspondam aos critérios de busca (nome, documento, telefone).

O usuário pode selecionar um hóspede para ver detalhes ou usá-lo em uma operação (reserva, check-in).

Pós-condições (falha):

Nenhum registro é retornado.

Mensagem informando que não há resultados para o critério.

UC04 – Gerenciar Reservas

UC04.1 – Criar Reserva

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Hóspede já cadastrado (ou possibilidade de cadastro rápido).

Pelo menos um quarto ou tipo de quarto configurado.

Tela de “Nova Reserva” acessível.

Pós-condições (sucesso):

Uma nova reserva é criada associando hóspede, período (check-in/check-out), quarto ou tipo de quarto, número de pessoas.

A reserva passa a aparecer na lista e no calendário de reservas.

O status inicial é definido (por exemplo, “Confirmada” ou “Pendente”).

Pós-condições (falha):

Nenhuma reserva é criada.

O sistema apresenta erros de validação (datas inválidas, ausência de hóspede, etc.).

UC04.2 – Verificar Disponibilidade de Quarto/Tipo

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Quarto(s) e/ou tipos de quarto cadastrados.

Existem (ou não) reservas para os períodos consultados.

Pós-condições (sucesso):

O sistema retorna a informação de disponibilidade para o período informado.

São listados os quartos/ tipos disponíveis quando houver.

Pós-condições (sem disponibilidade):

O sistema indica que não há disponibilidade para o período/quarto solicitado.

Nenhuma nova reserva conflitante é criada a partir dessa tentativa.

UC04.3 – Consultar Reservas (Lista)

Atores:

Recepcionista

Gerente do hotel

Pré-condições:

Usuário autenticado.

Existem reservas cadastradas.

Tela de lista de reservas acessível.

Pós-condições (sucesso):

A lista de reservas é apresentada com hóspede, datas, quarto, status.

Filtros por data, status e hóspede podem ser aplicados e afetam os resultados.

Pós-condições (falha):

Se não houver reservas ou nenhuma se encaixar no filtro, uma lista vazia é exibida com indicação adequada.

UC04.4 – Visualizar Reservas em Calendário

Atores:

Gerente do hotel

Recepcionista

Pré-condições:

Usuário autenticado.

Existem reservas cadastradas.

Visualização em calendário habilitada.

Pós-condições (sucesso):

Reservas são apresentadas em uma visão de calendário por data e, opcionalmente, por quarto.

Ao selecionar uma reserva no calendário, o usuário é levado aos detalhes da reserva.

UC04.5 – Editar Reserva

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Reserva existente selecionada.

Nova combinação de datas/quarto não deve gerar conflito.

Pós-condições (sucesso):

A reserva é atualizada com os novos dados (datas, quarto, hóspede, etc.).

A disponibilidade do quarto é recalculada e mantida consistente.

A lista e o calendário refletem as alterações.

Pós-condições (falha):

Nenhuma alteração é salva.

O sistema informa conflitos de disponibilidade ou erros de validação.

UC04.6 – Cancelar Reserva

Atores:

Recepcionista

(Opcional) Gerente do hotel

Pré-condições:

Usuário autenticado com permissão para cancelamento.

Reserva existente em estado cancelável (por ex., ainda não utilizada para check-in).

Pós-condições (sucesso):

O status da reserva é alterado para “Cancelada”.

O quarto é liberado no período correspondente (para futuras reservas).

Pós-condições (falha):

Status da reserva é mantido.

Mensagem é exibida explicando por que não é possível cancelar (ex.: já finalizada).

UC05 – Check-in

Atores:

Recepcionista

Pré-condições:

Recepcionista autenticado.

Uma reserva existente para a data atual ou um hóspede presente para check-in direto.

Quarto associado disponível para a estadia.

Pós-condições (sucesso):

A reserva tem status atualizado para algo como “Em estadia”.

O status do quarto é alterado para “Ocupado”.

O hóspede é registrado como “hóspede atual” do quarto.

Pós-condições (falha):

Nenhuma alteração de status ocorre.

Mensagem indica o motivo da falha (ex.: quarto não disponível, reserva inexistente, data inválida).

UC06 – Check-out e Fechamento de Conta

Atores:

Recepcionista

(Opcional) Financeiro

Pré-condições:

Usuário autenticado.

Hóspede em estadia (check-in realizado).

Datas de entrada/saída disponíveis para cálculo.

Valores de diária (e eventuais adicionais) configurados.

Pós-condições (sucesso):

O valor total da estadia é calculado com base nas diárias e período efetivamente utilizado.

O status da reserva é alterado para “Finalizada”.

O status do quarto é atualizado para o estado pós-estadia (por exemplo, “Limpeza” ou “Disponível”, conforme regra definida).

(Opcional) O registro financeiro da cobrança é criado/atualizado.

Pós-condições (falha):

Nenhum status é alterado.

Nenhum lançamento financeiro é registrado.

Uma mensagem explica o erro (dados ausentes, problema de cálculo, etc.).

UC07 – Gerenciar Tipos de Quarto e Tarifas

Atores:

Gerente do hotel

Administrador do sistema

Pré-condições:

Usuário autenticado com permissão de gestão de configuração.

Tela de “Tipos de Quarto / Tarifas” acessível.

Pós-condições (sucesso):

Tipos de quarto (standard, luxo, suíte, etc.) são criados ou atualizados com diárias padrão.

As novas configurações passam a ser usadas como valor padrão em novas reservas.

Pós-condições (falha):

Nenhuma configuração é alterada.

Sistema informa erros de validação (por exemplo, valor de diária inválido).

UC08 – Exibir Feedback de Ações e Validações de Formulários

Atores:

Qualquer usuário autenticado (Recepcionista, Gerente, Administrador, Financeiro)

Pré-condições:

Usuário autenticado.

Usuário está executando operações CRUD (criar, editar, excluir, salvar).

Pós-condições (sucesso):

Para cada operação concluída com sucesso, uma mensagem de confirmação é exibida.

A interface reflete imediatamente a alteração (registro novo, editado ou removido).

Pós-condições (falha):

Nenhuma operação inválida é persistida.

Mensagens de erro claras são exibidas e campos inválidos são destacados.

Se você quiser, no próximo passo posso:

Transformar esses casos de uso em um modelo de diagrama de casos de uso UML (texto \+ descrição das relações), ou

Montar um template de documento de especificação (SRS) já com seções preenchidas para você colar no Confluence ou no Word.

Qual desses te ajuda mais agora?

### **Rastreabilidade inicial**

#### “Vincule requisitos às histórias de usuário correspondentes.”

Vou fazer o vínculo em dois níveis:

Requisitos funcionais principais → Tarefas “macro” do KAN (KAN-1, KAN-3, KAN-4, KAN-5, KAN-6)

Requisitos mais específicos → Subtasks que você já criou (KAN-2, KAN-7, KAN-13 a KAN-23)

Assim você tem rastreabilidade clara entre requisito → história de usuário (já definidas) → item do Jira.

URL do projeto / lista de issues:

Minha equipe | Lista

Lista completa em: 

18 Issues

1\. Arquitetura / UI Geral

Requisito R1 – Definir arquitetura do sistema web de reservas

História de usuário (já criada):

Como arquiteto de software, eu quero definir a arquitetura da aplicação (camadas, módulos e integrações), para que o sistema seja escalável, fácil de manter e permita evolução futura dos módulos de quartos, hóspedes e reservas.

Vincular a:

KAN-1 – Arquitetura/UI (Tarefa macro)

KAN-1: Arquitetura/UI

A fazer

KAN-2 – Definir arquitetura do sistema de reservas (web) (Subtask)

KAN-2: Definir arquitetura do sistema de reservas (web)

A fazer

Sugestão de uso no Jira:

Colocar o texto da história de usuário na descrição de KAN-2.

Usar KAN-1 como guarda-chuva para demais histórias de UI que criarmos.

Requisito R2 – Ter um layout principal com menu lateral e área de conteúdo

História:

Como usuário do sistema (recepcionista/gerente), eu quero um layout principal com menu lateral e área de conteúdo bem organizada, para que eu encontre rapidamente as funcionalidades de quartos, hóspedes e reservas sem me perder na interface.

Vincular a:

KAN-1 – Arquitetura/UI (Tarefa macro)

Requisito R3 – Definir guideline visual e paleta de cores

História implícita:

Como usuário do sistema, eu quero uma identidade visual consistente (cores, fontes, componentes), para que eu tenha uma experiência agradável e reconhecível ao usar o sistema.

Vincular a:

KAN-1 – Arquitetura/UI

KAN-7 – Definir guideline visual (UI) e paleta de cores (verde/azul)

KAN-7: Definir guideline visual (UI) e paleta de cores (verde/azul)

A fazer

Aqui, KAN-7 é praticamente a história/hospitalidade de design. Você pode só ajustar o resumo se quiser seguir o formato “Como… eu quero…”.

2\. Gestão de Quartos

Requisito R4 – Manter cadastro de quartos (dados básicos)

História principal:

Como administrador do hotel, eu quero cadastrar e editar quartos com informações como número, tipo, capacidade, status e diária, para que eu mantenha um inventário atualizado e confiável dos quartos disponíveis.

Vincular a:

KAN-3 – Gestão de Quartos (Tarefa macro)

KAN-3: Gestão de Quartos

A fazer

KAN-13 – Implementar modelo de dados de Quartos e Camas

KAN-13: Implementar modelo de dados de Quartos e Camas 

A fazer

KAN-14 – Tela de cadastro/edição de Quartos

KAN-14: Tela de cadastro/edição de Quartos

A fazer

Sugestão:

Descrição de KAN-13 → foca no requisito de dados (campos, relacionamentos).

Descrição de KAN-14 → coloca a história de usuário de cadastro/edição de quarto \+ critérios Given-When-Then.

Requisito R5 – Listar quartos com filtros de status

História:

Como recepcionista, eu quero visualizar uma lista de quartos com filtros por status (livre, ocupado, reservado, manutenção), para que eu identifique rapidamente quais quartos posso alocar para novos hóspedes.

Vincular a:

KAN-3 – Gestão de Quartos

KAN-15 – Tela de listagem de Quartos

KAN-15: Tela de listagem de Quartos

A fazer

Requisito R6 – Ver detalhes de um quarto

História:

Como recepcionista, eu quero abrir a tela de detalhes de um quarto com todas as informações relevantes, para que eu possa tomar decisões informadas ao atribuí-lo a um hóspede.

Vincular a:

KAN-3 – Gestão de Quartos

KAN-14 – Tela de cadastro/edição de Quartos (usando uma aba ou seção de detalhes)

3\. Gestão de Hóspedes

Requisito R7 – Cadastrar e editar hóspedes

História:

Como recepcionista, eu quero cadastrar hóspedes com dados pessoais (nome, documento, contato, endereço), para que o hotel mantenha um registro organizado para check-in, cobrança e obrigações legais.

Vincular a:

KAN-4 – Gestão de Hóspedes (Tarefa macro)

KAN-4: Gestão de Hóspedes

A fazer

KAN-16 – Implementar modelo de dados de Hóspede

KAN-16: Implementar modelo de dados de Hóspede

A fazer

KAN-17 – Tela de cadastro/edição de Hóspede

KAN-17: Tela de cadastro/edição de Hóspede

A fazer

Requisito R8 – Listar e buscar hóspedes

Histórias:

Como recepcionista, eu quero editar dados de hóspedes e consultar rapidamente o histórico pelo nome ou documento…

Como recepcionista, eu quero buscar hóspedes por nome, documento ou telefone…

Vincular a:

KAN-4 – Gestão de Hóspedes

KAN-18 – Tela de listagem de Hóspedes

KAN-18: Tela de listagem de Hóspedes

A fazer

Na descrição de KAN-18, você pode incluir:

História de busca (nome/documento/telefone).

Critérios Given-When-Then de lista \+ filtro/pesquisa.

4\. Gestão de Reservas

Requisito R9 – Modelo de dados de Reserva

História implícita:

Como desenvolvedor/PO, eu quero um modelo de dados de reserva com hóspede, quarto, datas e status, para que o sistema consiga registrar e consultar reservas de forma consistente.

Vincular a:

KAN-5 – Gestão de Reservas (Tarefa macro)

KAN-5: Gestão de Reservas

A fazer

KAN-19 – Implementar modelo de dados de Reserva e regras básicas

KAN-19: Implementar modelo de dados de Reserva e regras básicas

A fazer

Requisito R10 – Tela de criação/edição de Reserva

Histórias:

Como recepcionista, eu quero criar reservas informando hóspede, datas, quarto (ou tipo) e número de pessoas…

Como recepcionista, eu quero editar dados de reservas (datas, quarto, hóspede) e cancelar reservas quando necessário…

Vincular a:

KAN-5 – Gestão de Reservas

KAN-21 – Tela de criação/edição de Reserva

KAN-21: Tela de criação/edição de Reserva

A fazer

Requisito R11 – Listagem de Quartos voltada para Reservas

História:

Como recepcionista, eu quero visualizar a disponibilidade de quartos para realizar reservas.

Vincular a:

KAN-5 – Gestão de Reservas

KAN-20 – Tela de listagem de Quartos para Gestão de Reservas

KAN-20: Tela de listagem de Quartos para Gestão de Reservas

A fazer

Requisito R12 – Tela principal de Gestão de Reservas

História (lista de reservas):

Como equipe de recepção, eu quero visualizar uma lista de reservas com filtros por data, status e hóspede…

Vincular a:

KAN-5 – Gestão de Reservas

KAN-21 – Tela de criação/edição de Reserva (pode incorporar navegação de lista \+ formulário)

Se depois você criar uma issue “Lista de Reservas”, ela também será ligada a esse requisito.

Requisito R13 – Verificar disponibilidade

História:

Como recepcionista, eu quero verificar automaticamente a disponibilidade de quartos para um período informado, para que eu evite conflitos de reservas e overbooking.

Vincular a:

KAN-5 – Gestão de Reservas

KAN-19 – Implementar modelo de dados de Reserva e regras básicas (onde entram as regras de conflito/overbooking)

5\. Integração, Navegação e UX Geral

Requisito R14 – Navegar facilmente entre módulos (Quartos, Hóspedes, Reservas)

História:

Como recepcionista, eu quero navegar facilmente entre Quartos, Hóspedes e Reservas a partir de um menu consistente, para que eu reduza o tempo gasto trocando de tela durante o atendimento.

Vincular a:

KAN-6 – Integração, Navegação e UX Geral (Tarefa macro)

KAN-6: Integração, Navegação e UX Geral

A fazer

KAN-22 – Implementar navegação entre módulos

KAN-22: Implementar navegação entre módulos

A fazer

Requisito R15 – Melhorias de UX e feedback ao usuário

Histórias:

Como usuário do sistema, eu quero ver mensagens claras de sucesso ou erro…

Como usuário, eu quero ser avisado quando algum campo obrigatório estiver faltando ou inválido…

Como usuário, eu quero filtros e ordenação intuitivos nas listas…

Vincular a:

KAN-6 – Integração, Navegação e UX Geral

KAN-23 – Melhorias de UX e feedback ao usuário

KAN-23: Melhorias de UX e feedback ao usuário

A fazer

Requisito R16 – Integração entre telas (usar dados de hóspedes/quartos em reservas)

História implícita:

Como recepcionista, eu quero que, ao criar uma reserva, eu consiga buscar hóspedes e escolher quartos já cadastrados, para não precisar digitar tudo do zero.

Vincular a:

KAN-6 – Integração, Navegação e UX Geral

KAN-19 – Modelo de dados de Reserva (lado de backend)

KAN-20 / KAN-21 / KAN-18 / KAN-15 (lado de UI reutilizada / seleção de dados)

6\. Como registrar esses vínculos no Jira

Como você não tem tipo de issue “Requisito” ainda, uma forma prática de garantir rastreabilidade é:

Criar uma página de requisitos (por exemplo, no Confluence) ou um documento simples e numerar: R1, R2, R3…

Em cada issue do Jira (KAN-1, KAN-3, KAN-4, KAN-5, KAN-6, KAN-13… KAN-23), adicionar na descrição ou em um campo customizado algo como:

Requisitos atendidos: R3, R4, R5

Opcional: criar um rótulo/label por requisito (ex.: req-R4-quartos-cadastro) e aplicar nas issues relacionadas.

Se você quiser, no próximo passo posso te devolver uma tabelinha em formato CSV:

com colunas Requisito;IssueKey;IssueResumo,

pronta para você importar ou usar como base de documentação de rastreabilidade. Quer que eu gere esse CSV?
