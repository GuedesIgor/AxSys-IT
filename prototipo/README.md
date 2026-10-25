# Protótipo AxPonto

Protótipo navegável do sistema de registro de ponto web. Serve para validar requisitos, telas e fluxos **antes** de construir o app real.

## Como abrir

- **Local:** abra [`index.html`](index.html) no navegador. Não precisa instalar nada. Para o GPS real, sirva por `localhost` ou `https`.
- **Artefato do Claude:** https://claude.ai/artifact/4FoMDu1U7nB9u7V3J4Nym8 (privado, exige acesso à conta dona do artefato)

## O que está no protótipo

| Área | Telas |
|---|---|
| Todos | Login, quiosque, Registrar ponto, Meu espelho, Meus ajustes, Ausências, Escalas, Alertas, Mural, Meu perfil |
| Gestor | Minha equipe, Espelho da equipe, Painel de exceções, Aprovações |
| RH / Admin | Visão geral, Painel de exceções, Aprovações, Colaboradores, Organização, Jornadas, Relatórios, Integrações, Configurações, Auditoria |

Cobertura detalhada em [docs/10 · Matriz de funcionalidades](../docs/10-matriz-de-funcionalidades.md).

## O que é real e o que é simulado

| Item | Situação |
|---|---|
| Regras de jornada, alertas, banco de horas, extras, escalas, ausências, fechamento, relatórios | **Funcionam** com dados fictícios |
| Cadastros (colaborador, setor, unidade, projeto, jornada), aprovações, configurações | **Funcionam** e mudam o comportamento do protótipo |
| Dados | Gerados ao abrir e guardados no navegador de quem testa (`localStorage`). **Reiniciar dados** no login recomeça |
| GPS | Tenta o GPS real. O visualizador de artefatos bloqueia, então há **simulador de local, aparelho e rede** |
| Selfie e reconhecimento facial | **Simulados** (sem câmera) |
| Mapa | Desenho esquemático. No app real será um mapa com tiles |
| Hora | Hora do navegador. No app real, hora do servidor sincronizada |
| E-mail, WhatsApp, Slack, Teams, folha, relógio físico, SSO | **Simulados**: só mudam o estado visual |
| Exportação | CSV por cópia de texto; AFD e AEJ em prévia ilustrativa |
| Senhas | Em texto, apenas para facilitar o teste |

Em Configurações, cada opção avisa se tem efeito no protótipo ("ativo no protótipo") ou se é só configuração.

## Roteiro de validação sugerido

1. Entre como **Ana**. Use o simulador para ficar "Em home office" e bata o ponto: o sistema exige selfie e justificativa por estar fora da área.
2. Abra **Meu espelho**, veja os alertas do mês, o botão **Local** e solicite ajuste no dia incompleto.
3. Entre como **Carlos** e abra **Aprovações** (ajuste e ausência) e o **Painel de exceções**. Mude um dia na **Escala**.
4. Entre como **Marina (RH)**, veja a **Visão geral**, edite uma **Ficha** e cadastre um colaborador. Gere os **Relatórios** e exporte um CSV.
5. Em **Configurações**, troque "fora da área" para Bloquear e volte a bater o ponto como Ana.
6. No login, abra o **modo quiosque** e bata o ponto do Bruno (AX-0006, PIN 6666).
7. Teste com **Sem internet** no simulador e depois **Sincronizar agora**.
8. Repita no celular ou com a janela estreita.

## Como atualizar

Ao mudar o protótipo, registre a decisão em [`docs/07-registro-de-validacoes.md`](../docs/07-registro-de-validacoes.md), atualize a [matriz](../docs/10-matriz-de-funcionalidades.md) e faça commit do novo `index.html` junto.
