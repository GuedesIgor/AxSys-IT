# 11 · Pacote jurídico: biometria facial e LGPD

> **Aviso.** Este pacote foi elaborado pela equipe de produto com apoio do Claude. É um **rascunho de trabalho** para um advogado de proteção de dados e trabalhista revisar e assinar. Ele não é parecer jurídico. A pesquisa usou fontes secundárias; os artigos da Portaria 671 e da LGPD devem ser conferidos no texto oficial.
>
> **Status geral:** Em elaboração: rascunho completo, aguardando revisão de advogado habilitado.

Resolve, no que cabe ao produto, as perguntas [Q-13](08-perguntas-em-aberto.md) (parecer sobre selfie e biometria) e [Q-22](08-perguntas-em-aberto.md) (quem não pode usar a câmera).

---

## 1. Resumo para decidir

| Tema | Posição recomendada |
|---|---|
| Base legal | Não depender de uma só. Adotar o art. 11, II, "g" da LGPD (prevenção à fraude na autenticação) como base principal **e** manter alternativa equivalente a quem não quiser usar o rosto, o que reforça necessidade e proporcionalidade |
| Biometria obrigatória sem saída | **Evitar.** É o desenho mais frágil: risco de discriminação (LGPD art. 6, IX; Lei Brasileira de Inclusão) e de o empregador ficar sem registro de jornada |
| O que guardar | Só o **modelo matemático do rosto** (template), cifrado, em base separada. Sem foto por padrão |
| Prazo | Template apagado no desligamento (até 30 dias). Resultado da validação guardado com a batida pelo prazo do registro de jornada |
| Papéis | Empresa cliente é **controladora**; AxSys é **operadora** (se SaaS). Depende de [Q-03](08-perguntas-em-aberto.md) |
| Antes do lançamento | RIPD assinado, aviso ao colaborador, contratos com operadores, encarregado indicado e teste de falha de segurança |

