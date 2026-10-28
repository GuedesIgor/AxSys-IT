# 10 · Matriz de funcionalidades

> Catálogo consolidado de tudo que os 10 sistemas estudados oferecem, mais as exigências brasileiras. Cada linha mostra quem tem a função, e se o protótipo já a cobre.

**Leitura da matriz:** uma marca (●) indica que a função foi **confirmada nas fontes lidas** para aquele sistema. Célula vazia significa "não confirmado nas fontes", e não "o sistema não tem". Veja os limites do estudo em [09 · Benchmark](09-benchmark-concorrentes.md).

## Resumo de cobertura

| Situação | Funções | % |
|---|---:|---:|
| Feito (implementado no protótipo) | 62 | 57% |
| Parcial ou simulado | 24 | 22% |
| Pendente (fora do protótipo, com motivo) | 23 | 21% |
| **Total catalogado** | **109** | |

Parcial significa que a tela e o fluxo existem para validar, mas o efeito real (câmera, envio de e-mail, conector, arquivo oficial) só acontece no app de verdade.

## Legenda dos sistemas

| Sigla | Sistema |
|---|---|
| UKG | UKG Workforce Management (antigo Kronos) |
| DEP | Deputy |
| CON | Connecteam |
| CLK | Clockify |
| JIB | Jibble |
| HOM | Homebase |
| WIW | When I Work |
| RIP | Rippling |
| QBT | QuickBooks Time |
| BUD | Buddy Punch |
| PTM | Pontomais (referência Brasil) |
| BR | Portaria 671 do MTE (exigência legal) |

## A · Registro de ponto

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| A01 | Registro pelo navegador (web) | ● | ● |  |  | ● |  |  |  |  |  |  |  | Feito | Tela "Registrar ponto" |
| A02 | Funcionar em celular e em qualquer navegador | ● | ● | ● |  | ● |  |  |  |  |  | ● |  | Feito | Web responsivo; no app real, PWA instalável (decisão V5-04) |
| A19 | Aplicativo nativo para celular | ● | ● | ● |  | ● |  |  |  |  |  | ● |  | Pendente | Decisão V5-05: só se uma função exigir |
| A03 | Quiosque compartilhado com matrícula e PIN | ● |  | ● | ● | ● |  |  |  |  |  | ● |  | Feito | Modo quiosque na tela de login |
| A04 | Validação facial com prova de vida antes de cada batida, obrigatória | ● | ● | ● |  | ● |  |  |  |  |  | ● |  | Feito | Desafios aleatórios, 3 tentativas, bloqueio e auditoria. Câmera simulada. Depende de parecer jurídico (Q-13) |
| A04c | Batida sem validação facial: pendente de aprovação do gestor, com justificativas dos dois lados |  |  | ● |  |  |  |  |  |  |  | ● |  | Feito | Reaproveita o fluxo do ponto sem localização. Entra no espelho marcada s/f |
| A04d | Método alternativo de validação autorizado pelo RH (PIN), sem registrar o motivo | ● |  |  |  |  |  |  |  |  |  | ● |  | Feito | Revisão a cada 180 dias. Batida marcada alt |
| A04b | Cadastro facial com prova de vida obrigatório para criar usuário | ● |  | ● |  | ● |  |  |  |  |  | ● |  | Feito | Sem rosto cadastrado não há cadastro nem batida. Câmera simulada |
| A05 | QR Code pessoal do colaborador |  |  |  |  |  |  |  |  |  |  | ● |  | Parcial | QR ilustrativo em Meu perfil; leitura real no app |
| A06 | Registro por WhatsApp |  |  |  |  |  |  |  |  |  |  | ● |  | Parcial | Método e integração simulados em Configurações |
| A07 | Registro por Slack ou Teams |  |  |  |  | ● |  |  |  |  |  |  |  | Parcial | Método e integração simulados |
| A08 | Registro offline com sincronização |  |  |  |  |  |  |  |  |  |  | ● | ● | Feito | Simulador "Sem internet" e botão Sincronizar |
| A09 | Relógio físico e biometria digital (REP) | ● |  |  |  |  |  |  |  |  |  |  | ● | Parcial | Integração "REP-C / leitor biométrico" simulada |
| A10 | Extensão de navegador ou desktop |  |  |  |  | ● |  |  |  |  |  |  |  | Pendente | Fora do escopo da primeira versão |
| A11 | Registro por telefone (URA) | ● |  |  |  |  |  |  |  |  |  |  |  | Pendente | Fora do escopo |
| A12 | Comprovante numerado de cada batida |  |  |  |  |  |  |  |  |  |  |  | ● | Feito | Comprovante com número, hora, local e origem |
| A13 | Hora legal sincronizada e relógio digital |  |  |  |  |  |  |  |  |  |  |  | ● | Parcial | Indicado na tela; sincronismo real é do servidor |
| A14 | Lançamento manual sujeito a aprovação |  | ● |  | ● |  |  |  |  |  |  |  |  | Feito | Ajustes de ponto com justificativa |
| A15 | Projeto ou atividade por registro |  |  |  | ● |  |  |  |  |  |  |  |  | Feito | Seleção na entrada e relatório por projeto |
| A16 | Cronômetro de tarefas durante o dia |  |  |  | ● |  |  |  |  |  |  |  |  | Pendente | Foco em jornada, não em tarefa |
| A17 | Limitar entrada antecipada | ● |  | ● |  |  |  |  |  |  |  |  |  | Feito | Janela de entrada em Configurações |
| A18 | Saída automática no fim do turno |  |  | ● |  |  |  |  |  |  |  |  |  | Parcial | Configuração; efeito completo no app |

