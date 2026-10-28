# 08 · Perguntas em aberto

Itens que precisam de decisão antes de especificar o app real.

| # | Pergunta | Impacto | Responsável | Status |
|---|---|---|---|---|
| Q-01 | O produto precisa ser **homologado** como ponto eletrônico (Portaria 671/MTE) ou será um controle interno? | Define arquitetura, comprovantes e promessa comercial | A definir | Aberto |
| Q-02 | O nome será **AxPonto**? | Marca e domínio | AxSys IT | Aberto |
| Q-03 | Produto próprio ou ferramenta interna? **Decisão: produto vendido como serviço (SaaS) a várias empresas.** Cada cliente é controlador dos dados e indica o próprio encarregado (DPO). A AxSys é operadora | Multiempresa, contratos, isolamento de dados | AxSys IT | Resolvido (Rodada 9) |
| Q-04 | A localização já é **obrigatória** (decidido). Falta definir: estar fora da área da empresa bloqueia, só sinaliza ou exige justificativa? Qual o raio? Vale um cadastro de locais por empresa? | Regras de bloqueio e LGPD | A definir | Parcial |
| Q-11 | A localização é coletada só na batida ou também em segundo plano? Quanto tempo guardamos? | LGPD, termo de consentimento | A definir | Aberto |
| Q-12 | O que fazer com quem usa navegador ou aparelho sem GPS, ou em prédio com sinal fraco (precisão ruim)? | Aceitar com precisão mínima ou exigir ajuste | A definir | Parcial: Sem GPS: ponto sem localização (Q-20). Precisão ruim: aberto |
| Q-05 | Como será o banco de horas: compensação, limite, vencimento? | Cálculo de saldo | RH do cliente | Parcial: Compensação feita; limite e vencimento abertos |
| Q-06 | Haverá feriados, férias, atestados e abonos no espelho? | Novas situações de dia | A definir | Resolvido no protótipo (Rodada 4); falta confirmar |
| Q-07 | Tempo de expiração da sessão e política de senha | Segurança | AxSys IT | Aberto |
| Q-08 | Quais relatórios o RH precisa de fato? | Escopo da primeira versão | RH do cliente | Aberto |
| Q-09 | Tecnologia do app real (front, back, banco, hospedagem) | Prazo e custo | AxSys IT | Aberto |
| Q-10 | Autenticação única (SSO) com Google ou Microsoft? | Login e cadastro | A definir | Aberto |
| Q-13 | A selfie usa **dado biométrico** (dado sensível na LGPD). Decisão da AxSys: a validação facial passou a ser **obrigatória** (Rodada 8), o que aumenta a urgência do parecer. Falta o parecer jurídico sobre a base legal (o art. 11, II, g da LGPD é a mais citada, mas sua aplicação ao ponto de empregados é debatida), o prazo de guarda da imagem e se há termo específico | LGPD, risco jurídico | Jurídico | Parcial: Pacote jurídico pronto em [docs/11](11-pacote-juridico-lgpd.md); falta revisão do advogado |
| Q-14 | Como tratar DSR (descanso semanal remunerado) e feriados municipais e estaduais? | Cálculo de folha e relatórios | RH do cliente | Aberto |
| Q-15 | O produto precisa suportar escala 12x36, turnos noturnos que viram o dia e jornadas rotativas na primeira versão? | Modelo de dados e cálculo | A definir | Aberto |
| Q-16 | Valor da hora e custo no app de ponto. AxSys questionou se faz sentido. **Resposta: não é essencial.** Virou módulo opcional, desligado por padrão, visível só a RH e Admin | Escopo e privacidade | AxSys IT | Resolvido |
| Q-17 | App nativo ou web? **Decisão: web responsivo instalável (PWA), funcionando em qualquer navegador e aparelho.** App nativo só se surgir função que o navegador não faz | Prazo e custo | AxSys IT | Resolvido |
| Q-20 | Quem nega a localização ou está em aparelho sem GPS. **Decisão: o ponto sem localização fica pendente, com justificativa de quem bate, e só é registrado quando o gestor aprovar, também com justificativa.** | Acessibilidade e regra de localização obrigatória | AxSys IT | Resolvido (Rodada 6) |
| Q-21 | Prazo do gestor e limite mensal no ponto sem localização. **Decisão: prazo comum de 2 dias úteis (configurável), lembrete no último dia e escalonamento ao RH; sem limite mensal por pessoa.** Não há prazo legal específico | Fluxo de aprovação e abuso | AxSys IT | Resolvido (Rodada 7) |
| Q-22 | Alternativa para quem não pode usar a câmera e escolha do serviço de prova de vida. **Decisão: exceção auditada (batida pendente de aprovação) e método alternativo autorizado pelo RH, sem registrar o motivo. Fornecedor por prova de conceito** ([docs/12](12-fornecedores-prova-de-vida.md)) | Acessibilidade, LGPD, custo | AxSys IT e Jurídico | Parcial: Alternativa resolvida no protótipo; fornecedor aberto |
| Q-23 | Abertura da empresa: a AxSys IT ainda não tem CNPJ. Tipo societário, data prevista e enquadramento tributário. Sem CNPJ não se assina contrato com cliente | Venda, contratos, notas fiscais | AxSys IT e contador | Aberto |
| Q-24 | Preço final por colaborador e mínimo mensal, após cotação da prova de vida ([docs/13](13-precificacao.md)) | Margem e competitividade | AxSys IT | Aberto |
| Q-18 | Quais integrações de folha entram primeiro (TOTVS, Senior, ADP, Domínio, Conta Azul)? | Prioridade de integração | Clientes-alvo | Aberto |
| Q-19 | Valores padrão: tolerância 10 min, limite de hora extra 2h, raio da cerca 200 m, intervalo mínimo 60 min. Estão certos? | Regras de alerta | RH do cliente | Parcial: Valores de partida |

> Quando uma pergunta for decidida, mova a resposta para [07 · Registro de validações](07-registro-de-validacoes.md) e atualize o documento afetado.
