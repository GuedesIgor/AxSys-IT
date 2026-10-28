# 07 · Registro de validações

Diário das decisões tomadas ao validar o protótipo. Mais recente no topo.

**Como ler:** Decidido, Mudou depois de testar, Aguardando decisão

---

## Rodada 12 · Hospedagem própria no IIS

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V12-01 | Hospedagem | Servidor próprio SRVAD1 com IIS, sem provedor de terceiros | Diretriz de não ter fornecedores externos | Decidido |
| V12-02 | Alerta de segurança | Não expor o app em controlador de domínio; HTTPS obrigatório; cópias fora do local | Dado biométrico e exigência dos navegadores | Pendente de confirmação |
| V12-03 | SLA | Sugestão de 99% no piloto, subindo depois de medir | Um servidor e um link dificilmente sustentam 99,5% | Aguardando decisão |
| V12-04 | Protótipo | Fonte embutida e configuração `web.config` para o IIS. Sem requisição externa | Não depender de terceiros | Feito |

---

## Rodada 11 · Sem fornecedores externos

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V11-01 | Diretriz | A AxSys desenvolve todas as funções por conta própria, sem fornecedores externos | Decisão do dono | Decidido |
| V11-02 | Exceção de infraestrutura | Hospedagem e envio de e-mail continuam de terceiros, sem acesso ao rosto | Não existe alternativa prática | Decidido |
| V11-03 | Certificação | Plano em três passos: testes internos, teste independente de fraude e REP-P no INPI | Só se diz "certificado" com carta ou registro | Decidido |
| V11-04 | Modelo facial | Risco de treino: dados de rostos e licenças | LGPD e licença comercial | Pendente (Q-26) |

---

## Rodada 10 · Leitor facial próprio e aprovação do advogado

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V10-01 | Aprovação jurídica | Segundo o dono, o advogado leu o resumo e aprovou as minutas. Falta a assinatura dele (OAB/SP nº 389.139 já informada) | Só o advogado assina | Aguardando assinatura |
| V10-02 | Leitor facial | Desenvolvimento próprio, com desafios (piscar, virar o rosto, sorrir) verificados no servidor. Sem fornecedor externo na primeira versão | Decisão do dono; evita custo por validação | Decidido |
| V10-03 | Compromisso de teste | Relatório interno de testes de fraude e de viés antes de vender. Não prometer "prova de vida certificada" | Sem certificação independente | Decidido |
| V10-04 | Licenças | Conferir a licença comercial de cada modelo e biblioteca | Risco de uso indevido | Pendente |

---

## Rodada 9 · Pacote jurídico e exceções à validação facial

**Versão do protótipo:** v9 · **Pedido:** resolver as pendências jurídicas e a alternativa para quem não pode usar a câmera.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V9-01 | Pacote jurídico | Criados [docs/11](11-pacote-juridico-lgpd.md) (RIPD, ROPA, retenção, aviso, contratos, incidente, perguntas ao advogado) e [docs/12](12-leitor-facial-proprio.md) (critérios e prova de conceito) | Q-13 e Q-22 | Parcial: aguarda advogado |
| V9-02 | Batida sem validação facial | Pendente, com justificativa dos dois lados, mesmo fluxo e prazo do ponto sem localização | Evita travar a jornada e mantém decisão humana | Decidido|
| V9-03 | Método alternativo | RH autoriza por pessoa, sem registrar o motivo, com revisão em 180 dias; confirmação por PIN | Acessibilidade sem tratar dado de saúde | Decidido|
| V9-04 | Marcação imediata | Requisito de gravar de imediato a marcação recebida, mesmo pendente (RNF-19) | Risco com a Portaria 671 | Parcial: conferir com advogado |
| V9-06 | Modelo de negócio | Produto vendido como serviço a empresas. Cada cliente é controlador e indica o encarregado; a AxSys é operadora. Resolve a Q-03 | Decisão do dono | Decidido|
| V9-07 | Dados do contrato | Foro de Ilha Solteira (SP). CNPJ, razão social e endereço pendentes (empresa ainda não aberta). SLA de 99,5%, contrato mensal sem fidelidade, teste de 30 dias. Cláusula de limitação de responsabilidade redigida (12 e 24 meses). Preço aguarda cotação | Decisões do dono e estudo de mercado | Decidido; preço aguardando |
| V9-05 | Base legal | Art. 11, II, "g" como principal, com alternativa equivalente garantida | ANPD ainda não tem posição sobre ponto biométrico | Parcial: aguarda advogado |

