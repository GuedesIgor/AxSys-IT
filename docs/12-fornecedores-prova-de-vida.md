# 12 · Fornecedores de prova de vida e comparação facial

> **Status:** 🟡 critérios e plano de prova de conceito prontos. **Nenhum fornecedor foi escolhido.** Preços, disponibilidade em região brasileira e cartas de certificação **não foram verificados** e precisam ser pedidos a cada fornecedor.

Resolve a segunda parte de [Q-22](08-perguntas-em-aberto.md): qual serviço usar, onde guardar o modelo facial e a imagem.

## 1. Opções de arquitetura

| Opção | Como funciona | Vantagens | Riscos |
|---|---|---|---|
| **A. Serviço de terceiros (SaaS)** | O navegador envia a captura ao fornecedor, que devolve "viva" e "similaridade" | Rápido, prova de vida testada, menos código | Dado biométrico sai da AxSys, contrato e transferência internacional, custo por validação |
| **B. Nuvem com serviço de rosto** | Usar o serviço de reconhecimento da nuvem escolhida | Integra com a infraestrutura, região no Brasil possível | Verificar prova de vida em navegador, certificação e uso dos dados |
| **C. Motor próprio ou embarcado** | Modelo rodando no nosso servidor ou no aparelho | Controle total do dado | Alto custo, difícil certificar prova de vida, risco de fraude |
| **D. Biometria do aparelho (passkey/WebAuthn)** | O celular confirma com o rosto ou digital do próprio aparelho; o sistema recebe só "ok" | O rosto **nunca** sai do aparelho; ótima para LGPD | Não prova quem é a pessoa, só que o aparelho foi desbloqueado; pode ser emprestado |

**Recomendação:** começar com **A ou B para o rosto**, com contrato de operador, e usar **D como camada extra** (aparelho confiável). Evitar C na primeira versão.

## 2. Critérios de escolha

| # | Critério | Peso | Como verificar |
|---|---|:-:|---|
| 1 | Teste independente de ataque de apresentação (ISO/IEC 30107-3) | Alto | Pedir a **carta do laboratório** com data, versão e nível. Nota de mercado: iBeta é laboratório de testes, não certificador |
| 2 | Funciona no navegador do celular, sem aplicativo | Alto | Prova de conceito |
| 3 | Onde os dados ficam e se são usados para treinar modelo | Alto | Contrato e política |
| 4 | Taxa de falsa rejeição por faixa etária e tom de pele | Alto | Relatório de viés do fornecedor e teste próprio |
| 5 | Custo por validação (duas por pessoa por dia) | Médio | Cotação |
| 6 | Cadastro de rosto com opção de apagar sob demanda | Alto | API de exclusão |
| 7 | Suporte a pt-BR e acessibilidade | Médio | Teste |
| 8 | Suboperadores e certificações de segurança | Médio | Questionário |
| 9 | Plano de saída (exportar e apagar) | Médio | Contrato |

## 3. Candidatos para cotação

Lista de partida, **sem ranking**. O que foi confirmado nesta pesquisa está na coluna "Verificado".

| Fornecedor | Perfil | Verificado |
|---|---|---|
| iProov | Prova de vida especializada | Fontes de mercado o listam com testes ISO 30107-3 níveis 1 e 2. Falta carta oficial |
| Incode | Identidade e prova de vida | Material do fornecedor relata teste nível 3 em fev/2026 e fontes de mercado citam níveis 1 e 2. Falta carta oficial |
| FaceTec | Prova de vida 3D | Citado como testado pela iBeta; **nível não confirmado** |
| Unico | Fornecedor brasileiro de identidade digital | Não verificado |
| CAF, idwall | Fornecedores brasileiros de verificação | Não verificados |
| AWS (Face Liveness), Azure | Nuvem | Disponibilidade em região no Brasil e certificação **não verificadas** |
| Serpro Datavalid | Confere o rosto do cadastro com base oficial | Útil só na admissão, para validar a identidade inicial. Não verificado |

Fontes de mercado sobre certificação são em boa parte material de fornecedores. Para decidir, exija a carta do laboratório.

## 4. Plano de prova de conceito (2 semanas)

1. Escolher 3 fornecedores pelos critérios 1 a 3.
2. Integrar cada um ao protótipo do app real em ambiente de teste, **com dados sintéticos ou de voluntários que assinaram termo**.
3. Medir: tempo da validação, recusas indevidas (falsa rejeição) e tentativas de ataque com foto, vídeo e máscara.
4. Testar em aparelho Android de entrada, iPhone, notebook, luz fraca e contraluz.
5. Pedir carta de teste independente, relatório de viés, contrato de operador e lista de suboperadores.
6. Comparar custo mensal para 100, 500 e 2.000 colaboradores.
7. Decisão registrada em [07](07-registro-de-validacoes.md).

## 5. Onde guardar

| Dado | Onde | Como |
|---|---|---|
| Template facial | Base própria (ou do fornecedor, se for o desenho do contrato), separada dos dados de jornada | Cifrado, chave em cofre, região no Brasil |
| Foto da captura | Não guardar | Descartar logo após a comparação |
| Resultado da validação | Com a batida | Sem dado biométrico |
| Log de acesso | Registro de auditoria | Imutável |

## 6. Decisões em aberto

- Quem contrata o fornecedor: AxSys (como suboperadora) ou o cliente.
- Se o produto exigirá hospedagem somente no Brasil.
- Quem paga o custo por validação e como entra no preço.
