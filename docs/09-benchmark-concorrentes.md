# 09 · Benchmark de sistemas de ponto

> Estudo dos 10 sistemas de controle de ponto mais citados no mercado, feito para não deixar nenhuma função importante de fora do AxPonto.
> Catálogo completo de funções: [10 · Matriz de funcionalidades](10-matriz-de-funcionalidades.md).

## Como escolhemos os 10

Não existe um ranking oficial de "mais usados no mundo". As fontes encontradas são listas editoriais e avaliações de usuários, sem dados de participação de mercado. Por isso o critério foi **aparecer de forma recorrente nessas listas e nas avaliações** do Capterra e comparativos de 2026, cobrindo três perfis: corporativo, pequenas equipes de campo e ferramentas de horas por projeto.

| # | Sistema | Perfil | Por que entrou |
|---|---|---|---|
| 1 | **UKG Workforce Management** (antigo Kronos) | Grandes empresas | Referência histórica em ponto corporativo e regras trabalhistas |
| 2 | **Deputy** | Equipes por turno | Primeiro colocado em um dos comparativos de 2026 e com o conjunto mais amplo de controles encontrado |
| 3 | **Connecteam** | Equipes de campo | Citado como o melhor para ponto por GPS e com o maior conjunto de antifraude encontrado |
| 4 | **Clockify** | Todos os portes | Mais de 5 milhões de usuários declarados e 4,8 de nota em milhares de avaliações |
| 5 | **Jibble** | Pequenas e médias | Reconhecimento facial e registro por chat, nota 4,8 |
| 6 | **Homebase** | Varejo e restaurantes | Ponto, escala e RH em um pacote |
| 7 | **When I Work** | Equipes por turno | Escala e mensagens entre a equipe |
| 8 | **Rippling** | Médias e grandes | Ponto dentro de uma plataforma de RH, folha e TI; nota 4,9 |
| 9 | **QuickBooks Time** | Pequenas empresas | Horas ligadas a folha e finanças |
| 10 | **Buddy Punch** | Pequenas empresas | Controle de local do registro, nota 4,8 |

**Referência Brasil (não conta entre os 10):** Pontomais, Tangerino, Secullum, Ahgora e Kairos, mais a **Portaria 671 do MTE**, que define o que um sistema de ponto precisa cumprir no país. A Pontomais foi estudada em detalhe. Das demais só havia descrições gerais.

## O que cada sistema faz de mais relevante