## B · Localização e antifraude

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| B01 | Localização do aparelho obrigatória com mapa |  | ● |  |  |  |  |  |  | ● | ● |  |  | Feito | Pedido da AxSys. Bloqueia a batida sem permissão |
| B02 | Cerca virtual com raio ajustável | ● |  | ● |  | ● |  |  |  |  | ● |  |  | Feito | Raio em Configurações, uma cerca por unidade |
| B03 | Tratar batida fora da cerca (permitir, justificar, bloquear) |  |  | ● |  |  |  |  |  |  |  |  |  | Feito | Três modos configuráveis |
| B04 | Várias unidades, cada uma com sua cerca |  | ● |  |  |  |  |  |  |  |  |  |  | Feito | Organização > Unidades |
| B05 | Aviso quando a batida vem de outro aparelho |  |  | ● |  |  |  |  |  |  |  |  |  | Feito | Alerta e painel de exceções |
| B06 | Prevenção de batida por colega (selfie, aparelho e local) |  |  | ● |  |  |  |  |  |  |  | ● |  | Feito | Combinação de selfie, aparelho e local |
| B07 | Ver onde cada batida aconteceu |  | ● |  |  |  |  |  |  | ● | ● |  |  | Feito | Botão Local no espelho e relatório Localização |
| B10 | Ponto sem localização com aprovação justificada do gestor |  |  |  |  |  |  |  |  |  |  |  |  | Feito | Pedido da AxSys (RN-19): pendente, não conta até aprovar, justificativas dos dois lados |
| B08 | Entrada e saída automática ao cruzar a cerca |  |  |  |  | ● |  |  |  |  |  |  |  | Pendente | Exige app nativo e rastreio em segundo plano (LGPD) |
| B09 | Rastreamento contínuo de GPS |  |  |  |  |  |  |  |  |  | ● |  |  | Pendente | Decisão de produto: coletar só na batida |