**Ponto de honestidade:** não encontramos posição consolidada da ANPD sobre biometria no controle de ponto. A autoridade publicou o [Radar Tecnológico sobre biometria e reconhecimento facial](https://www.mayerbrown.com/en/insights/publications/2024/07/biometrics-and-facial-recognition-anpd-releases-report) (jun/2024) e abriu [tomada de subsídios para regulamentar o tema](https://convergenciadigital.com.br/governo/autoridade-de-dados-quer-regulamentar-uso-de-dados-biometricos-e-reconhecimento-facial/). O art. 11, II, "g" não é uma base óbvia para ponto de empregados. Por isso o desenho abaixo não aposta tudo nela.

---

## 2. Papéis (LGPD art. 5, VI e VII)

> **Decisão (Q-03):** o AxPonto é vendido a empresas. **Cada cliente é controlador e indica o seu encarregado.** A AxSys IT é operadora. Isso muda o que a AxSys precisa entregar: ver a seção 15.

| Papel | Quem | Observação |
|---|---|---|
| Controlador | Empresa que contrata o AxPonto (empregadora) | Decide finalidade e meios. Responde pela base legal e pelo aviso ao empregado |
| Operador | AxSys IT | Trata os dados em nome do cliente, conforme contrato (art. 39) |
| Suboperador | Fornecedor de prova de vida e comparação facial, nuvem | Precisa de contrato e autorização do controlador |
| Encarregado (DPO) | **Indicado por cada cliente** (controlador). A AxSys mantém um canal de contato e, como agente de pequeno porte, pode ter dispensa da indicação formal (Resolução CD/ANPD nº 2/2022; **confirmar**) | Canal com titulares e ANPD (art. 41) |

A AxSys também é controladora dos dados dos próprios usuários da conta (por exemplo, e-mail de contato do cliente), mas isso é tratamento comum, fora deste pacote.

---

## 3. Bases legais analisadas

| Base | Encaixe | Força | Comentário |
|---|---|---|---|
| Art. 11, II, "g": prevenção à fraude e segurança do titular na identificação e autenticação em sistemas eletrônicos | Conferir que quem bate é quem diz ser | Média | Cobre a **conferência na batida**. Não cobre outros usos do rosto. Aplicação a ponto de empregados é debatida |
| Art. 11, II, "a": cumprimento de obrigação legal | A CLT exige registro de jornada | Baixa para biometria | A lei exige registrar a jornada, não exige o rosto |
| Art. 11, I: consentimento específico e destacado | Aviso e aceite | Frágil se for o único | Entre empregador e empregado, a liberdade do consentimento é questionada. **Ganha força se existir alternativa real e sem prejuízo** |
| Art. 7, IX: legítimo interesse | | **Não se aplica** | Não vale para dado sensível |

**Recomendação:** base principal art. 11, II, "g", com RIPD demonstrando necessidade, **mais** alternativa equivalente garantida e aviso transparente. Se o advogado considerar a base insuficiente, a rota de contingência é consentimento específico com alternativa livre, e a validação facial passa a ser a opção padrão, não a única.

---

## 4. Decisões de produto derivadas

| # | Decisão proposta | Efeito no protótipo |
|---|---|---|
| J-01 | Validação facial com prova de vida segue **obrigatória por padrão** para todos | Já implementado (Rodada 8) |
| J-02 | **Exceção auditada:** falhou 3 vezes ou sem câmera. A batida vira pedido pendente, aprovado pelo gestor com justificativa dos dois lados | Rodada 9 |
| J-03 | **Método alternativo autorizado pelo RH** (PIN com confirmação no quiosque), com revisão periódica. **Não se registra o motivo**, para não tratar dado de saúde | Rodada 9 |
| J-04 | O pedido ao RH de método alternativo **não exige explicação**. Basta pedir | Texto do aviso |
| J-05 | O template facial é apagado no desligamento | Requisito RNF-17 |
| J-06 | Nenhuma foto guardada por padrão | Requisito RNF-18 |
| J-07 | O resultado da validação (aprovada, reprovada, método alternativo) fica gravado na batida e na auditoria | Já implementado |
| J-08 | Nunca usar o rosto para outra finalidade (por exemplo, avaliar humor, desempenho ou presença contínua) | Cláusula de contrato e aviso |

---

## 5. Relatório de Impacto à Proteção de Dados (RIPD), rascunho

**Base normativa:** LGPD art. 5, XVII e art. 38. Modelo para o cliente adaptar.

### 5.1 Descrição do tratamento

| Item | Conteúdo |
|---|---|
| Finalidade | Confirmar a identidade de quem registra o ponto, evitando que um colega bata por outro, e garantir a integridade do registro de jornada |
| Dados tratados | Template facial (modelo matemático), resultado da prova de vida, pontuação de similaridade, data e hora, aparelho. **Sem foto armazenada por padrão** |
| Titulares | Empregados, estagiários e demais pessoas que registram jornada |
| Quando ocorre | No cadastro (uma vez) e a cada batida |
| Compartilhamento | Operador (AxSys) e suboperador de prova de vida, sob contrato. Sem venda ou cessão a terceiros |
| Retenção | Ver seção 7 |

### 5.2 Necessidade e proporcionalidade

| Pergunta | Resposta proposta |
|---|---|
| O objetivo se alcança com menos dado? | Em parte: PIN e QR são mais frágeis (podem ser emprestados). O rosto reduz fraude. Por isso há alternativa para quem não puder ou não quiser |
| O dado coletado é o mínimo? | Sim: só template, sem foto, sem localização do rosto, sem vídeo |
| Há alternativa equivalente? | Sim: método alternativo autorizado pelo RH |
| Quem decide a exceção? | RH (método alternativo) e gestor (batida pontual), ambos com justificativa registrada |

### 5.3 Riscos e medidas

| Risco | Probabilidade | Impacto | Medida |
|---|:-:|:-:|---|
| Vazamento do template | Baixa | Alto | Cifragem em repouso e em trânsito, base separada, chave em cofre, acesso mínimo, log de acesso |
| Uso do dado para outra finalidade | Média | Alto | Cláusula contratual, política de finalidade, bloqueio técnico de exportação |
| Discriminação (falsa rejeição por tom de pele, idade, deficiência) | Média | Alto | Método alternativo, teste de viés do fornecedor, revisão de taxas de recusa por grupo (sem identificar a pessoa) |
| Coação por não aceitar o rosto | Média | Médio | Alternativa sem prejuízo, canal de reclamação ao encarregado |
| Fraude por foto, vídeo ou máscara | Média | Médio | Prova de vida certificada, desafios aleatórios, limite de tentativas |
| Retenção além do necessário | Média | Médio | Rotina de exclusão no desligamento, revisão periódica |
| Falha do fornecedor | Baixa | Médio | Contrato de operador, auditoria, plano de saída |
| Incidente de segurança | Baixa | Alto | Plano da seção 10 |

### 5.4 Parecer do encarregado e aprovação

Campos para preencher pelo cliente: data, nome do encarregado, parecer, nome do responsável, assinatura.

---

## 6. Registro das operações (ROPA, art. 37)

| Campo | Valor |
|---|---|
| Atividade | Validação facial para registro de ponto |
| Categoria de dados | Biométricos (sensível) e de jornada |
| Base legal | Art. 11, II, "g" (a confirmar pelo jurídico) |
| Finalidade | Autenticação do registrante e prevenção de fraude no ponto |
| Origem | Titular, no cadastro e na batida |
| Compartilhamento | Operador e suboperador de prova de vida |
| Transferência internacional | A definir conforme o fornecedor (art. 33; verificar a regulamentação vigente da ANPD sobre cláusulas-padrão) |
| Retenção | Seção 7 |
| Medidas de segurança | Seção 5.3 |

---

## 7. Política de retenção proposta

| Dado | Prazo | Justificativa |
|---|---|---|
| Template facial | Até o desligamento da pessoa, apagado em até 30 dias | Finalidade acaba com o vínculo |
| Foto da batida | **Não guardar.** Se o jurídico exigir evidência, no máximo 30 dias, cifrada | Minimização |
| Resultado da validação (aprovada, reprovada, alternativo, pontuação) | Junto com o registro de ponto | Prova do registro. A prescrição trabalhista (CF art. 7, XXIX: 5 anos na vigência, até 2 anos após o fim do contrato) orienta o prazo; **confirmar com o advogado** |
| Log de acesso ao dado biométrico | 6 meses no mínimo (Marco Civil, art. 15, para logs de aplicação) | Segurança e investigação |
| Pedido de exclusão | Atendido em até 15 dias, salvo obrigação de guarda | LGPD art. 18 e 19 |

---

## 8. Aviso ao colaborador (texto-base)

> **Como o AxPonto confere que é você**
>
> Para registrar o seu ponto, o sistema compara o seu rosto com um modelo matemático criado quando você foi cadastrado. Ele também confere que você está presente ao vivo, pedindo gestos simples como piscar ou virar a cabeça.
>
> **Para quê:** evitar que outra pessoa registre o ponto por você e proteger a integridade da sua jornada. Não usamos o seu rosto para nenhuma outra finalidade.
>
> **O que guardamos:** apenas o modelo matemático do rosto, que não é uma foto e não reconstrói a sua imagem. Por padrão, não guardamos fotos nem vídeos das batidas.
>
> **Por quanto tempo:** o modelo é apagado até 30 dias depois do seu desligamento. O resultado de cada conferência fica junto com o registro do ponto pelo prazo legal.
>
> **Quem acessa:** apenas os sistemas necessários à conferência e as pessoas autorizadas. Nada é vendido nem compartilhado para outros fins.
>
> **Você tem alternativa.** Se não puder ou não quiser usar o rosto, peça ao RH um método alternativo. Você **não precisa explicar o motivo** e não será prejudicado.
>
> **Seus direitos:** saber o que guardamos, corrigir, pedir a exclusão e reclamar ao encarregado de dados (`[contato do encarregado]`) ou à ANPD.

---

## 9. Contrato com operador e suboperadores: cláusulas mínimas

1. Tratar os dados só conforme as instruções documentadas do controlador (art. 39).
2. Proibição de usar os dados para treinar ou melhorar modelos próprios do fornecedor.
3. Localização do tratamento. Se for fora do Brasil, mecanismo de transferência internacional válido.
4. Segurança: cifragem, controle de acesso, segregação, testes de intrusão periódicos.
5. Prova de vida com **teste independente de resistência a fraude** (ISO/IEC 30107-3) e entrega da carta do laboratório, com data e versão testada.
6. Relatório de viés: taxas de falsa rejeição e falsa aceitação por faixa etária e tom de pele.
7. Comunicação de incidente ao controlador em até 24 horas.
8. Exclusão ou devolução dos dados ao fim do contrato, com certificado.
9. Direito de auditoria e lista de suboperadores com aviso prévio de mudança.
10. Apoio ao atendimento dos direitos dos titulares.

---

## 10. Plano de incidente de segurança (resumo)

1. Detectar e conter. Revogar chaves e acessos.
2. Avaliar se há risco ou dano relevante aos titulares.
3. O controlador comunica a ANPD e os titulares em prazo razoável (art. 48). A regulamentação da ANPD fixa prazo de **3 dias úteis**; confirmar o texto vigente.
4. Registrar causa, impacto e correção.
5. Revisar o RIPD.

---

## 11. Direitos dos titulares (art. 18)

| Pedido | Como o produto atende |
|---|---|
| Confirmar o tratamento e acessar | Tela de perfil mostra "cadastro facial feito em" e método de validação |
| Corrigir | Refazer o cadastro facial (RH) |
| Excluir | RH apaga o template; o colaborador passa ao método alternativo |
| Revogar ou questionar | Pedido ao RH ou ao encarregado, sem exigir motivo |
| Revisão de decisão automatizada (art. 20) | Recusa na validação facial leva à batida pendente com decisão humana do gestor |

---

## 12. Portaria MTP 671/2021 e o ponto eletrônico

Pontos que o advogado e o time técnico precisam conferir no texto oficial, pois as fontes encontradas são secundárias:

1. **Certificação:** o REP-P (programa) deve ser [certificado no INPI](https://solides.com.br/blog/rep-p/) e cumprir os requisitos técnicos do Anexo IX. O AxPonto só pode ser vendido como ponto eletrônico oficial depois disso (Q-01).
2. **Restrição de marcação:** o REP-P [não pode restringir horários de marcação](https://calculojuridico.com.br/portaria-671-mtp-mudancas-registro-ponto/) (redação dada pela Portaria MTP 1.486/2022). Conferir se a janela de entrada antecipada do protótipo, o bloqueio por cerca virtual e a recusa por falha facial podem ser vistos como restrição.
3. **Risco do desenho "pendente de aprovação":** se a batida sem localização ou sem validação facial **não é registrada até o gestor aprovar**, pode-se questionar se o registro da marcação foi feito na hora. **Mitigação proposta:** gravar de imediato a marcação recebida (hora do servidor, aparelho, justificativa) em registro imutável com situação "aguardando decisão", e deixar a aprovação decidir só se ela entra no cálculo da jornada. Isso preserva o rastro e a hora real. Item para o advogado validar.
4. **Biometria como meio de identificação:** a portaria admite identificação biométrica, inclusive facial, mas como possibilidade, não como obrigação.

---

## 13. Perguntas ao advogado

1. A base do art. 11, II, "g" cobre a validação facial do empregado no registro de ponto? Se não, qual base?
2. Basta o aviso (art. 9) ou é necessário termo específico? Convém negociar em acordo coletivo?
3. Tornar o rosto o método padrão, com alternativa livre, está seguro? E tornar o rosto o único método?
4. O prazo de guarda do template e do resultado da validação está correto?
5. O desenho de batida "pendente de aprovação" é compatível com a Portaria 671? A mitigação da seção 12.3 é suficiente?
6. O RIPD deve ser elaborado pelo controlador, pela AxSys ou por ambos?
7. Há necessidade de comunicação prévia à ANPD ou a sindicato?
8. Como tratar menores (estagiários e jovens aprendizes) e seus responsáveis?
9. Qual o texto correto para a transferência internacional, se o fornecedor processar fora do Brasil?

---

## 14. Checklist de lançamento

- [ ] Advogado revisou e assinou este pacote
- [ ] Canal de contato de privacidade da AxSys publicado
- [ ] Cada cliente indica o seu encarregado (exigir no onboarding)
- [ ] RIPD preenchido e assinado pelo cliente, com o modelo da AxSys
- [ ] Aviso ao colaborador publicado e entregue
- [ ] Contrato com operador e suboperadores com as cláusulas da seção 9
- [ ] Fornecedor de prova de vida escolhido ([doc 12](12-fornecedores-prova-de-vida.md))
- [ ] Carta de teste independente de resistência a fraude recebida
- [ ] Rotina de exclusão no desligamento testada
- [ ] Método alternativo disponível e divulgado
- [ ] Exercício de simulação de incidente feito
- [ ] Certificação do REP-P no INPI iniciada, se o produto for vendido como ponto oficial

## 15. O que a AxSys entrega a cada cliente (kit de conformidade)

As minutas já redigidas estão em [docs/juridico](juridico/00-resumo-para-o-advogado.md): contrato de operador, contrato SaaS e termos de uso, política de privacidade, aviso ao colaborador, modelo de RIPD e política de segurança.

Como a AxSys vende o sistema, a responsabilidade pela base legal e pelo aviso é do cliente, mas **o produto e os documentos devem facilitar** que ele cumpra.

| Entrega | Situação |
|---|---|
| Contrato de operador (cláusulas de dados) anexo ao contrato de serviço | A redigir com o advogado |
| Termos de uso e política de privacidade do AxPonto | A redigir |
| Modelo de RIPD e de aviso ao colaborador (seções 5 e 8) | Rascunho pronto |
| Lista de suboperadores (fornecedor de prova de vida, nuvem) com aviso de mudança | Depende do doc 12 |
| Tela do aviso ao colaborador no primeiro acesso, editável pelo cliente | Requisito RF-89 |
| Campo no onboarding para o cliente informar o encarregado e o contato | Requisito novo (RF-90) |
| Exclusão do template facial por colaborador e no desligamento | RNF-17 |
| Isolamento total entre empresas (cada cliente só vê os seus dados) | Requisito novo (RNF-20) |
| Relatório de exportação dos dados de uma pessoa, para atender pedidos de titular | A especificar |
| Canal e prazo para a AxSys avisar o cliente de incidente (até 24 h) | Seção 9 |

**Ponto de atenção:** vender o sistema com a promessa de "ponto eletrônico oficial" exige a certificação do REP-P no INPI (seção 12 e Q-01). Sem ela, o produto deve ser descrito como controle de jornada, e o cliente deve ser avisado da diferença.

## Fontes consultadas

- [ANPD: Radar Tecnológico sobre biometria e reconhecimento facial (resumo Mayer Brown)](https://www.mayerbrown.com/en/insights/publications/2024/07/biometrics-and-facial-recognition-anpd-releases-report)
- [Convergência Digital: ANPD quer regulamentar biometria e reconhecimento facial](https://convergenciadigital.com.br/governo/autoridade-de-dados-quer-regulamentar-uso-de-dados-biometricos-e-reconhecimento-facial/)
- [Cálculo Jurídico: Portaria 671/2021, mudanças no registro de ponto](https://calculojuridico.com.br/portaria-671-mtp-mudancas-registro-ponto/)
- [Solides: REP-P e certificação no INPI](https://solides.com.br/blog/rep-p/)
- Lei 13.709/2018 (LGPD), Lei 13.146/2015 (Lei Brasileira de Inclusão) e Portaria MTP 671/2021: **texto oficial a conferir**.
