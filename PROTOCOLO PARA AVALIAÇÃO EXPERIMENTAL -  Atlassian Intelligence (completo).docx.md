**PROTOCOLO PARA AVALIAÇÃO EXPERIMENTAL**

**ANÁLISE COMPARATIVA DE FERRAMENTAS DE IA BASEADAS EM LLMs PARA ENGENHARIA DE SOFTWARE**

**TEMPLATE PARA DOCUMENTAÇÃO DE RESULTADOS**

**Instruções gerais:**

De acordo com o protocolo definido, ferramentas podem ser consideradas “Generalistas” (cobrem todo o SDLC) ou ferramentas "Especializadas" (ex: focadas apenas em etapas específicas do SDLC, como construção e/ou testes). O avaliador deve considerar as seguintes premissas para a avaliação:

* Os testes padronizados devem ser realizados para cada uma das etapas apoiadas pela ferramenta, em conformidade com a primeira parte da avaliação realizada (Google Forms).  
* O avaliador deve sinalizar as etapas fora do escopo funcional da ferramenta, registrando o caso de teste em questão como "N/A \- Fora do Escopo", não havendo a necessidade de executá-lo.  
* Deve-se respeitar a dependência de artefatos, caso sejam necessários para a realização dos testes.

Os tipos de testes a serem realizados dependerão do tipo de prompt ou input aceito por cada ferramenta.

* Os prompts disponibilizados neste template para cada caso de teste devem ser utilizados sem qualquer tipo de alteração, visando a padronização das avaliações (conforme Anexos II e III do protocolo).  
* Caso seja utilizado outro tipo de input que não seja um prompt textual este deve ser documentado juntamente com o resultado obtido (output).   
* Todos os outputs devem ser documentados na íntegra para posterior análise e síntese da avaliação. 

Serão adotados como padrão os seguintes tipos de input para as ferramentas:

* **Chat direto** (textual): a ferramenta aceita prompts explícitos (em texto) como entrada para o trabalho da IA (seguir os casos de teste padrão);  
* **Contexto** (ou prompt implícito): a ferramenta utiliza de forma implícita e/ou autônoma o contexto do IDE (ou ambiente em questão) como entrada para o trabalho da IA (alinhamento caso a caso, buscando atingir os objetivos dos testes definidos no protocolo);  
* **Arquivos** (ou artefatos): a ferramenta precisa que o usuário realize a inserção de arquivos (artefatos referentes a uma etapa anterior, por exemplo) para realizar o trabalho baseado em IA (alinhamento caso a caso, buscando atingir os objetivos dos testes definidos no protocolo).

A avaliação humana (realizada pelo integrante responsável) é imprescindível para todos os casos de teste. 

Casos omissos devem ser alinhados com a gestão do Squad e documentados conforme orientação.

**Etapa 1 – Engenharia de Requisitos** 

(  x  ) Dentro do escopo                 (     ) Fora do escopo

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Solicite explicitamente:

1. Elicitação e estruturação de requisitos

   * “Liste requisitos funcionais (RF) e não funcionais (RNF) para este sistema.”

   * “Classifique-os por prioridade (MoSCoW).”

2. Histórias de usuário

   * “Crie as histórias de usuário no formato padrão (Como \[tipo de usuário\], eu quero…, para que…).”

   * “Inclua critérios de aceitação no formato padrão (Given-When-Then).”

3. Casos de uso

   * “Defina os casos de uso principais com atores, pré-condições e pós-condições.”

4. Rastreabilidade inicial

   * “Vincule requisitos às histórias de usuário correspondentes.”

**Etapa 2 – Arquitetura e Projeto de Software**

(     ) Dentro do escopo                 (  x  ) Fora do escopo

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Solicite:

1. Arquitetura

   * “Proponha uma arquitetura para este sistema (ex.: camadas, microserviços, ou monolito modular).”

   * “Justifique a escolha considerando desempenho, escalabilidade e manutenção.”

2. Decisões arquiteturais

   * “Documente as decisões arquiteturais críticas do sistema.”

3. Modelagem

   * “Gere o diagrama de componentes (texto ou UML).”

   * “Gere o diagrama de classes principal (Quarto, Hóspede, Reserva.).”

4. Padrões de projeto

   * “Sugira padrões de projeto aplicáveis ao sistema e justifique.”

**Etapa 3 – Construção (Geração de Código)**

(     ) Dentro do escopo                 (  x  ) Fora do escopo