## C · Jornada e regras

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| C01 | Vários modelos de jornada | ● |  |  |  | ● |  |  |  |  |  |  |  | Feito | Jornadas com horário, horas e intervalo |
| C02 | Criar e editar jornadas | ● |  |  |  |  |  |  |  |  |  |  |  | Parcial | Criação pronta; edição no app |
| C03 | Tolerância de atraso e saída | ● |  | ● |  |  |  |  |  |  |  |  |  | Feito | Configurável |
| C04 | Intervalo mínimo e alerta de intervalo curto |  | ● |  |  |  | ● |  |  |  |  |  |  | Feito | Configurável |
| C05 | Alerta de mais de 6h sem intervalo |  | ● |  |  |  | ● |  |  |  |  |  |  | Feito | Regra automática |
| C06 | Horas extras 50% e 100% | ● | ● |  |  | ● |  |  |  |  |  |  |  | Feito | Separadas em dias úteis e folgas ou feriados |
| C07 | Limite diário de hora extra com alerta |  |  | ● |  | ● | ● | ● |  |  |  |  |  | Feito | Configurável |
| C08 | Adicional noturno | ● |  |  |  |  |  |  |  |  |  |  |  | Parcial | Cálculo pronto; jornada que atravessa a meia-noite fica para o app |
| C09 | Interjornada mínima de 11h | ● |  |  |  |  |  |  |  |  |  |  |  | Feito | Alerta automático |
| C10 | Banco de horas com saldo | ● |  |  |  |  |  |  |  |  |  | ● |  | Feito | Saldo acumulado e folga compensatória |
| C11 | Validade do banco de horas |  |  |  |  |  |  |  |  |  |  |  |  | Parcial | Configuração; vencimento automático no app |
| C12 | Feriados nacionais no cálculo |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Calendário em Organização |
| C13 | Feriados estaduais e municipais |  |  |  |  |  |  |  |  |  |  |  |  | Pendente | Entram no app real, por unidade |
| C14 | Descanso semanal remunerado (DSR) |  |  |  |  |  |  |  |  |  |  |  |  | Pendente | Depende da política da empresa e da folha |
| C15 | Escalas 12x36 e turnos rotativos | ● |  |  |  |  |  |  |  |  |  |  |  | Pendente | Exige virada de dia |
| C16 | Regras de leis de jornada por local (fair workweek) | ● | ● |  |  |  |  |  |  |  |  |  |  | Pendente | Específico dos EUA; aqui vale a CLT |
| C17 | Alerta de jornada acima de 10h |  |  |  |  |  |  |  |  |  |  |  |  | Feito | Regra da CLT |

## D · Escalas

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| D01 | Escala semanal por pessoa |  | ● | ● | ● |  | ● | ● |  |  |  |  |  | Feito | Tela Escalas |
| D02 | Folga e plantão em um clique |  |  |  |  |  | ● | ● |  |  |  |  |  | Feito | Gestor alterna o dia |
| D03 | Comparar escala e realizado |  | ● |  |  |  |  |  |  |  |  |  |  | Feito | Previsto × realizado e alerta de atraso |
| D04 | Troca de turno entre pessoas |  |  |  |  |  | ● | ● |  |  |  |  |  | Parcial | Pedido como tipo de ausência; troca automática no app |
| D05 | Turnos abertos que o colaborador reivindica |  |  |  |  |  | ● | ● |  |  |  |  |  | Pendente | Fora do escopo da primeira versão |
| D06 | Escala sugerida por previsão de demanda | ● | ● |  |  |  |  |  |  |  |  |  |  | Pendente | Exige dados de vendas e IA |
| D07 | Custo de mão de obra | ● | ● |  | ● |  | ● | ● |  |  |  |  |  | Feito | Módulo opcional, desligado por padrão, só RH e Admin (V5-03) |
| D08 | Custo contra vendas |  | ● |  |  |  |  |  |  |  |  |  |  | Pendente | Sem dados de vendas |

