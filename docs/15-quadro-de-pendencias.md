# 15 · Quadro de pendências

Atualizado em 28/10/2026. Reúne tudo o que falta, por quem precisa agir e por quanto bloqueia a venda. O detalhe de cada pergunta está em [08](08-perguntas-em-aberto.md).

**Bloqueia a venda:** sem isso não se assina contrato com cliente.
**Bloqueia o lançamento:** sem isso o sistema não vai ao ar.
**Pode esperar:** decide-se durante o desenvolvimento.

## 1. Depende do dono (AxSys IT)

| # | Pendência | Efeito | Referência |
|---|---|---|---|
| 1 | Abrir a empresa: tipo societário, CNPJ, razão social e endereço | Bloqueia a venda | Q-23; minutas |
| 2 | Responder sobre o SRVAD1: é controlador de domínio? Onde fica, qual link e qual energia? | Bloqueia o lançamento | Q-25; [14](14-hospedagem-iis.md) |
| 3 | Escolher o domínio do sistema e do demo e quem emite o certificado HTTPS | Bloqueia o lançamento | [14](14-hospedagem-iis.md) |
| 4 | Aprovar SLA de 99% no piloto (hoje o contrato diz 99,5%) | Bloqueia a venda | [14](14-hospedagem-iis.md), seção 3 |
| 5 | Definir o preço final por colaborador e o mínimo mensal | Bloqueia a venda | Q-24; [13](13-precificacao.md) |
| 6 | Definir o plano de cópias de segurança fora do local | Bloqueia o lançamento | [14](14-hospedagem-iis.md) |
| 7 | Confirmar o nome AxPonto e verificar disponibilidade de marca e domínio | Pode esperar | Q-02 |
| 8 | Preencher o e-mail de contato de privacidade e o nome do sócio nas minutas | Bloqueia a venda | minutas |
| 9 | Decidir se o produto será vendido como ponto eletrônico oficial (REP-P no INPI) ou como controle de jornada | Define a promessa comercial | Q-01 |

## 2. Depende do advogado (Dr. Dinalto Gomes Martins)

| # | Pendência | Efeito | Referência |
|---|---|---|---|
| 10 | Assinar as seis minutas (assinatura digital gov.br ou ICP-Brasil) e informar a data da aprovação | Bloqueia a venda | [docs/juridico](juridico/00-resumo-para-o-advogado.md) |
| 11 | Esclarecer a inscrição: o CNA mostra OAB/MS nº 28.925 (Três Lagoas), situação regular, mas a carteira antiga é de SP nº 389.139. Qual é a principal hoje? Como ele atende o foro de Ilha Solteira (SP)? | Bloqueia a venda | Conferência de 28/10/2026 |
| 12 | Responder as 11 perguntas do resumo (base legal, obrigatoriedade, Portaria 671, retenção, papéis, pequeno porte, limitação de responsabilidade, menores, sem certificação, sem CNPJ) | Bloqueia a venda | Q-13 |
| 13 | Validar a cláusula 10 (limitação de responsabilidade) | Bloqueia a venda | contrato SaaS |
| 14 | Confirmar se a batida pendente é compatível com a Portaria 671 e se a gravação imediata da marcação basta | Bloqueia o lançamento | RNF-19 |

## 3. Depende do desenvolvimento (a construir e testar)

| # | Pendência | Efeito | Referência |
|---|---|---|---|
| 15 | Escolher como obter o modelo de reconhecimento facial e conferir as licenças comerciais | Bloqueia o lançamento | Q-26; RNF-23 |
| 16 | Construir o leitor facial próprio com desafios verificados no servidor | Bloqueia o lançamento | [12](12-leitor-facial-proprio.md) |
| 17 | Rodar os testes de fraude e de viés e emitir o relatório interno | Bloqueia a venda | RNF-22 |
| 18 | Teste independente de resistência a fraude, para poder dizer "certificado" | Pode esperar | [12](12-leitor-facial-proprio.md), seção 8 |
| 19 | Certificação do REP-P no INPI | Pode esperar, se a venda for como controle de jornada | Q-01 |
| 20 | Escolher a tecnologia do app real (proposta: ASP.NET Core no IIS) | Bloqueia o lançamento | Q-09 |
| 21 | Tela do aviso ao colaborador e campo do encarregado no onboarding | Bloqueia o lançamento | RF-89, RF-90 |
| 22 | Isolamento total entre empresas na base de dados | Bloqueia o lançamento | RNF-20 |
| 23 | Rotina que apaga o modelo facial no desligamento | Bloqueia o lançamento | RNF-17 |

## 4. Regras do produto ainda sem decisão

| # | Pendência | Referência |
|---|---|---|
| 24 | Fora da área da empresa: bloqueia, sinaliza ou exige justificativa? Qual raio? | Q-04 |
| 25 | Localização só na batida ou também em segundo plano? Quanto tempo guarda? | Q-11 |
| 26 | Prédio com sinal fraco (precisão ruim da localização) | Q-12 |
| 27 | Banco de horas: limite e vencimento | Q-05 |
| 28 | Expiração da sessão e política de senha | Q-07 |
| 29 | Relatórios que o RH realmente precisa | Q-08 |
| 30 | Login único com Google ou Microsoft | Q-10 |
| 31 | DSR e feriados municipais e estaduais | Q-14 |
| 32 | Escala 12x36, noturno e jornada rotativa na primeira versão | Q-15 |
| 33 | Integrações de folha: qual primeiro | Q-18 |
| 34 | Confirmar os valores padrão (tolerância 10 min, extra 2 h, raio 200 m, intervalo 60 min) | Q-19 |

## 5. Já resolvido

Q-03 (venda como serviço), Q-06 (feriados e ausências no protótipo), Q-16 (custo da hora é módulo opcional), Q-17 (web instalável), Q-20 (ponto sem localização), Q-21 (prazo do gestor de 2 dias úteis e sem limite mensal). Inscrição do advogado conferida no CNA em 28/10/2026, situação regular.

## 6. Próximos passos sugeridos

1. Itens 1, 10 e 11: abrir a empresa e fechar a documentação do advogado.
2. Itens 2, 3 e 4: responder sobre o SRVAD1, o domínio e o SLA, para publicar o demo no IIS.
3. Item 15: prova de conceito pequena do modelo facial, antes de prometer desempenho.
E