| Sistema | Destaques confirmados nas fontes |
|---|---|
| **UKG** | Registro por relógio biométrico, celular, navegador, telefone e reconhecimento facial sem toque. Motor de regras com alertas de exceção, atualização de regras de lei, trilha pronta para auditoria, painéis de horas, exceções e custo. Automação de hora extra e adicionais. Registro móvel com cerca virtual. Políticas de acúmulo para férias e licenças |
| **Deputy** | Folha de horas automática. Confirmação de local por GPS ou foto. Lançamento manual com aprovação. Várias unidades. Exportação para Excel e folha. Monitoramento de intervalos, hora extra e adicionais. Visão em tempo real de quem está no turno, atrasado ou em pausa. Relatórios de horas previstas contra realizadas e custo contra vendas. Pedidos em linguagem natural: pendências de aprovação, aprovação em lote, atrasos, comparação com a escala, quem esqueceu de bater a saída, quem bateu sem estar escalado, faltas, correção e criação de folha |
| **Connecteam** | Cerca virtual com raio ajustável e aprovação de batidas fora da cerca, com aviso. Quiosque com selfie e reconhecimento facial. Conta ligada ao telefone mais GPS contra batida por colega. Saída automática. Limite de entrada antecipada. Alerta de hora extra. Alerta de aparelho diferente. Integração com escala |
| **Clockify** | Projetos, tarefas, taxas, estimativas e orçamento. Quiosque por PIN. Auditoria de tempo, edição em lote, lançar horas para outros. Folgas, faturamento e aprovação de folha. Relatório de presença e hora extra. Escala, previsão, custo de mão de obra, GPS e despesas. SSO e log de auditoria nos planos altos |
| **Jibble** | Reconhecimento facial e quiosque rápido. Registro por navegador, celular, desktop, extensão e por Slack e Teams. Cerca virtual com entrada e saída automáticas. Hora extra por dia ou semana com tipos e taxas. Aprovação de folhas. Folgas pelo celular |
| **Homebase** | Relógio de ponto no plano gratuito. Alertas de intervalo e hora extra. Previsão e controle de custo. Folgas. Folha e RH no mesmo pacote |
| **When I Work** | Alertas de atraso e hora extra em tempo real. Conversas por turno, individuais e em grupo, com arquivos. Folgas pelo aplicativo. Custo de mão de obra |
| **Rippling** | Ponto como parte de uma plataforma única de RH, folha, despesas, benefícios e computadores. Integração nativa com a folha |
| **QuickBooks Time** | GPS, controle de folgas, integração com folha (ADP, Square, Paychex, OnPay, Justworks) |
| **Buddy Punch** | Ver onde cada pessoa está e restringir onde pode bater. Integra com QuickBooks, ADP, Paychex, Gusto, Paylocity. Exporta para Excel |
| **Pontomais** (Brasil) | Registro simples, offline, por quiosque (PontoREP) com QR Code ou reconhecimento facial, facial offline, por WhatsApp. Antifraude. Portaria 671 e LGPD. Assinatura eletrônica do espelho sem certificado digital. Relatório de ocorrências (marcação ímpar, ponto faltante, batida em férias). Banco de horas em tempo real. Férias, folgas e escala. Mais de 20 relatórios e indicadores de absenteísmo e horas noturnas. Integração com folha |
| **Portaria 671** (Brasil) | REP-P: software de ponto em nuvem com registro no INPI. Identificação do trabalhador e da empresa. Hora legal brasileira com variação máxima de 30 segundos. Relógio digital com segundos. Marcações imutáveis (AFD) e arquivo de jornada tratada (AEJ). Assinaturas no padrão CAdES. Comprovante ao trabalhador. Operação offline excepcional com envio posterior |

## O que o AxPonto incorporou

Do estudo saíram **105 funções catalogadas**. Em síntese, o protótipo agora cobre:

- **Registro:** web, quiosque com PIN, selfie, QR, offline, projeto por batida, comprovante numerado.
- **Local e antifraude:** local obrigatório com mapa, cerca por unidade com raio ajustável, três modos para batida fora da cerca, alerta de aparelho diferente.
- **Regras da CLT:** tolerância, intervalo mínimo, mais de 6h sem pausa, hora extra 50% e 100%, limite diário, interjornada de 11h, jornada acima de 10h, adicional noturno, banco de horas, feriados.
- **Escalas e ausências:** escala semanal com folga e plantão, comparação com o realizado, férias com saldo, atestado, folga compensatória, licença, abono, calendário de ausências.
- **Aprovação e fechamento:** ajustes, espelho assinado pelo colaborador, aprovado pelo gestor e fechado pelo RH, com mês travado.
- **Gestão:** painel de exceções (atrasos, marcação ímpar, faltas, fora da escala, fora da área, aparelho, offline, extras, espelhos), custo de mão de obra, realizado contra previsto.
- **Relatórios:** consolidado, extras, atrasos e faltas, banco de horas, horas por projeto, localização, eventos de folha, prévia de AFD e AEJ.
- **Cadastro:** ficha completa, setores, unidades, projetos, jornadas, perfis.
- **Configuração e integrações:** políticas de ponto, métodos de registro, segurança, conectores simulados.

