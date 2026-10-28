# 13 · Precificação e nível de serviço

> **Status:** proposta preliminar. O preço final só pode ser fechado depois da cotação do fornecedor de prova de vida ([doc 12](12-fornecedores-prova-de-vida.md)), porque cada validação facial tem custo.

## 1. O que o mercado cobra

Dados encontrados em pesquisa de preços públicos. Valores mudam, vêm de páginas de fornecedores e de comparativos de terceiros, e não são orçamento formal.

| Sistema | Preço observado | Observação |
|---|---|---|
| [Genyo](https://genyo.com.br/?p=30) (Brasil) | Cerca de R$ 5,52 por colaborador na faixa de 1 a 10; R$ 3,75 na faixa de 51 a 100; a empresa diz partir de R$ 2,84 | Sem taxa de implantação e sem fidelidade |
| Jibble | Gratuito, com pagos a partir de US$ 4,49 a US$ 5,99 por usuário ao mês ([Jibble](https://www.jibble.io/?p=410139), [GetApp](https://www.getapp.com.au/software/107609/jibble)) | Diz incluir reconhecimento facial até no plano gratuito; fonte é o próprio fornecedor |
| Deputy | US$ 5, US$ 6,50 e US$ 9 por usuário ao mês ([Capterra](https://capterra.com/p/167811/Deputy/pricing/)) | Facial a partir do plano de US$ 6,50, segundo comparativo do concorrente Jibble |
| Clockify | A partir de US$ 4,99 por usuário ao mês ([Clockit](https://get.clockit.io/compare/clockify-vs-jibble)) | Segundo o mesmo comparativo, sem relógio biométrico |
| Connecteam | Fontes conflitantes: pacote por grupo de 30 usuários ou US$ 5,99 por usuário | Dado de 2024 pode estar defasado |
| Pontomais, Sólides, Tangerino, Secullum | Não encontrei preço público | Pedir orçamento |

Leitura: no Brasil, o ponto online custa de **R$ 3 a R$ 6 por colaborador ao mês**, com planos sem fidelidade; internacionalmente, de **US$ 4 a US$ 9**.

## 2. O risco que muda a conta: custo da validação facial

Cada colaborador faz de 2 a 4 batidas por dia, ou **cerca de 44 a 88 validações por mês**. Se o fornecedor cobrar, por exemplo, R$ 0,05 por validação, o custo vai de **R$ 2,20 a R$ 4,40 por colaborador ao mês**, o que pode consumir quase todo o preço de mercado. Valor ilustrativo, não cotação.

Por isso a cotação é decisiva. Alternativas para controlar o custo:
- Fazer prova de vida completa no cadastro e a cada batida só a comparação mais barata.
- Usar a chave do aparelho (passkey) como camada principal, e a prova de vida cheia só quando houver dúvida.
- Cobrar a validação facial como adicional.

## 3. Proposta provisória

| Item | Proposta | Base |
|---|---|---|
| Preço por colaborador ativo | **[a confirmar]**, hipótese de R$ 6,90 ao mês | Acima da média do mercado brasileiro por incluir prova de vida e localização; ajustar à cotação |
| Mínimo mensal | **[a confirmar]**, hipótese de R$ 99 | Cobre o custo fixo de cada cliente |
| Implantação | Sem custo | Prática de Genyo e outros |
| Teste | 30 dias gratuitos | Prática comum |
| Fidelidade | Nenhuma, aviso de 30 dias | Prática do mercado (Genyo e outros) |
| Desconto anual | 15%, pago adiantado | Comum em SaaS |
| Nível de serviço | 99,5% de disponibilidade | Faixa usual de SaaS para pequenas e médias empresas; 99,9% custa mais caro de entregar |
| Suporte | Dias úteis, 9h às 18h; primeira resposta em 1 dia útil, falha que impeça bater ponto em 4 horas úteis | Realista para uma equipe pequena |
| Crédito por indisponibilidade | 5% por ponto percentual abaixo, máximo 30% | Padrão de mercado |

## 4. Como decidir

1. Cotar 3 fornecedores de prova de vida ([doc 12](12-fornecedores-prova-de-vida.md), seção 4).
2. Calcular o custo por colaborador com 44 a 88 validações ao mês.
3. Definir o preço com margem sobre esse custo e comparar com R$ 3 a R$ 6 do mercado.
4. Registrar a decisão em [07](07-registro-de-validacoes.md) e preencher o contrato.
