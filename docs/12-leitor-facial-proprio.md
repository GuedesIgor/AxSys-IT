# 12 · Leitor facial próprio e prova de vida

> **Status:** Em elaboração: critérios e plano de prova de conceito prontos. **Nenhum fornecedor foi escolhido.** Preços, disponibilidade em região brasileira e cartas de certificação **não foram verificados** e precisam ser pedidos a cada fornecedor.

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
| Foto de evidência da batida | Base própria, separada, em servidor no Brasil | Um quadro (sem vídeo), cifrada com chave própria, apagada automaticamente em 30 dias. Acesso restrito e registrado. Contestação aberta suspende a exclusão |
| Resultado da validação | Com a batida | Sem dado biométrico |
| Log de acesso | Registro de auditoria | Imutável |

## 6. Decisões em aberto

- Quem contrata o fornecedor: AxSys (como suboperadora) ou o cliente.
- Se o produto exigirá hospedagem somente no Brasil.
- Quem paga o custo por validação e como entra no preço.

## 7. Decisão: tudo desenvolvido pela AxSys (Rodadas 10 e 11)

**Diretriz do dono (Rodada 11):** a AxSys desenvolve por conta própria todas as funções do produto, **sem fornecedores externos**. Isso inclui o leitor facial, a prova de vida, o cálculo de jornada e as integrações. Depois de construído, o sistema passa por uma bateria completa de testes para certificação (seção 8).

**O que continua sendo de terceiros, e por quê:** servidor e banco de dados (hospedagem) e envio de e-mail. A AxSys não opera data center nem servidor de e-mail confiável. Esses itens entram como **hospedagem**, sem acesso ao rosto: o modelo facial é cifrado com chave controlada pela AxSys. A escolha deve privilegiar hospedagem no Brasil. Ver Q-25.

**Risco do modelo facial próprio:** treinar um reconhecedor de rostos do zero exige muitos rostos de treino. Usar imagens de terceiros esbarra na LGPD e em licenças. Caminhos possíveis: (a) usar modelo aberto com licença comercial permissiva e ajustá-lo; (b) treinar com voluntários que consentiram por escrito, o que limita a qualidade; (c) técnicas clássicas de menor precisão. A decisão fica para a prova de conceito técnica (Q-26).

## 7.1 Leitor facial próprio (Rodada 10)

O dono decidiu **desenvolver o leitor facial próprio**, que pede gestos (piscar, virar o rosto, sorrir) para comprovar que é uma pessoa viva e não foto nem vídeo. **Não haverá fornecedor externo de prova de vida na primeira versão.** A comparação por fornecedor continua válida como opção futura para clientes mais exigentes.

### Requisitos do leitor próprio

| # | Requisito | Motivo |
|---|---|---|
| 1 | O servidor **sorteia e assina** um desafio novo a cada tentativa (gestos e ordem), com validade curta | Impede reaproveitar vídeo gravado (replay) |
| 2 | A detecção dos gestos roda no aparelho, mas o servidor **verifica** a sequência e o tempo, e não confia só no resultado enviado | O aparelho do usuário pode ser adulterado |
| 3 | Além dos gestos, medir sinais passivos: textura, reflexo, profundidade aparente, consistência entre quadros | Gestos sozinhos são fáceis de imitar com vídeo |
| 4 | Detectar câmera virtual e vídeo injetado, tanto quanto possível no navegador | Ataque mais comum contra prova de vida |
| 5 | A comparação do rosto com o cadastro usa o modelo guardado (template) e um limiar medido | Equilíbrio entre falsa aceitação e falsa rejeição |
| 6 | **Verificar a licença** de cada modelo e biblioteca antes de usar | Alguns modelos faciais populares só podem ser usados em pesquisa, não em produto comercial |
| 7 | Descartar vídeo e quadros intermediários logo após a conferência. Guardar só **um quadro de evidência**, cifrado, por 30 dias | Respaldo em contestação com minimização |
| 8 | Tudo processado em servidor no Brasil | LGPD |

### Obrigação de testar antes de vender

Sem laboratório independente, a confiança vem de **teste próprio documentado**. Antes do lançamento:

1. Atacar o sistema com foto impressa, foto na tela, vídeo na tela, vídeo gravado, máscara, câmera virtual e replay.
2. Medir **falsa aceitação** (deixou passar fraude) e **falsa rejeição** (barrou a pessoa certa), por faixa etária e tom de pele, com voluntários que autorizaram.
3. Registrar método, resultado e versão em um relatório guardado por cliente que o pedir.
4. Repetir a cada mudança relevante do leitor.
5. Considerar um teste independente antes de vender para clientes de alto risco.

### O que muda no discurso (até haver certificação)

Não prometer "prova de vida certificada". Dizer "prova de vida com desafios aleatórios verificados no servidor, testada contra fotos, vídeos e máscaras". Isso vale para o site, o contrato e o relatório de impacto.

## 8. Plano de testes para certificação

"Certificar" tem três sentidos diferentes, e cada um pede um passo:

| Certificação | O que é | Como obter |
|---|---|---|
| Teste de resistência a fraude (ISO/IEC 30107-3) | Laboratório independente ataca o leitor e emite carta | Contratar um laboratório de teste. **Não é fornecedor do produto**, é verificador externo |
| REP-P no INPI (Portaria MTP 671/2021) | Registro do programa como ponto eletrônico | Processo no INPI e atendimento ao anexo técnico |
| Segurança da informação (por exemplo ISO/IEC 27001) | Certificação de gestão de segurança | Auditoria por certificadora, quando houver cliente que exija |

### Ordem proposta

1. **Testes internos** (antes de qualquer cliente): ataques com foto, tela, vídeo, replay, máscara e câmera virtual; falsa aceitação e falsa rejeição por idade e tom de pele; carga e desempenho; segurança (teste de intrusão); isolamento entre clientes.
2. **Relatório interno** versionado, entregue a quem pedir.
3. **Piloto** com um cliente pequeno, com aviso e método alternativo.
4. **Teste independente** de resistência a fraude, para poder dizer "certificado" com base em carta de laboratório.
5. **REP-P no INPI**, para poder vender como ponto eletrônico oficial (Q-01).

Até o passo 4, o discurso é "testado internamente", nunca "certificado".