Os números exatos de cobertura estão em [10 · Matriz de funcionalidades](10-matriz-de-funcionalidades.md#resumo-de-cobertura).

## O que ficou de fora e por quê

| Grupo | Exemplos | Motivo |
|---|---|---|
| Fora do tema ponto | Contratação, folha completa, benefícios, gestão de computadores, desempenho, faturamento e despesas | São módulos de outros produtos. O AxPonto envia eventos para a folha |
| Exige app nativo ou hardware | Registro automático ao cruzar a cerca, rastreio contínuo de GPS, extensão de navegador, URA, leitor biométrico real | Dependem do app real. Rastreio contínuo foi descartado por privacidade (LGPD) |
| Precisa de decisão | Homologação e INPI, DSR, escalas 12x36, feriados municipais | Ver [perguntas em aberto](08-perguntas-em-aberto.md) |
| Depende do ambiente | PDF e Excel, upload de atestado, câmera real, envio de e-mail | O visualizador do artefato bloqueia download e dispositivos |

## Limites deste estudo

- As informações vêm de páginas públicas dos fornecedores, comparativos e agregadores. Várias são material de marketing, então são alegações do fornecedor, não verificação independente.
- Algumas páginas de recursos não puderam ser lidas (bloqueadas ou indisponíveis na consulta): Connecteam, Jibble, Clockify, Homebase e When I Work em suas páginas oficiais. Nesses casos usei resultados de busca e comparativos.
- Para Rippling não foi possível confirmar reconhecimento facial, GPS nem acúmulo de férias.
- Para Tangerino, Secullum, Ahgora e Kairos há só descrições gerais. Nenhuma lista de funções detalhada foi lida.
- Na matriz, **ausência de marca não prova ausência da função**. Antes de qualquer decisão comercial, vale uma demonstração de cada produto.
- Preços variam entre fontes e não foram usados.

## Fontes consultadas

- [10 Best Time and Attendance Software of 2026 · People Managing People](https://peoplemanagingpeople.com/tools/best-time-and-attendance-software/) (acesso bloqueado na leitura; aparece nos resultados de busca)
- [7 Best Time and Attendance Software in 2026 · Apps365](https://www.apps365.com/blog/best-time-and-attendance-software/)
- [7 Top Time and Attendance Software · Paycor](https://www.paycor.com/resource-center/articles/top-time-and-attendance-software/)
- [Best Time Clock Software 2026 · Capterra](https://www.capterra.com/time-clock-software)
- [Deputy · Time and Attendance](https://www.deputy.com/features/time-and-attendance)
- [Connecteam · Geofence time clock](https://connecteam.com/employee-time-clock-app/geofence-time-clock-app/) e [Time theft](https://connecteam.com/employee-time-clock-app/time-theft/)
- [Clockify · Paid features explained](https://clockify.me/learn/resources/paid-features-explained/) e [Software Advice](https://www.softwareadvice.com/time-clock/clockify-profile/)
- [Jibble · Features](https://www.jibble.io/features) e [Review · Fit Small Business](https://fitsmallbusiness.com/jibble-review/)
- [Homebase vs When I Work](https://www.joinhomebase.com/compare/homebase-vs-wheniwork) e [SoftwareFinder](https://softwarefinder.com/resources/when-i-work-vs-homebase)
- [UKG · Time and attendance](https://www.ukg.com/products/features/time-and-attendance)
- [Buddy Punch vs QuickBooks Time](https://buddypunch.com/compare/buddy-punch-vs-quickbooks-time/) e [Buddy Punch vs Rippling · TrustRadius](https://trustradius.com/compare-products/buddy-punch-vs-rippling)
- [Pontomais](https://www.pontomais.com.br/) e [B2B Stack · sistemas de ponto](https://www.b2bstack.com.br/categoria/sistema-de-ponto)
- [Portaria 671 · Senior](https://documentacao.senior.com.br/exigenciaslegais/destaques/portaria-671) e [Anexo IX · TOTVS](https://tdn.totvs.com.br/download/attachments/809504336/ANEXO-IX-REQUISITOS-DO-REGISTRADOR-ELETRONICO-DE-PONTO-VIA-PROGRAMA-REP-P.pdf?api=v2)
