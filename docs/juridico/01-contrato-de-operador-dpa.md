# Contrato de Tratamento de Dados Pessoais (Anexo de Proteção de Dados)

> **Minuta para revisão.** Advogado responsável pela revisão: Dr. Dinalto Gomes Martins, OAB/[UF] nº [número]. Não revisada nem assinada. Anexo ao Contrato de Prestação de Serviços SaaS do AxPonto ([02](02-contrato-saas-e-termos-de-uso.md)).

## Partes

- **CONTROLADORA:** [razão social do cliente], CNPJ [número], com sede em [endereço], representada por [nome e cargo].
- **OPERADORA:** AxSys IT, razão social, CNPJ e endereço [PENDENTE: a AxSys IT ainda não tem CNPJ aberto], representada por [nome do sócio].

## 1. Definições

Aplicam-se as definições da Lei nº 13.709/2018 (LGPD). Neste anexo: **Dados Pessoais** são os tratados pela OPERADORA em nome da CONTROLADORA por meio do AxPonto; **Dados Biométricos** são o modelo facial (template) e o resultado da validação facial; **Titulares** são os empregados, estagiários e demais pessoas que registram jornada.

## 2. Objeto e instruções

2.1. A OPERADORA tratará os Dados Pessoais **somente** para prestar o serviço contratado e conforme as instruções documentadas da CONTROLADORA (LGPD, art. 39).
2.2. Este anexo, o contrato principal e as configurações feitas pela CONTROLADORA no sistema constituem as instruções.
2.3. A OPERADORA avisará a CONTROLADORA se entender que uma instrução viola a lei.

## 3. Natureza, finalidade e dados

| Item | Descrição |
|---|---|
| Finalidade | Registro de jornada, cálculo de horas, aprovação de ajustes e ausências, prevenção de fraude no registro por validação facial e localização |
| Categorias de dados | Identificação (nome, e-mail, matrícula, CPF parcial), vínculo (setor, cargo, gestor), jornada, localização da batida, dispositivo, **dados biométricos** (sensíveis) |
| Titulares | Empregados e colaboradores da CONTROLADORA |
| Duração | Vigência do contrato, mais o período de devolução ou eliminação (cláusula 11) |

## 4. Obrigações da CONTROLADORA

4.1. Definir e responder pela **base legal** do tratamento, inclusive dos Dados Biométricos, e informar os Titulares (LGPD, art. 9).
4.2. Elaborar o **Relatório de Impacto** (LGPD, art. 38), com o modelo fornecido pela OPERADORA ([05](05-modelo-ripd.md)).
4.3. Indicar o **encarregado** e informar nome e contato à OPERADORA no cadastro.
4.4. Oferecer **método alternativo** à validação facial a quem não puder ou não quiser usá-la, sem exigir explicação nem prejudicar o Titular.
4.5. Não inserir no sistema dado pessoal desnecessário, em especial dado de saúde.

## 5. Obrigações da OPERADORA

5.1. Tratar os dados só conforme as instruções (cláusula 2).
5.2. Manter **confidencialidade** com quem acessa os dados, por compromisso formal.
5.3. Adotar as medidas de **segurança** do Anexo A, compatíveis com o risco do dado biométrico (LGPD, arts. 46 a 49).
5.4. **Não utilizar** os Dados Pessoais, em especial os Biométricos, para outra finalidade, nem para treinar ou melhorar modelos próprios ou de terceiros.
5.5. Manter **isolamento lógico** entre os dados de clientes diferentes.
5.6. Manter registro das operações de tratamento (LGPD, art. 37) e **log de acesso** aos Dados Biométricos.
5.7. Auxiliar a CONTROLADORA a atender os direitos dos Titulares (LGPD, art. 18) em até [5] dias úteis.

## 6. Suboperadores