**Pré-condição:** definir uma stack (se permitido pela ferramenta). Se não for permitido, gerar na linguagem padrão suportada pela ferramenta. **Realizar a os testes com duas stacks diferentes para efeito de comparação:** 

* **Stack 1: TypeScript \+ Node.js \+ React;**  
* **Stack 2: Java \+ Spring.**

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta). Responda para a Stack 1 e para a Stack 2 (se permitido pela ferramenta):

Solicite:

1. Modelo de dados

   * “Implemente as classes para: Quarto, Hóspede e Reserva.”

2. Módulo de Gestão de Quartos (exemplo de escopo)

   * “Considerando o módulo de Gestão de Quartos, implemente:

     * Cadastro de quarto

     * Edição de quarto

     * Listagem de quartos com:

       * Número

       * Tipo

       * Preço por hora

       * Disponibilidade (Ocupado, Livre, Manutenção, Limpeza)

     * Suporte a múltiplas camas por quarto (Solteiro, King, Queen).”

3. Boas práticas

   * “Garanta princípios SOLID e clean code.”

   * “Explique decisões de implementação em comentários.”

     

     

     

     

4. Avaliação baseada em métricas (realizada pelo avaliador sem o uso da ferramenta, baseado nos resultados obtidos). Responda para a Stack 1 e para a Stack 2 (se permitido pela ferramenta):

   * Qual o percentual de requisitos atendidos em relação ao teste realizado? Aplicar a seguinte formula:

     ![TextoO conteúdo gerado por IA pode estar incorreto.][image1]

     * Número total de requisitos:

     * Número total de requisitos cobertos pelo teste:

     * Resultado final (%): 

     

   * O código atende aos critérios de aceitação definidos anteriormente?

   * Qual a quantidade de linhas de código geradas (LOC)?

     * incluir apenas código executável;

     * excluir comentários;

     * excluir linhas em branco.

       

   * Qual o número de funções/métodos?

     * contar apenas definições explícitas.

       

   * Qual o número de interações necessárias (número de prompts para atingir o resultado correto)? Conta como **uma interação**: qualquer novo prompt textual enviado pelo avaliador **com intenção de modificar o resultado**.

     * Prompt inicial (definido e padronizado pelo protocolo): 1ª interação;

     * Refinamento (documentar): 2ª interação;

     * Correção (documentar): 3ª interação.

     * Documentar novas interações se necessário.

**Etapa 4 – Testes de Software**

(     ) Dentro do escopo                 (  x  ) Fora do escopo

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Solicite:

1. Testes unitários

   * “Crie testes unitários para:

     * Cadastro de quarto

     * Edição de quarto”

2. Testes de integração

   * “Proponha testes de integração para fluxo:  
     Cadastro de hóspede → Criação de reserva → Atualização de disponibilidade do quarto.”

3. Cobertura e justificativa

   * “Explique a estratégia de cobertura de testes definida.”

**Etapa 5 – Operações**

(     ) Dentro do escopo                 (  x  ) Fora do escopo

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Solicite:

1. Plano de implantação

   * “Proponha um pipeline de deploy para o sistema em questão (ex.: Docker \+ CI/CD).”

2. Monitoramento

   * “Defina métricas e logs a serem monitorados (disponibilidade, latência, erros).”

3. Gestão de incidentes

   * “Descreva um procedimento de resposta a falhas (runbook).”

**Etapa 6 – Manutenção**

(     ) Dentro do escopo                 (  x  ) Fora do escopo

Prompts/entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Forneça um trecho de código “problemático” do módulo de quartos e solicite:

1. “Identifique problemas de qualidade no código e sugira refatorações, se necessário.”

2. “Forneça uma versão melhorada do código.”

3. “Explique como isso reduz dívida técnica.”

**Entrada 7 – Gerenciamento**

(  x  ) Dentro do escopo                 (    ) Fora do escopo

Prompts/Entradas para a ferramenta, além do cenário de aplicação (documente se houver uso de contexto ou arquivos pela ferramenta):

Solicite:

1. Plano de projeto

   * “Proponha um cronograma baseado em sprints.”

   * “Estime esforço em story points ou horas.”

2. Gestão de riscos

   * “Liste os riscos técnicos e gerenciais com planos de mitigação.”

3. Governança e qualidade

   * “Defina KPIs e critérios de qualidade para o projeto.”

# Extração

