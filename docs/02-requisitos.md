# 02 · Requisitos

> **Legenda de prioridade:** 🔴 Essencial · 🟡 Importante · 🟢 Desejável
> **Legenda de validação:** ✅ visto no protótipo · 🟡 parcial · ⬜ ainda não prototipado

## Requisitos funcionais

### Acesso

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-01 | Login com e-mail e senha | 🔴 | ✅ |
| RF-02 | Bloquear a conta após 3 senhas erradas seguidas | 🟡 | ✅ |
| RF-03 | Impedir login de usuário inativo, com mensagem clara | 🔴 | ✅ |
| RF-04 | Recuperar e trocar senha pelo próprio usuário | 🟡 | ✅ (recuperação simulada) |
| RF-05 | Sair da sessão a qualquer momento | 🔴 | ✅ |

### Registro de ponto

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-10 | Mostrar relógio e os 4 registros do dia | 🔴 | ✅ |
| RF-11 | Destacar apenas o próximo registro válido | 🔴 | ✅ |
| RF-12 | Pedir confirmação antes de gravar | 🟡 | ✅ |
| RF-13 | Emitir comprovante com número, data, hora e origem | 🔴 | ✅ |
| RF-14 | Mostrar horas trabalhadas e progresso da jornada do dia | 🟡 | ✅ |
| RF-15 | Gravar a hora do servidor, não a do aparelho | 🔴 | ⬜ (simulada) |
| RF-16 | **Localização do aparelho obrigatória**: sem permissão, o botão de ponto normal fica bloqueado. O único caminho é o ponto sem localização (RF-74), que depende de aprovação | 🔴 | ✅ |
| RF-17 | Mostrar mapa com a posição da pessoa, círculo de precisão e a sede | 🔴 | ✅ (mapa esquemático) |
| RF-18 | Gravar latitude, longitude e precisão em cada batida e no comprovante | 🔴 | ✅ |
| RF-19 | Indicar se o registro foi dentro ou fora da área da empresa (apenas informativo) | 🟡 | ✅ |

### Espelho de ponto

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-20 | Listar o mês dia a dia com batidas, total, saldo e situação | 🔴 | ✅ |
| RF-21 | Resumo do mês: horas, saldo, faltas, dias incompletos | 🔴 | ✅ |
| RF-22 | Escolher entre os últimos 3 meses | 🟡 | ✅ |
| RF-23 | Destacar fins de semana e folgas | 🟢 | ✅ |
| RF-24 | Atalho "Ajustar" em dias com problema | 🟡 | ✅ |

### Ajustes

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-30 | Solicitar ajuste com dia, tipo de batida, horário e justificativa | 🔴 | ✅ |
| RF-31 | Exigir justificativa com ao menos 10 caracteres | 🟡 | ✅ |
| RF-32 | Gestor aprova ou recusa; recusa pede motivo | 🔴 | ✅ |
| RF-33 | Aprovação altera o espelho e marca a batida como "ajuste" | 🔴 | ✅ |
| RF-34 | Colaborador acompanha o status das solicitações | 🟡 | ✅ |
| RF-35 | Notificar por e-mail quando houver decisão | 🟢 | ⬜ |

### Gestão e RH

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-40 | Gestor vê a equipe: quem está trabalhando, no intervalo, ausente | 🔴 | ✅ |
| RF-41 | Gestor abre o espelho de cada pessoa da equipe (leitura) | 🟡 | ✅ |
| RF-42 | RH vê painel com presença agora, pendências e inconsistências | 🟡 | ✅ |
| RF-43 | RH cadastra colaborador com perfil, gestor e jornada | 🔴 | ✅ |
| RF-44 | RH ativa/desativa usuário e redefine senha | 🔴 | ✅ |
| RF-45 | RH consulta modelos de jornada | 🟡 | ✅ (leitura) |
| RF-46 | RH edita e cria jornadas | 🟡 | 🟡 (criação pronta) |
| RF-47 | Relatório mensal por colaborador | 🔴 | ✅ |
| RF-48 | Exportar relatório em CSV e PDF | 🟡 | 🟡 (CSV por cópia de texto) |
| RF-49 | Log de auditoria de ações sensíveis | 🔴 | ✅ |

### Requisitos adicionados pelo benchmark (Rodada 4)

