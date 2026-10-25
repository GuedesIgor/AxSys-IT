# 07 · Registro de validações

Diário das decisões tomadas ao validar o protótipo. Mais recente no topo.

**Como ler:** ✅ decidido · 🔁 mudou depois de testar · ⏳ aguardando decisão

---

## Rodada 3 · Identidade visual AxSys

**Versão do protótipo:** v3 · **Pedido:** o visual estava feio e fora do padrão de negócio de alto nível; usar o logo e o estilo do site.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V3-01 | Marca | Usar o logo oficial do axsys.com.br no login e na barra lateral | Coerência com o site | ✅ |
| V3-02 | Cores e fonte | Adotar paleta navy e azul e a fonte Inter do site | Mesma linguagem visual da empresa | ✅ |
| V3-03 | Componentes | Cartões brancos de 20 px, botões pílula, barra lateral clara | Aspecto corporativo, limpo e com mais respiro | ✅ |
| V3-04 | Login | Painel de apresentação navy com 3 argumentos do produto | Primeira impressão de produto, não de tela de teste | ✅ |
| V3-05 | Relógio | Fonte leve e grande, sem fonte monoespaçada | Menos aspecto técnico, mais elegância | ✅ |
| V3-06 | Tema escuro | Derivado do navy do site | Manter a identidade nos dois temas | ✅ |

### Pendências desta rodada
- O logo do site é PNG com espaço entre o losango e o texto. Pedir à AxSys o arquivo vetorial (SVG) e uma versão para fundo escuro.
- Confirmar se o AxPonto terá marca própria ou usará só a AxSys IT.

---

## Rodada 2 · Localização obrigatória e mapa

**Versão do protótipo:** v2 · **Pedido:** a localização do aparelho deve ser obrigatória para bater o ponto, com mapa da pessoa.

| # | Tema | Decisão | Motivo | Status |
|---|---|---|---|---|
| V2-01 | Obrigatoriedade | Sem localização, os botões de ponto ficam bloqueados | Regra pedida pela AxSys | ✅ |
| V2-02 | Mapa | Cartão com mapa, precisão, sede e coordenadas na tela de ponto e no modal de confirmação | Pessoa confere onde está antes de gravar | ✅ |
| V2-03 | Dados gravados | Latitude, longitude e precisão ficam na batida e no comprovante | Rastro do registro | ✅ |
| V2-04 | Área da empresa | Mostrar "na área" ou "fora da área" (raio de 200 m), sem bloquear | Evita bloquear quem trabalha remoto até a regra ser definida | ⏳ ver Q-04 |
| V2-05 | Simulador | O protótipo inclui simulador de local e de negação de permissão | O visualizador de artefatos bloqueia o GPS real; sem o simulador não dá para validar o fluxo | ✅ só protótipo |
| V2-06 | Mapa no protótipo | Desenho esquemático, não mapa real | O artefato não carrega imagens de mapa de outros sites. No app real usar tiles (OpenStreetMap/Leaflet) | ✅ |

### Pendências desta rodada
- Gestor e RH ainda não veem o local de cada batida. Sugestão: ícone de pin no espelho abrindo o mapa.
- Definir se "fora da área" bloqueia, só sinaliza ou exige justificativa.
- LGPD: informar ao colaborador, antes do pedido do navegador, por que e quando a localização é coletada.

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
