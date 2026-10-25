# Protótipo AxPonto

Protótipo navegável do sistema de registro de ponto web. Serve para validar requisitos, telas e fluxos **antes** de construir o app real.

## Como abrir

- **Local:** abra [`index.html`](index.html) no navegador. Não precisa instalar nada.
- **Artefato do Claude:** https://claude.ai/artifact/4FoMDu1U7nB9u7V3J4Nym8 (privado, exige acesso à conta dona do artefato)

## O que está no protótipo

| Área | Telas |
|---|---|
| Todos | Login, Registrar ponto, Meu espelho, Meus ajustes |
| Gestor | Minha equipe, Espelho da equipe, Aprovações |
| RH / Admin | Visão geral, Aprovações, Colaboradores, Jornadas, Relatórios, Auditoria |

## O que é simulado

- Dados e usuários: todos fictícios, gerados ao abrir (ver [usuários de teste](../docs/04-perfis-e-usuarios-ficticios.md)).
- Hora do registro: hora do navegador.
- Localização: o protótipo pede o GPS de verdade. O visualizador de artefatos bloqueia essa permissão, então há um **simulador de local** (e de negação). Para testar o GPS real, abra `index.html` direto no navegador (precisa de `localhost` ou `https`).
- Mapa: desenho esquemático com a posição, a precisão e a sede. No app real será um mapa com tiles.
- Sede de exemplo: Av. Paulista, São Paulo (coordenadas fictícias).
- Persistência: guardada no navegador de quem testa (`localStorage`). Use **Reiniciar dados** no login para recomeçar.
- Senhas: em texto, apenas para facilitar o teste.

## O que ainda não existe

Recuperação de senha, edição de jornadas, exportação CSV/PDF, e-mails, feriados, férias e abonos. Veja [requisitos](../docs/02-requisitos.md) para o estado de cada item.

## Roteiro de validação sugerido

1. Entre como **Ana** e bata o próximo ponto. Confira o comprovante.
2. Abra **Meu espelho** e solicite ajuste no dia incompleto.
3. Entre como **Carlos**, abra **Aprovações** e aprove. Volte ao espelho da Ana.
4. Entre como **Marina (RH)**, veja a **Visão geral**, cadastre um colaborador e confira a **Auditoria**.
5. Tente entrar como **Fábio** (inativo) e erre a senha de outra conta 3 vezes.
6. Repita no celular ou com a janela estreita.

## Como atualizar

Ao mudar o protótipo, registre a decisão em [`docs/07-registro-de-validacoes.md`](../docs/07-registro-de-validacoes.md) e faça commit do novo `index.html` junto.