## **Contexto:** 

Considere o seguinte contexto e crie tarefas para serem adicionadas como cards no quadro: “Você é um Engenheiro de Software e deve considerar o seguinte domínio de aplicação: Um sistema de reserva, para um único hotel. Este sistema é composto por alguns módulos e regras de negócios, a saber: • Gestão de quartos: o Cadastro de quarto, com os campos sendo: ▪ Número do quarto (Input) ▪ Capacidade (Input) ▪ Tipo do quarto (Básico, Moderno, Luxo) (Select) ▪ Preço por diária (Input) ▪ Há Frigobar (Checkbox) ▪ Há café da manhã incluso (Checkbox) ▪ Há Ar-condicionado (Checkbox) ▪ Há TV (Checkbox) ▪ Uma sessão "Camas" sendo: ▪ Tipo de cama (Solteiro, Casal King, Casal Queen) (Select) o Lista dos quartos, com as colunas: ▪ Número do quarto (Número) ▪ Tipo do quarto (Texto) ▪ Preço por diária (Número) ▪ Disponibilidade (Ocupado, Livre, Manutenção e Limpeza) (Select) ▪ Botão para editar o quarto (ícone de lápis) (Botão) • Gestão de Hospedes: o Cadastro de hóspede, sendo os campos: ▪ Nome (Input) ▪ Sobrenome (Input) ▪ CPF (Input) ▪ Email (Input) o Lista de hóspedes, contendo todos os 3 campos, exceto e-mail. • Gestão de reserva: o Lista de quartos, sendo: ▪ Número do quarto (Número) ▪ Tipo do quarto (Texto) ▪ Nome do Hospede (Texto) ▪ Disponibilidade (Ocupado, Livre, Manutenção e Limpeza) (Chip) ▪ Botão para editar a reserva (ícone de lápis) (Botão) O sistema terá interface web, com paleta de cores verde e azul e utilizará componentes modernos.”

Segue uma sugestão de tarefas para você criar como cards no quadro do projeto KAN, já organizadas por tema, no formato que você costuma usar (tarefas gerais \+ subtarefas mais concretas).

1\. Arquitetura / UI

Tarefa: Definir arquitetura do sistema de reservas (web)

Subtarefas:

Escolher stack front-end (framework, biblioteca de componentes modernos, gerenciamento de estado)

Definir arquitetura de pastas e camadas (components, pages, services, models)

Definir padrão de comunicação com backend (REST, DTOs, tratamento de erros)

Definir modelo de dados principal (Quarto, Cama, Hóspede, Reserva, Status de disponibilidade)

Documentar decisões de arquitetura em um documento de referência

Tarefa: Definir guideline visual (UI) e paleta de cores (verde/azul)

Subtarefas:

Definir paleta de cores primária e secundária (variações de verde e azul)

Definir tokens de design (cores, tipografia, espaçamentos, bordas)

Escolher biblioteca de componentes modernos (ex.: Material, Chakra, etc.)

Criar layout base (header, menu de navegação, conteúdo principal)

Definir componentes padrão (botões, inputs, selects, checkboxes, chips, tabelas)

2\. Gestão de Quartos

Tarefa: Implementar modelo de dados de Quartos e Camas

Subtarefas:

Criar entidade/modelo Quarto com campos:

númeroDoQuarto

capacidade

tipoDoQuarto (Básico, Moderno, Luxo)

precoPorDiaria

haFrigobar

haCafeDaManha

haArCondicionado

haTv

Criar entidade/modelo Cama associada ao quarto:

tipoDeCama (Solteiro, Casal King, Casal Queen)

Definir relação Quarto–Camas (1:N)

Implementar validações de domínio (ex.: capacidade \> 0, preço \> 0\)

Tarefa: Tela de cadastro/edição de Quartos

Subtarefas:

Criar formulário de cadastro de quarto com campos:

Número do quarto (Input)

Capacidade (Input)

Tipo do quarto (Select: Básico, Moderno, Luxo)

Preço por diária (Input numérico/moeda)

Há Frigobar (Checkbox)

Há café da manhã incluso (Checkbox)

Há Ar-condicionado (Checkbox)

Há TV (Checkbox)

Implementar sessão “Camas”:

Lista de camas do quarto

Campo “Tipo de cama” (Select: Solteiro, Casal King, Casal Queen)

Ações para adicionar/remover camas

Implementar validações de formulário e mensagens de erro

