# 07 · Registro de validações

Diário das decisões tomadas ao validar o protótipo. Mais recente no topo.

**Como ler:** ✅ decidido · 🔁 mudou depois de testar · ⏳ aguardando decisão

---

## Rodada 1 · Estrutura inicial

**Versão do protótipo:** v1 · **Origem:** artefato do Claude, arquivo `prototipo/index.html`

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V1-01 | Nome | Usar **AxPonto** como nome de trabalho | Curto e ligado à marca AxSys | ⏳ confirmar |
| V1-02 | Perfis | Quatro perfis: Administrador, RH, Gestor, Colaborador | Cobre quem registra, aprova e administra | ✅ |
| V1-03 | Batidas | Quatro por dia, na ordem fixa | Evita registro fora de sequência | ✅ |
| V1-04 | Tela inicial | Colaborador cai direto em "Registrar ponto" | Ação mais frequente deve estar a um toque | ✅ |
| V1-05 | Confirmação | Pedir confirmação antes de gravar | Evita clique acidental, já que o registro é imutável | ✅ |
| V1-06 | Comprovante | Mostrar comprovante numerado após cada batida | Dá segurança ao colaborador | ✅ |
| V1-07 | Ajustes | Aprovação pelo gestor direto; RH e Admin também podem | Evita fila parada quando o gestor está ausente | ✅ |
| V1-08 | Bloqueio | 3 senhas erradas bloqueiam a conta | Padrão básico de segurança | ✅ |
| V1-09 | Jornadas | Três modelos: Comercial 8h, Reduzida 6h, Estágio 4h | Cobrem os casos mais comuns | ✅ |
| V1-10 | Layout | Barra lateral por perfil; vira faixa no celular | Navegação clara sem esconder funções | ✅ |
| V1-11 | Tema | Claro e escuro automáticos | Conforto de uso | ✅ |
| V1-12 | Dados de teste | 10 usuários fictícios com cenários prontos | Permite validar fluxos sem montar dados | ✅ |

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
| VN-01 | ... | ... | ... | ✅ / 🔁 / ⏳ |
```