6.1. A CONTROLADORA **autoriza** os suboperadores da lista do Anexo B.
6.2. A OPERADORA avisará com [30] dias de antecedência qualquer inclusão ou troca, e a CONTROLADORA poderá se opor por motivo fundamentado. Persistindo a oposição, qualquer parte poderá rescindir sem multa.
6.3. A OPERADORA impõe aos suboperadores obrigações equivalentes e responde por eles perante a CONTROLADORA.

## 7. Transferência internacional

Dados Pessoais ficam em servidores localizados [no Brasil]. Qualquer tratamento fora do Brasil dependerá de aviso prévio e de mecanismo válido (LGPD, art. 33 e regulamentação da ANPD).

## 8. Incidentes de segurança

8.1. A OPERADORA comunicará a CONTROLADORA em até **24 horas** após tomar conhecimento de incidente que afete Dados Pessoais, com: natureza, dados e Titulares afetados, medidas adotadas e contato.
8.2. A comunicação à ANPD e aos Titulares é de responsabilidade da CONTROLADORA (LGPD, art. 48), com o apoio da OPERADORA.
8.3. A OPERADORA seguirá a [Política de segurança e incidentes](06-politica-de-seguranca-e-incidentes.md).

## 9. Direitos dos Titulares

Pedidos recebidos diretamente pela OPERADORA serão encaminhados à CONTROLADORA em até [2] dias úteis, sem resposta ao Titular, salvo instrução em contrário.

## 10. Auditoria

A CONTROLADORA pode, mediante aviso de [15] dias e uma vez por ano, solicitar informações e relatórios que comprovem o cumprimento deste anexo. Auditoria presencial dependerá de acordo, com sigilo e sem acesso a dados de outros clientes.

## 11. Término

11.1. Encerrado o contrato, a OPERADORA, a critério da CONTROLADORA, **devolve ou elimina** os Dados Pessoais em até [30] dias, e comprova a eliminação por escrito.
11.2. O **template facial** é eliminado quando a CONTROLADORA registrar o desligamento do Titular, em até 30 dias.
11.3. Poderão ser mantidos os dados cuja guarda a lei exigir, pelo prazo legal.

## 12. Responsabilidade

Cada parte responde pelos danos que causar ao descumprir a LGPD e este anexo, nos termos dos arts. 42 a 45 da LGPD. Aplicam-se aos danos de violação deste anexo os limites da cláusula 10.2 do contrato principal (limite especial para dados pessoais), ressalvados os direitos dos titulares. **(Revisão do advogado.)**

## 13. Disposições gerais

Em caso de conflito, prevalece este anexo quanto a dados pessoais. Foro da comarca de Ilha Solteira, Estado de São Paulo. Assinatura eletrônica admitida.

[Local], [data].

______________________  ______________________
CONTROLADORA            OPERADORA

## Anexo A: medidas de segurança

| Área | Medida |
|---|---|
| Criptografia | Dados cifrados em trânsito (TLS) e em repouso. Template facial em base separada, com chave em cofre de segredos |
| Acesso | Mínimo necessário, autenticação forte para a equipe, revisão trimestral |
| Registro | Log de acesso a dados biométricos, imutável, guardado por [6 meses] |
| Isolamento | Separação lógica entre clientes |
| Continuidade | Cópias de segurança cifradas, teste de restauração [semestral] |
| Desenvolvimento | Revisão de código, dependências atualizadas, ambientes separados, dados reais nunca usados em teste |
| Pessoas | Compromisso de confidencialidade e treinamento anual |
| Testes | Teste de intrusão [anual] |

## Anexo B: suboperadores autorizados

| Suboperador | Serviço | País | Dados |
|---|---|---|---|
| [fornecedor de nuvem] | Hospedagem | [Brasil] | Todos, cifrados |
| [fornecedor de prova de vida] | Prova de vida e comparação facial | [a definir] | Captura facial durante a validação |
| [fornecedor de e-mail] | Envio de notificações | [a definir] | E-mail e nome |