Conectar formulário com backend para criar/atualizar quartos

Tarefa: Tela de listagem de Quartos

Subtarefas:

Criar tabela de listagem de quartos com colunas:

Número do quarto (Número)

Tipo do quarto (Texto)

Preço por diária (Número)

Disponibilidade (Select: Ocupado, Livre, Manutenção, Limpeza)

Incluir botão/ícone de lápis para editar quarto em cada linha

Implementar paginação e/ou filtros básicos (por tipo, disponibilidade)

Conectar listagem com backend (carregar, atualizar status de disponibilidade)

3\. Gestão de Hóspedes

Tarefa: Implementar modelo de dados de Hóspede

Subtarefas:

Criar entidade/modelo Hospede com campos:

nome

sobrenome

cpf

email

Implementar validações de domínio (formato de CPF, e-mail, campos obrigatórios)

Definir regras de unicidade (ex.: CPF único no sistema)

Tarefa: Tela de cadastro/edição de Hóspede

Subtarefas:

Criar formulário de cadastro de hóspede com campos:

Nome (Input)

Sobrenome (Input)

CPF (Input)

Email (Input)

Implementar validações de formulário (obrigatoriedade, formatos)

Implementar feedback de sucesso/erro (toasts, mensagens)

Conectar formulário com backend para criar/atualizar hóspedes

Tarefa: Tela de listagem de Hóspedes

Subtarefas:

Criar tabela de listagem de hóspedes com colunas:

Nome

Sobrenome

CPF

Implementar busca por nome/CPF

Incluir ação para editar hóspede (ícone de lápis ou ação na linha)

Conectar listagem com backend (carregar e atualizar dados)

4\. Gestão de Reservas

Tarefa: Implementar modelo de dados de Reserva e regras básicas

Subtarefas:

Criar entidade/modelo Reserva com associações:

Quarto

Hóspede

Datas de check-in e check-out (se for escopo atual)

Status da reserva (por definir: ativa, concluída, cancelada, etc. – se aplicável)

Implementar regra de disponibilidade:

Não permitir dois hóspedes diferentes em um mesmo quarto se o quarto estiver “Ocupado” no período

Definir integração entre status da reserva e disponibilidade do quarto (Livre/Ocupado/Manutenção/Limpeza)

Tarefa: Tela de listagem de Quartos para Gestão de Reservas

Subtarefas:

Criar tabela na área de “Gestão de reserva” com colunas:

Número do quarto (Número)

Tipo do quarto (Texto)

Nome do hóspede (Texto – vazio se quarto livre)

Disponibilidade (Chip: Ocupado, Livre, Manutenção, Limpeza)

Definir estilo visual do chip de disponibilidade (cores/estados)

Adicionar botão/ícone de lápis para editar reserva do quarto

Conectar listagem com backend (buscar reserva atual por quarto)

Tarefa: Tela de criação/edição de Reserva

(Mesmo que não esteja 100% detalhada no texto, é necessária para o fluxo)

Subtarefas:

Permitir selecionar:

Quarto (a partir da lista de quartos livres)

Hóspede (selecionar de lista ou buscar por nome/CPF)

(Opcional/estendido) Campos de:

Data de check-in

Data de check-out

Ao salvar:

Atualizar disponibilidade do quarto para “Ocupado”

Persistir vínculo entre quarto e hóspede

Implementar validações (quarto não pode estar ocupado ao criar reserva)

5\. Integração, Navegação e UX Geral

Tarefa: Implementar navegação entre módulos

Subtarefas:

Tarefa: Melhorias de UX e feedback ao usuário

Subtarefas:

Implementar estados de carregamento (loading) nas listas

Implementar mensagens de erro genéricas (falhas de rede, validação no servidor)

Implementar confirmações para ações críticas (ex.: cancelamento de reserva, alteração de disponibilidade)

Garantir responsividade básica das telas principais

Se quiser, no próximo passo posso transformar essas tarefas em descrições prontas no formato específico de cards do seu Jira (por exemplo, com título, descrição e critérios de aceite em Gherkin para você só copiar e colar). Quer focar primeiro em qual módulo: Quartos, Hóspedes ou Reservas?

**![][image2]**

**![][image3]**

**![][image4]**

Conforme sugerido pela IA, foram criados os cards e subtarefas de acordo com o contexto do sistema sujerido. Para cada subtarefa, foi adicionada uma descrição conforme o output obtido.

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

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>