Origem de cada um na [matriz de funcionalidades](10-matriz-de-funcionalidades.md).

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-50 | Ficha do colaborador com matrícula, CPF, setor, cargo, gestor, unidade, perfil, jornada, contrato, admissão, centro de custo, valor da hora e PIN | 🔴 | ✅ |
| RF-51 | RH gerencia setores, unidades, projetos e jornadas | 🔴 | ✅ |
| RF-52 | Quiosque compartilhado com matrícula e PIN | 🟡 | ✅ |
| RF-53 | Validação facial com prova de vida obrigatória antes de toda batida (web, quiosque e ponto sem localização). Não pode ser desligada | 🔴 | 🟡 simulada |
| RF-54 | Cerca virtual por unidade, raio configurável, e três modos para batida fora da cerca (permitir, justificar, bloquear) | 🔴 | ✅ |
| RF-55 | Alertar quando a batida vem de aparelho diferente do habitual | 🟡 | ✅ |
| RF-56 | Registrar offline e sincronizar depois | 🟡 | ✅ |
| RF-57 | Escolher projeto na entrada e gerar horas por projeto | 🟢 | ✅ |
| RF-58 | Alertas automáticos: atraso, saída antecipada, intervalo curto, mais de 6h sem pausa, hora extra acima do limite, jornada acima de 10h, interjornada menor que 11h | 🔴 | ✅ |
| RF-59 | Separar hora extra 50% e 100% e calcular adicional noturno | 🔴 | ✅ |
| RF-60 | Banco de horas com saldo e folga compensatória | 🔴 | ✅ |
| RF-61 | Calendário de feriados nacionais no cálculo | 🔴 | ✅ |
| RF-62 | Escala semanal com folga, plantão, férias e feriados | 🟡 | ✅ |
| RF-63 | Ausências (férias, atestado, folga, licença, abono, troca) com aprovação e saldo de férias | 🔴 | ✅ |
| RF-64 | Espelho assinado pelo colaborador, aprovado pelo gestor e fechado pelo RH, com mês travado | 🔴 | ✅ |
| RF-65 | Painel de exceções para gestor e RH | 🔴 | ✅ |
| RF-66 | Relatórios: consolidado, extras, atrasos e faltas, banco de horas, projetos, localização, eventos de folha e AFD/AEJ | 🔴 | ✅ (AFD/AEJ em prévia) |
| RF-67 | Integrações com folha, chat, agenda, SSO e relógios físicos | 🟡 | 🟡 simuladas |
| RF-68 | Configurações de política de ponto, métodos de registro e segurança | 🔴 | ✅ |
| RF-69 | Mural de avisos por empresa ou setor | 🟢 | ✅ |
| RF-70 | Perfil com dados, QR Code, troca de senha e preferências de notificação | 🟡 | ✅ |
| RF-71 | Ver o local de cada batida no espelho (gestor e RH) | 🟡 | ✅ |
| RF-72 | Módulo opcional de custo de mão de obra (valor da hora, custo estimado e valores nos eventos de folha), desligado por padrão e visível só a RH e Admin | 🟢 | ✅ |
| RF-73 | Aviso de finalidade na captura da selfie e método alternativo (PIN ou QR) | 🔴 | 🟡 aviso feito, alternativa no app |

### Ponto sem localização (Rodada 6)

| ID | Requisito | Prioridade | Protótipo |
|---|---|---|---|
| RF-74 | Sem a localização liberada, a pessoa pode **solicitar** o ponto sem localização. Ele **não é registrado** até o gestor aprovar | 🔴 | ✅ |
| RF-75 | A pessoa que bate **deve justificar** (mínimo 10 caracteres). A validação facial com prova de vida também é obrigatória | 🔴 | ✅ |
| RF-76 | O gestor recebe aviso na lista de pendências e no contador do menu, com a justificativa, o motivo técnico, o aparelho e a hora batida, **antes de decidir** | 🔴 | ✅ |
| RF-77 | O gestor **deve justificar** a aprovação ou a recusa (mínimo 10 caracteres). A decisão e as duas justificativas ficam no histórico e na auditoria | 🔴 | ✅ |
| RF-78 | Ponto aprovado entra no espelho marcado como "sem localização" e mostra quem aprovou e por quê. Recusado não entra | 🔴 | ✅ |
| RF-79 | Ninguém decide o próprio ponto. Para gestores, decidem RH e Admin | 🔴 | ✅ |
| RF-80 | Configuração para **bloquear** o ponto sem localização em vez de enviá-lo para aprovação | 🟡 | ✅ |
| RF-81 | Prazo para o gestor decidir (padrão 2 dias úteis, configurável): lembrete no último dia e escalonamento ao RH quando vence | 🟡 | ✅ |
| RF-82 | Cadastro facial com prova de vida obrigatório para cadastrar usuário. Sem ele o cadastro não é salvo | 🔴 | 🟡 simulada |
| RF-83 | Prova de vida com desafios aleatórios (piscar, virar a cabeça, sorrir, abrir a boca) a cada tentativa | 🔴 | 🟡 simulada |
| RF-84 | Rosto que não confere ou prova de vida reprovada impede a batida. Após 3 tentativas a validação bloqueia e a pessoa procura o RH. Cada recusa vai para a auditoria | 🔴 | ✅ |
| RF-85 | Usuário sem rosto cadastrado não bate o ponto e vê aviso para procurar o RH. O RH pode refazer o cadastro facial na edição | 🔴 | ✅ |
| RF-86 | Falha na validação facial (3 recusas), câmera indisponível ou cadastro facial pendente: a pessoa pode pedir a batida **sem validação facial**. Ela fica pendente, com justificativa dela e do gestor | 🔴 | ✅ |
| RF-87 | O RH pode autorizar **método alternativo** (PIN) a uma pessoa, sem registrar o motivo. Revisão a cada 180 dias, com aviso na ficha quando vencida | 🔴 | ✅ |
| RF-88 | Batidas aprovadas sem validação facial ou por método alternativo ficam marcadas no espelho (s/f, alt), na ficha do dia e nos alertas | 🟡 | ✅ |
| RF-89 | Aviso ao colaborador sobre o tratamento do rosto, com alternativa sem necessidade de explicação | 🔴 | 🔴 texto pronto em [docs/11](11-pacote-juridico-lgpd.md), tela no app real |
| RF-90 | Onboarding do cliente com o nome e o contato do encarregado (DPO) da empresa, exibidos no aviso ao colaborador | 🔴 | 🔴 app real |