## E · Ausências

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| E01 | Férias com saldo de dias | ● |  |  |  |  | ● | ● |  |  |  | ● |  | Feito | 30 dias, agendado e usado |
| E02 | Atestado médico |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Aprovado pelo gestor |
| E03 | Folga compensatória pelo banco de horas |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Desconta do banco |
| E04 | Licenças e abonos |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Tipos Licença e Abono |
| E05 | Calendário de ausências da equipe |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Em Ausências e Escalas |
| E06 | Saldo de férias calculado por período aquisitivo | ● |  |  |  |  |  |  |  | ● |  |  |  | Parcial | Saldo fixo de 30 dias por ano |
| E07 | Anexar atestado em PDF ou imagem |  |  |  |  |  |  |  |  |  |  |  |  | Pendente | Upload fica para o app real |

## F · Aprovação e fechamento

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| F01 | Aprovação de ajustes pelo gestor |  | ● | ● | ● | ● |  |  |  |  |  |  |  | Feito | Aprovações |
| F02 | Aprovação do espelho mensal |  | ● | ● | ● | ● |  |  |  |  |  |  |  | Feito | Aprovar espelho |
| F03 | Assinatura eletrônica do espelho pelo colaborador |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Botão Assinar espelho |
| F04 | Fechamento do mês que trava alterações | ● |  |  |  |  |  |  |  |  |  |  |  | Feito | Fechar mês pelo RH |
| F05 | Aprovação em lote |  | ● |  |  |  |  |  |  |  |  |  |  | Parcial | Fechamento em lote pronto; ajustes em lote no app |
| F06 | Trilha de auditoria | ● |  |  | ● |  |  |  |  |  |  |  | ● | Feito | Tela Auditoria com filtro |

## G · Gestão em tempo real e alertas

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| G01 | Quem está trabalhando, no intervalo ou ausente agora |  | ● |  |  |  |  |  |  |  |  |  |  | Feito | Minha equipe e Visão geral |
| G02 | Atrasos e ausências do dia |  | ● |  |  |  |  | ● |  |  |  |  |  | Feito | Painel de exceções |
| G03 | Marcação ímpar e faltas sem justificativa |  | ● |  |  |  |  |  |  |  |  | ● |  | Feito | Painel de exceções e Alertas |
| G04 | Batida fora da escala |  | ● |  |  |  |  |  |  |  |  |  |  | Feito | Painel de exceções |
| G05 | Alertas de hora extra |  |  | ● |  |  | ● | ● |  |  |  |  |  | Feito | Alerta e exceção |
| G06 | Notificações por e-mail e push | ● |  |  |  |  |  | ● |  |  |  |  |  | Parcial | Central de Alertas e preferências; envio real no app |
| G07 | Perguntas rápidas ao sistema (assistente) |  | ● |  |  |  |  |  |  |  |  |  |  | Parcial | Painel de exceções responde às mesmas perguntas, sem IA conversacional |
| G08 | Mural e mensagens para a equipe |  |  | ● |  |  |  | ● |  |  |  |  |  | Parcial | Mural de avisos; chat fica para o app |

## H · Relatórios e integrações

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| H01 | Espelho de ponto mensal |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Meu espelho e espelho da equipe |
| H02 | Relatórios consolidados por colaborador | ● | ● |  |  |  |  |  |  |  |  | ● |  | Feito | Consolidado, extras, atrasos, banco |
| H03 | Horas por projeto |  |  |  | ● |  |  |  |  | ● |  |  |  | Feito | Relatório por projeto |
| H04 | Relatório de localização das batidas |  |  |  |  |  |  |  |  |  | ● |  |  | Feito | Relatório Localização |
| H05 | Eventos para a folha de pagamento |  |  |  |  |  | ● |  | ● | ● | ● | ● |  | Feito | Relatório Eventos de folha |
| H06 | Arquivos AFD e AEJ da Portaria 671 |  |  |  |  |  |  |  |  |  |  |  | ● | Parcial | Prévia ilustrativa; arquivo oficial assinado no app |
| H07 | Exportação CSV |  | ● |  |  |  |  |  |  |  | ● |  |  | Feito | Texto para copiar (download bloqueado no visualizador) |
| H08 | Exportação PDF e Excel |  | ● |  |  |  |  |  |  |  | ● |  |  | Pendente | Depende de download de arquivo, indisponível no visualizador |
| H09 | Relatórios personalizados |  |  |  |  |  |  |  |  |  |  | ● |  | Pendente | Construtor de relatórios no app real |
| H10 | Integração com folha (ADP, TOTVS, Senior) |  |  |  | ● |  |  |  |  | ● | ● | ● |  | Parcial | Conectores simulados |
| H11 | API e webhooks | ● |  |  |  |  |  |  |  |  |  |  |  | Parcial | Tela com token fictício |
| H12 | Agenda (Google Calendar e Outlook) |  |  |  |  |  |  |  |  |  |  |  |  | Parcial | Conector simulado |
| H13 | Faturamento, despesas e invoices |  |  |  | ● |  |  |  |  | ● |  |  |  | Pendente | Fora do escopo de ponto |