### Pendências desta rodada
- Revisão e assinatura do advogado sobre o pacote.
- Escolha do fornecedor de prova de vida pela prova de conceito.

---

## Rodada 8 · Validação facial obrigatória com prova de vida

**Versão do protótipo:** v8 · **Pedido:** validar o rosto com teste de vida antes de bater o ponto, e exigir o cadastro facial para cadastrar usuário.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V8-01 | Validação na batida | Obrigatória e sempre ativa, antes de confirmar, no navegador, no quiosque e no ponto sem localização | Pedido da AxSys; substitui a selfie opcional | Decidido: simulada |
| V8-02 | Prova de vida | Dois desafios sorteados a cada tentativa (piscar, virar a cabeça, sorrir, abrir a boca) | Impede foto, vídeo e máscara | Decidido: simulada |
| V8-03 | Falhas | Prova reprovada ou rosto que não confere: recusa, auditoria e 3 tentativas. Depois bloqueia | Antifraude sem travar para sempre: o RH desbloqueia | Decidido|
| V8-04 | Cadastro | Não é possível criar usuário sem cadastrar o rosto com prova de vida. O RH pode refazer na edição | Pedido da AxSys | Decidido|
| V8-05 | Sem rosto cadastrado | A pessoa não bate o ponto e é orientada a procurar o RH | Evita validar contra nada | Decidido|
| V8-06 | Configuração | A opção de ligar e desligar a selfie foi removida | A validação passou a ser obrigatória | Decidido|
| V8-07 | Dados de teste | Dados do protótipo renovados (nova versão de armazenamento); os 10 usuários já têm rosto cadastrado | Novo campo no cadastro | Decidido|

### Pendências desta rodada
- Q-13 ficou mais crítica: a biometria deixou de ser opcional. O parecer jurídico vira requisito de lançamento.
- Q-22: método alternativo para quem não pode usar a câmera e como será a prova de vida real.

---

## Rodada 7 · Prazo do gestor no ponto sem localização

**Versão do protótipo:** v7 · **Origem:** respostas da AxSys à pergunta Q-21.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V7-01 | Prazo | 2 dias úteis, configurável de 1 a 10 em Configurações. Não há prazo legal específico; vale a prática comum de aprovações de ponto | A AxSys pediu o prazo legal ou o mais usado | Decidido|
| V7-02 | Depois do prazo | Lembrete no último dia; vencido, o pedido fica marcado "escalado ao RH" | O ponto não pode ficar parado até o fechamento | Decidido: simulado (sem e-mail ou push) |
| V7-03 | Limite mensal | Sem limite por pessoa | Decisão da AxSys | Decidido|

---

## Rodada 6 · Ponto sem localização depende do gestor

**Versão do protótipo:** v6 · **Pedido:** ponto sem localização fica pendente de aprovação do gestor e só é registrado depois; quem bate justifica; o gestor vê a justificativa e também justifica.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V6-01 | Caminho sem localização | Sem permissão, a pessoa pode solicitar o ponto sem localização. Ele **não é registrado** até a aprovação | Resolve a pergunta Q-20 | Decidido|
| V6-02 | Justificativa de quem bate | Obrigatória (mínimo 10 caracteres), mais selfie quando ativa | Responsabilização e antifraude | Decidido|
| V6-03 | Aviso ao gestor | Cartão em destaque em Aprovações, contador no menu e grupo no painel de exceções | O gestor não pode deixar de ver | Decidido|
| V6-04 | Decisão do gestor | Vê justificativa, motivo técnico, aparelho e hora, e precisa justificar a aprovação ou a recusa | Pedido da AxSys | Decidido|
| V6-05 | Efeito no espelho | Aprovado entra com marca "sem localização", com as duas justificativas. Recusado não entra | Transparência e rastro | Decidido|
| V6-06 | Quem decide | Gestor direto, RH e Admin. Ninguém decide o próprio ponto; gestores são decididos por RH e Admin | Evita autoaprovação | Decidido|
| V6-07 | Configuração | Opção de bloquear em vez de enviar para aprovação | Clientes que não aceitam exceção | Decidido|
| V6-08 | Dados de teste | Os dados do protótipo foram renovados (nova versão de armazenamento) | Incluir o cenário de teste da Elisa | Decidido|