## Requisitos não funcionais

| ID | Requisito | Meta |
|---|---|---|
| RNF-01 | Funciona em celular e computador | Layout responsivo desde 360 px |
| RNF-02 | Desempenho | Tela de ponto carrega em menos de 2 s em 4G |
| RNF-03 | Segurança de senha | Armazenamento com hash forte, nunca em texto puro |
| RNF-04 | Sessão | Expira por inatividade (valor a definir) |
| RNF-05 | Integridade | Registros imutáveis; só ajuste com trilha |
| RNF-06 | Acessibilidade | Contraste AA, navegação por teclado, rótulos em formulários |
| RNF-07 | Tema | Claro e escuro conforme o sistema do usuário |
| RNF-08 | Privacidade | Seguir a LGPD: coletar só o necessário |
| RNF-09 | Disponibilidade | Meta inicial de 99,5% (a validar) |
| RNF-10 | Idioma | Português do Brasil, fuso America/Sao_Paulo |
| RNF-11 | Mapa real no app | Mapa com tiles (ex.: OpenStreetMap com Leaflet). O protótipo usa um desenho esquemático |
| RNF-12 | Contexto seguro | Geolocalização e câmera exigem HTTPS |
| RNF-13 | **Qualquer navegador e qualquer aparelho** | Funciona nas duas últimas versões de Chrome, Edge, Firefox, Safari e Samsung Internet, em Windows, macOS, Linux, Android e iOS, de 360 px de largura até telas grandes |
| RNF-14 | App web instalável (PWA) | Instalável na tela inicial, abre em tela cheia e tem o mesmo comportamento em todos os aparelhos |
| RNF-15 | Sem dependência de app nativo | Toda função da primeira versão roda no navegador. Câmera e GPS usam as permissões do próprio navegador |
| RNF-16 | Caminho alternativo quando o aparelho ou a câmera não permite | Ver [Q-20](08-perguntas-em-aberto.md) e [Q-22](08-perguntas-em-aberto.md) |
| RNF-17 | Template facial apagado no desligamento (até 30 dias) | Ver [docs/11](11-pacote-juridico-lgpd.md), seção 7 |
| RNF-18 | Nenhuma foto de batida guardada por padrão. Só o modelo matemático e o resultado | Minimização (LGPD art. 6, III) |
| RNF-19 | Gravar de imediato a marcação recebida, mesmo pendente, em registro imutável | Mitiga o risco da Portaria 671 (ver docs/11, seção 12) |
| RNF-20 | Multiempresa: cada cliente só acessa os próprios dados, com isolamento na base | Produto vendido como serviço ([Q-03](08-perguntas-em-aberto.md)) |

## Rastreabilidade rápida

```mermaid
flowchart LR
    O1[O1 Registro rápido] --> RF10 & RF11 & RF12 & RF13
    O3[O3 Transparência] --> RF20 & RF21 & RF34
    O4[O4 Fechamento] --> RF47 & RF48
    O5[O5 Rastro] --> RF49 & RNF05
```
