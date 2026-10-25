# 08 · Perguntas em aberto

Itens que precisam de decisão antes de especificar o app real.

| # | Pergunta | Impacto | Responsável | Status |
|---|---|---|---|---|
| Q-01 | O produto precisa ser **homologado** como ponto eletrônico (Portaria 671/MTE) ou será um controle interno? | Define arquitetura, comprovantes e promessa comercial | A definir | 🔴 Aberto |
| Q-02 | O nome será **AxPonto**? | Marca e domínio | AxSys IT | 🔴 Aberto |
| Q-03 | O sistema será produto próprio (SaaS para vários clientes) ou ferramenta para uso interno de um cliente? | Multi-empresa, cobrança, isolamento de dados | AxSys IT | 🔴 Aberto |
| Q-04 | A localização já é **obrigatória** (decidido). Falta definir: estar fora da área da empresa bloqueia, só sinaliza ou exige justificativa? Qual o raio? Vale um cadastro de locais por empresa? | Regras de bloqueio e LGPD | A definir | 🟡 Parcial |
| Q-11 | A localização é coletada só na batida ou também em segundo plano? Quanto tempo guardamos? | LGPD, termo de consentimento | A definir | 🔴 Aberto |
| Q-12 | O que fazer com quem usa navegador ou aparelho sem GPS, ou em prédio com sinal fraco (precisão ruim)? | Aceitar com precisão mínima ou exigir ajuste | A definir | 🔴 Aberto |
| Q-05 | Como será o banco de horas: compensação, limite, vencimento? | Cálculo de saldo | RH do cliente | 🔴 Aberto |
| Q-06 | Haverá feriados, férias, atestados e abonos no espelho? | Novas situações de dia | A definir | 🔴 Aberto |
| Q-07 | Tempo de expiração da sessão e política de senha | Segurança | AxSys IT | 🔴 Aberto |
| Q-08 | Quais relatórios o RH precisa de fato? | Escopo da primeira versão | RH do cliente | 🔴 Aberto |
| Q-09 | Tecnologia do app real (front, back, banco, hospedagem) | Prazo e custo | AxSys IT | 🔴 Aberto |
| Q-10 | Autenticação única (SSO) com Google ou Microsoft? | Login e cadastro | A definir | 🔴 Aberto |

> Quando uma pergunta for decidida, mova a resposta para [07 · Registro de validações](07-registro-de-validacoes.md) e atualize o documento afetado.