### Pendências desta rodada
- Resolvidas na [Rodada 7](#rodada-7--prazo-do-gestor-no-ponto-sem-localização).

---

## Rodada 5 · Decisões sobre selfie, custo e plataforma

**Versão do protótipo:** v5 · **Origem:** respostas da AxSys às perguntas Q-13, Q-16 e Q-17.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V5-01 | Selfie | Manter a selfie **ativada por padrão**, sempre configurável, **desde que a validação jurídica confirme a base legal** | A AxSys aceita se for prática comum e legal. Prática comum: sim (UKG, Connecteam, Jibble, Pontomais). Legalidade no ponto de empregados: sem posição consolidada | Aguardando: depende de parecer jurídico |
| V5-02 | Selfie: salvaguardas | Aviso na hora da captura, alternativa por PIN ou QR, guardar só o necessário, prazo de retenção definido | Reduz risco enquanto o parecer não sai | Decidido: aviso no protótipo; resto vai para a especificação |
| V5-03 | Valor da hora | Sair do cadastro padrão. Vira o **módulo opcional de custo de mão de obra**, desligado por padrão, visível só a RH e Admin | O valor da hora é dado de folha, não de ponto. Reduz exposição de dado sensível | Decidido|
| V5-04 | Plataforma | O AxPonto é um **app web responsivo instalável (PWA)** que funciona em qualquer navegador moderno e em qualquer aparelho | Requisito da AxSys. Um só produto serve computador, Android e iPhone | Decidido: requisito registrado |
| V5-05 | App nativo | Não é necessário na primeira versão. Só entra se uma função exigir (rastreio em segundo plano, controle de aparelho do quiosque) | Evita três bases de código | Decidido|

---

## Rodada 4 · Benchmark de mercado e cadastro completo

**Versão do protótipo:** v4 · **Pedido:** colaborador com setor, gestor e demais informações; estudar os 10 sistemas de ponto mais usados e trazer todas as funções.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V4-01 | Ficha | Colaborador com 14 campos: matrícula, CPF, setor, cargo, gestor, unidade, contrato, admissão, centro de custo, valor da hora, PIN e outros | Pedido da AxSys | Decidido|
| V4-02 | Benchmark | Estudar 10 sistemas globais e referências do Brasil; registrar em [09](09-benchmark-concorrentes.md) | Não deixar função de fora | Decidido|
| V4-03 | Catálogo | 104 funções em [10](10-matriz-de-funcionalidades.md), cada uma com situação no protótipo | Rastreabilidade | Decidido|
| V4-04 | Quiosque | Modo quiosque com matrícula e PIN | Presente em UKG, Clockify, Connecteam, Jibble, Pontomais | Decidido|
| V4-05 | Antifraude | Selfie, cerca por unidade, aviso de aparelho diferente | Connecteam, Jibble, Pontomais | Decidido: simulado |
| V4-06 | Fora da área | Três modos configuráveis; padrão: exigir justificativa | Responde parte da Q-04 sem bloquear quem trabalha fora | Aguardando: confirmar padrão |
| V4-07 | Regras CLT | Alertas de intervalo, 6h sem pausa, interjornada, extras e jornada longa | Exigência trabalhista brasileira | Decidido|
| V4-08 | Banco de horas | Saldo acumulado com folga compensatória | Pontomais e UKG | Decidido|
| V4-09 | Escalas e ausências | Escala semanal, férias com saldo, atestado, licença, abono | Deputy, When I Work, Pontomais | Decidido|
| V4-10 | Fechamento | Espelho assinado, aprovado e fechado, travando o mês | Pontomais e UKG | Decidido|
| V4-11 | Exceções | Painel único com nove tipos de problema | Equivalente sem IA ao assistente do Deputy | Decidido|
| V4-12 | Relatórios | Oito relatórios, exportação CSV por cópia | Pontomais, Deputy, Clockify | Decidido|
| V4-13 | Integrações | Conectores simulados | UKG, Buddy Punch, QuickBooks Time, Pontomais | Parcial: simulado |
| V4-14 | Configurações | Cada opção avisa se tem efeito no protótipo | Transparência na validação | Decidido|

### Pendências desta rodada
- Perguntas Q-13 a Q-19 em [08](08-perguntas-em-aberto.md).
- Funções marcadas como Pendente na matriz precisam de decisão de escopo.

---

## Rodada 3 · Identidade visual AxSys

**Versão do protótipo:** v3 · **Pedido:** o visual estava feio e fora do padrão de negócio de alto nível; usar o logo e o estilo do site.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V3-01 | Marca | Usar o logo oficial do axsys.com.br no login e na barra lateral | Coerência com o site | Decidido|
| V3-02 | Cores e fonte | Adotar paleta navy e azul e a fonte Inter do site | Mesma linguagem visual da empresa | Decidido|
| V3-03 | Componentes | Cartões brancos de 20 px, botões pílula, barra lateral clara | Aspecto corporativo, limpo e com mais respiro | Decidido|
| V3-04 | Login | Painel de apresentação navy com 3 argumentos do produto | Primeira impressão de produto, não de tela de teste | Decidido|
| V3-05 | Relógio | Fonte leve e grande, sem fonte monoespaçada | Menos aspecto técnico, mais elegância | Decidido|
| V3-06 | Tema escuro | Derivado do navy do site | Manter a identidade nos dois temas | Decidido|

### Pendências desta rodada
- O logo do site é PNG com espaço entre o losango e o texto. Pedir à AxSys o arquivo vetorial (SVG) e uma versão para fundo escuro.
- Confirmar se o AxPonto terá marca própria ou usará só a AxSys IT.

---

## Rodada 2 · Localização obrigatória e mapa

**Versão do protótipo:** v2 · **Pedido:** a localização do aparelho deve ser obrigatória para bater o ponto, com mapa da pessoa.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V2-01 | Obrigatoriedade | Sem localização, os botões de ponto ficam bloqueados | Regra pedida pela AxSys | Decidido|
| V2-02 | Mapa | Cartão com mapa, precisão, sede e coordenadas na tela de ponto e no modal de confirmação | Pessoa confere onde está antes de gravar | Decidido|
| V2-03 | Dados gravados | Latitude, longitude e precisão ficam na batida e no comprovante | Rastro do registro | Decidido|
| V2-04 | Área da empresa | Mostrar "na área" ou "fora da área" (raio de 200 m), sem bloquear | Evita bloquear quem trabalha remoto até a regra ser definida | Aguardando: ver Q-04 |
| V2-05 | Simulador | O protótipo inclui simulador de local e de negação de permissão | O visualizador de artefatos bloqueia o GPS real; sem o simulador não dá para validar o fluxo | Decidido: só protótipo |
| V2-06 | Mapa no protótipo | Desenho esquemático, não mapa real | O artefato não carrega imagens de mapa de outros sites. No app real usar tiles (OpenStreetMap/Leaflet) | Decidido|

### Pendências desta rodada
- Gestor e RH ainda não veem o local de cada batida. Sugestão: ícone de pin no espelho abrindo o mapa.
- Definir se "fora da área" bloqueia, só sinaliza ou exige justificativa.
- LGPD: informar ao colaborador, antes do pedido do navegador, por que e quando a localização é coletada.

---

## Rodada 1 · Estrutura inicial

**Versão do protótipo:** v1 · **Origem:** artefato do Claude, arquivo `prototipo/index.html`

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V1-01 | Nome | Usar **AxPonto** como nome de trabalho | Curto e ligado à marca AxSys | Aguardando: confirmar |
| V1-02 | Perfis | Quatro perfis: Administrador, RH, Gestor, Colaborador | Cobre quem registra, aprova e administra | Decidido|
| V1-03 | Batidas | Quatro por dia, na ordem fixa | Evita registro fora de sequência | Decidido|
| V1-04 | Tela inicial | Colaborador cai direto em "Registrar ponto" | Ação mais frequente deve estar a um toque | Decidido|
| V1-05 | Confirmação | Pedir confirmação antes de gravar | Evita clique acidental, já que o registro é imutável | Decidido|
| V1-06 | Comprovante | Mostrar comprovante numerado após cada batida | Dá segurança ao colaborador | Decidido|
| V1-07 | Ajustes | Aprovação pelo gestor direto; RH e Admin também podem | Evita fila parada quando o gestor está ausente | Decidido|
| V1-08 | Bloqueio | 3 senhas erradas bloqueiam a conta | Padrão básico de segurança | Decidido|
| V1-09 | Jornadas | Três modelos: Comercial 8h, Reduzida 6h, Estágio 4h | Cobrem os casos mais comuns | Decidido|
| V1-10 | Layout | Barra lateral por perfil; vira faixa no celular | Navegação clara sem esconder funções | Decidido|
| V1-11 | Tema | Claro e escuro automáticos | Conforto de uso | Decidido|
| V1-12 | Dados de teste | 10 usuários fictícios com cenários prontos | Permite validar fluxos sem montar dados | Decidido|

### Pendências desta rodada
- Fluxo de recuperação de senha ainda não prototipado (RF-04).
- Edição de jornadas pelo RH ainda não prototipada (RF-46).
- Exportação de relatórios ainda não prototipada (RF-48).

---

## Modelo para novas rodadas

```markdown
## Rodada N · Tema

**Versão do protótipo:** vN · **Data:** AAAA-MM-DD

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| VN-01 | ... | ... | ... | Decidido / Mudou / Aguardando |
```
