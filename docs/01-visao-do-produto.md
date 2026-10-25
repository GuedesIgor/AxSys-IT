# 01 · Visão do produto

> **Situação:** rascunho validado · **Projeto:** AxPonto (nome de trabalho)

## Problema

Empresas pequenas e médias ainda controlam jornada em planilhas, papel ou relógios de parede. Isso gera esquecimentos, correções sem rastro, fechamento de folha lento e dificuldade de provar o que aconteceu em caso de dúvida.

## Proposta

Um sistema web em que o colaborador registra o ponto pelo navegador, o gestor resolve exceções e o RH fecha o mês com dados confiáveis e auditáveis.

## Objetivos

| # | Objetivo | Como saberemos que deu certo |
|---|---|---|
| O1 | Registrar o ponto em menos de 10 segundos | Do login ao comprovante em até 3 toques |
| O2 | Reduzir ajustes manuais | Dias incompletos visíveis no mesmo dia |
| O3 | Dar transparência | Colaborador vê o espelho sempre atualizado |
| O4 | Facilitar o fechamento | RH gera o consolidado do mês sem planilha |
| O5 | Manter rastro completo | Toda alteração fica na auditoria |

## Público

- **Colaboradores** de escritório e remotos, em computador ou celular.
- **Gestores** com equipes de 3 a 30 pessoas.
- **RH** que consolida jornadas e banco de horas.

## Dentro do escopo (primeira versão)

- Login com e-mail e senha
- Registro de ponto com 4 batidas (entrada, saída p/ intervalo, volta, saída)
- Espelho mensal com horas trabalhadas e saldo
- Solicitação e aprovação de ajustes
- Cadastro de colaboradores, perfis e jornadas
- Relatório mensal por colaborador
- Log de auditoria

## Fora do escopo (por enquanto)

- Aplicativo nativo para celular
- Reconhecimento facial e biometria
- Integração com folha de pagamento
- Geolocalização obrigatória
- Escalas complexas (12x36, turnos rotativos)
- Homologação legal de ponto eletrônico (Portaria 671/MTE). Precisa de estudo jurídico antes de qualquer promessa comercial. Ver [perguntas em aberto](08-perguntas-em-aberto.md).

## Princípios de produto

1. **Rápido para quem bate ponto todo dia.** A tela inicial do colaborador é o botão certo, grande, já destacado.
2. **Nada some.** Registros não são apagados, apenas ajustados com aprovação e justificativa.
3. **Cada pessoa vê o que precisa.** Permissões por perfil.
4. **Simples de explicar.** Linguagem clara em português, sem jargão técnico na interface.
