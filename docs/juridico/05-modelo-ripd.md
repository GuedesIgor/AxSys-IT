# Modelo de Relatório de Impacto à Proteção de Dados Pessoais (RIPD)

> **Minuta aprovada pelo advogado, conforme informado pelo dono em [data]. Inscrição conferida no CNA em 28/10/2026: situação regular.** Advogado responsável pela revisão: Dr. Dinalto Gomes Martins, OAB/MS nº 28.925. Falta a assinatura do advogado, que só ele pode apor. Modelo fornecido pela AxSys IT (operadora) para que cada **cliente (controlador)** preencha, revise e assine. Base: LGPD, art. 5, XVII e art. 38. Conteúdo base em [docs/11](../11-pacote-juridico-lgpd.md), seção 5.

**Controlador:** [razão social do cliente]  **Encarregado:** [nome e contato]  **Data:** [data]  **Versão:** [1.0]
**Operador:** AxSys IT  **Tratamento:** validação facial com prova de vida no registro de ponto

## 1. Descrição do tratamento

| Item | Resposta |
|---|---|
| Finalidade | Confirmar a identidade de quem registra o ponto e evitar fraude |
| Dados | Modelo facial, resultado da prova de vida, pontuação de similaridade, data e hora, aparelho. Sem foto armazenada |
| Titulares | [número aproximado] empregados e estagiários |
| Frequência | Cadastro (uma vez) e [2 a 4] vezes por dia |
| Compartilhamento | Operador e suboperadores do Anexo B do contrato |
| Retenção | Modelo até o desligamento + 30 dias. Resultado pelo prazo do registro de jornada |
| Local do tratamento | [Brasil / outro] |

## 2. Base legal escolhida pelo controlador

[ ] Art. 11, II, "g" (prevenção à fraude na autenticação)  [ ] Art. 11, I (consentimento específico)  [ ] Outra: [ ]
Justificativa: [texto]

## 3. Necessidade e proporcionalidade

| Pergunta | Resposta do controlador |
|---|---|
| Por que o rosto e não PIN ou QR? | [ex.: histórico de fraude por empréstimo de crachá ou PIN] |
| Existe alternativa equivalente? | Sim, método alternativo autorizado pelo RH |
| Quem autoriza a alternativa e em quanto tempo? | [RH, em até __ dias] |
| O que acontece com quem recusa? | Nada além do uso do método alternativo. Sem sanção |
| Como será informado? | Aviso no primeiro acesso e [reunião/e-mail] |

## 4. Riscos e medidas

| Risco | Probab. | Impacto | Medida do controlador | Medida da AxSys |
|---|---|---|---|---|
| Vazamento do modelo facial | [ ] | [ ] | Política de acesso ao painel | Cifragem, base separada, log de acesso |
| Uso para outra finalidade | [ ] | [ ] | Política interna proibindo | Bloqueio técnico e cláusula contratual |
| Discriminação ou falsa rejeição | [ ] | [ ] | Alternativa sem sanção | Teste de viés próprio, documentado |
| Coação para aceitar | [ ] | [ ] | Canal de reclamação ao encarregado | Aviso e alternativa no sistema |
| Fraude com foto, vídeo ou máscara | [ ] | [ ] | Apuração disciplinar | Prova de vida própria com desafios aleatórios verificados no servidor, testes de fraude documentados, limite de tentativas |
| Retenção excessiva | [ ] | [ ] | Registrar desligamentos em dia | Eliminação automática do modelo |
| Incidente de segurança | [ ] | [ ] | Plano de comunicação à ANPD | Aviso em até 24 horas |

## 5. Conclusão e aprovação

Risco residual: [baixo / médio / alto]. Parecer do encarregado: [texto]. Decisão: [ ] aprovar  [ ] aprovar com condições  [ ] não aprovar.

Responsável: ______________________  Encarregado: ______________________  Data: __/__/____

## 6. Revisão

Revisar a cada [12] meses, ou quando mudar o fornecedor, a finalidade, o tipo de dado ou após incidente.