## I · Cadastro e organização

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| I01 | Ficha completa do colaborador |  |  |  |  |  |  |  |  |  |  | ● |  | Feito | Matrícula, CPF, setor, cargo, gestor, unidade, contrato, admissão, centro de custo, valor da hora e PIN |
| I02 | Setores |  |  |  |  |  |  |  |  |  |  |  |  | Feito | Organização |
| I03 | Unidades e locais de trabalho |  | ● |  |  |  |  |  |  |  |  |  |  | Feito | Organização |
| I04 | Projetos e atividades |  |  |  | ● |  |  |  |  |  |  |  |  | Feito | Organização |
| I05 | Perfis e permissões | ● |  |  |  |  |  |  |  |  |  |  |  | Feito | Quatro perfis |
| I06 | Importação em massa por planilha |  |  |  |  |  |  |  |  |  |  |  |  | Pendente | App real |
| I07 | Foto do colaborador |  |  |  |  |  |  |  |  |  |  |  |  | Parcial | Avatar com iniciais |

## J · Segurança e conformidade

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| J01 | Política de senha forte e troca de senha |  |  |  | ● |  |  |  |  |  |  |  |  | Feito | Meu perfil |
| J02 | Recuperação de senha |  |  |  |  |  |  |  |  |  |  |  |  | Parcial | Fluxo simulado |
| J03 | Bloqueio após tentativas erradas |  |  |  |  |  |  |  |  |  |  |  |  | Feito | Três tentativas |
| J04 | Verificação em duas etapas |  |  |  |  |  |  |  |  |  |  |  |  | Parcial | Configuração |
| J05 | Login único (SSO) e provisionamento (SCIM) |  |  |  | ● |  |  |  |  |  |  |  |  | Parcial | Configuração e integração simuladas |
| J06 | LGPD e termo de consentimento de localização |  |  |  |  |  |  |  |  |  |  | ● |  | Parcial | Documentado; tela de consentimento no app |
| J07 | Conformidade com a Portaria 671 e registro no INPI |  |  |  |  |  |  |  |  |  |  | ● | ● | Pendente | Depende da decisão Q-01 |

## K · Outros módulos de RH

| ID | Funcionalidade | UKG | DEP | CON | CLK | JIB | HOM | WIW | RIP | QBT | BUD | PTM | BR | Protótipo | Como está |
|---|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|---|
| K01 | Contratação e admissão digital |  |  |  |  |  | ● |  | ● |  |  | ● |  | Pendente | Fora do escopo do AxPonto |
| K02 | Folha de pagamento e holerite |  |  |  |  |  | ● |  | ● |  |  | ● |  | Pendente | Fora do escopo; o AxPonto envia eventos |
| K03 | Benefícios, gestão de TI e dispositivos |  |  |  |  |  |  |  | ● |  |  |  |  | Pendente | Fora do escopo |
| K04 | Desempenho e engajamento |  |  |  |  |  |  |  |  |  |  | ● |  | Pendente | Fora do escopo |
