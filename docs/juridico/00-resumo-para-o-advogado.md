# Resumo para o advogado responsável

**Para:** Dr. Dinalto Gomes Martins, advogado (OAB/[UF] nº [número a preencher])
**De:** AxSys IT
**Assunto:** AxPonto, sistema de registro de ponto vendido como serviço (SaaS). Revisão das minutas e parecer sobre biometria facial.
**Situação:** minutas elaboradas pela equipe de produto com apoio do Claude. Segundo o dono, o advogado leu este resumo e aprovou. **Pendentes:** número da OAB, assinatura do advogado e os campos entre colchetes (CNPJ, preço).
**Atualização:** a validação facial será um **leitor próprio**, sem fornecedor externo de prova de vida (ver [docs/12](../12-fornecedores-prova-de-vida.md)). Isso altera a pergunta 7 e o risco de fraude; ver pergunta 11.

## O produto em 5 linhas

1. Sistema web para empresas registrarem o ponto de seus empregados, pelo navegador do celular ou computador e por quiosque.
2. Cada batida exige **localização do aparelho** e **validação facial com prova de vida**. O cadastro do rosto é obrigatório para criar o usuário.
3. Sem localização, sem câmera ou após 3 recusas da validação facial, a batida fica **pendente** até o gestor aprovar com justificativa. O RH pode autorizar **método alternativo (PIN)** a uma pessoa, sem registrar o motivo.
4. Guardamos só o modelo matemático do rosto (sem foto), cifrado, apagado até 30 dias após o desligamento.
5. A AxSys vende o serviço a empresas. **Cada cliente é controlador** e indica o seu encarregado. **A AxSys é operadora.**

## O que pedimos que o senhor faça

| # | Tarefa | Documento |
|---|---|---|
| 1 | Revisar e ajustar o contrato de operador (anexo de proteção de dados) | [01](01-contrato-de-operador-dpa.md) |
| 2 | Revisar o contrato de serviço SaaS e os termos de uso | [02](02-contrato-saas-e-termos-de-uso.md) |
| 3 | Revisar a política de privacidade | [03](03-politica-de-privacidade.md) |
| 4 | Revisar o aviso ao colaborador | [04](04-aviso-ao-colaborador.md) |
| 5 | Revisar o modelo de relatório de impacto (RIPD) | [05](05-modelo-ripd.md) |
| 6 | Revisar a política de segurança e de incidentes | [06](06-politica-de-seguranca-e-incidentes.md) |
| 7 | Responder as perguntas abaixo | este documento |

## Informações já definidas

- **Foro:** comarca de Ilha Solteira, SP.
- **Empresa:** a AxSys IT **ainda não tem CNPJ**. Razão social, CNPJ e endereço estão como pendentes. Os contratos só podem ser assinados com clientes depois da abertura da empresa; o senhor poderá orientar sobre o tipo societário.
- **Preços e SLA:** propostos com base em estudo de mercado ([docs/13](../13-precificacao.md)).
- **Cláusula de limitação de responsabilidade:** minutada (contrato SaaS, cláusula 10), pede sua análise.

## Perguntas centrais

1. **Base legal.** O art. 11, II, "g" da LGPD (prevenção à fraude na autenticação) sustenta a validação facial do empregado no ponto? Se não, qual base? Não encontramos posição da ANPD específica para ponto biométrico.
2. **Obrigatoriedade.** É seguro tornar o rosto o método padrão, com alternativa garantida e sem exigir explicação? E o rosto como único método?
3. **Portaria MTP 671/2021.** A batida "pendente de aprovação" (sem localização ou sem validação facial) é compatível com o dever de registrar a marcação? Propomos gravar a marcação na hora, em registro imutável, e deixar a aprovação decidir só se ela entra no cálculo. Basta?
4. **Retenção.** O template apagado até 30 dias após o desligamento e o resultado da validação guardado pelo prazo do registro de jornada (CF art. 7, XXIX) estão corretos?
5. **Papéis.** A AxSys como operadora e cada cliente como controlador está bem caracterizado? Há risco de a AxSys ser vista como controladora conjunta por definir as regras de validação?
6. **Pequeno porte.** A AxSys se enquadra como agente de tratamento de pequeno porte (Resolução CD/ANPD nº 2/2022) e fica dispensada de indicar encarregado?
7. **Transferência internacional.** Com o leitor próprio e hospedagem no Brasil, não há transferência prevista. Se a hospedagem for fora do Brasil, qual o mecanismo adequado?
8. **Limitação de responsabilidade.** Os limites de 12 e 24 meses de pagamentos, com regresso proporcional, são válidos e adequados ao risco de dado biométrico?
11. **Sem CNPJ.** Qual o melhor enquadramento para a AxSys vender o serviço (sociedade limitada unipessoal, outro) e o que ela pode ou não fazer antes da abertura?
9. **Menores.** Como tratar estagiários e jovens aprendizes menores de 18 anos?
10. **Certificação.** O que mudar nos contratos e na publicidade enquanto o REP-P não for certificado no INPI?

11. **Leitor facial próprio.** Sem certificação independente de resistência a fraude, quais cuidados jurídicos devemos ter na promessa ao cliente e na cláusula de responsabilidade? Propomos documentar testes internos de ataque e não prometer "prova de vida certificada".

## Material de apoio

- [Pacote jurídico completo](../11-pacote-juridico-lgpd.md) (bases legais, RIPD, retenção, Portaria 671).
- [Regras de negócio da validação facial](../03-regras-de-negocio.md) (RN-19, RN-20, RN-21).
- Protótipo navegável (link do artefato, com usuários e senhas fictícios).
