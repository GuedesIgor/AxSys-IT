# Política de Segurança da Informação e de Resposta a Incidentes

> **Minuta aprovada pelo advogado, conforme informado pelo dono em [data].** Advogado responsável pela revisão: Dr. Dinalto Gomes Martins, OAB/SP nº 389.139. Falta a assinatura do advogado, que só ele pode apor. Parte técnica a validar por quem opera a infraestrutura. Aplica-se à AxSys IT como operadora do AxPonto.

## 1. Princípios

Confidencialidade, integridade, disponibilidade, mínimo privilégio e proteção por padrão. O dado biométrico recebe o maior nível de proteção.

## 2. Responsabilidades

| Papel | Responsável |
|---|---|
| Dono do produto e da decisão | [nome do sócio] |
| Contato de privacidade e segurança | [e-mail] |
| Operação e desenvolvimento | Equipe técnica da AxSys IT |

## 3. Controles mínimos

1. **Acesso:** contas individuais, autenticação em dois fatores, revisão trimestral, remoção imediata no desligamento.
2. **Dados biométricos:** template cifrado em base separada, chave em cofre de segredos, acesso somente pelo serviço de validação, log de todo acesso.
3. **Dados de teste:** nunca usar dados reais em desenvolvimento ou demonstração.
4. **Isolamento:** cada cliente só acessa os próprios dados, com teste automatizado dessa regra.
5. **Cópias de segurança:** cifradas, com teste de restauração semestral.
6. **Atualizações:** dependências e sistema atualizados, correção de falha crítica em até [7] dias.
7. **Fornecedores:** só os listados no contrato, com carta de teste de segurança e contrato de operador.
8. **Registros:** log de aplicação e de acesso guardados por [6] meses, protegidos contra alteração.

## 4. Classificação de incidentes

| Nível | Exemplo | Resposta |
|---|---|---|
| Crítico | Vazamento de templates faciais ou de dados de vários clientes | Imediata. Aviso aos clientes em até 24 h |
| Alto | Acesso indevido a dados de um cliente | Em até 4 h. Aviso ao cliente em até 24 h |
| Médio | Falha de isolamento sem acesso comprovado, indisponibilidade longa | Em até 1 dia útil |
| Baixo | Tentativa de ataque barrada | Registro e análise |

## 5. Procedimento

1. **Detectar e registrar:** quem viu, quando, o quê.
2. **Conter:** revogar chaves e acessos, isolar sistemas afetados.
3. **Avaliar:** quais dados e quais titulares, se há risco ou dano relevante.
4. **Comunicar:** avisar o cliente (controlador) em até **24 horas**, com natureza do incidente, dados afetados, medidas e contato. O cliente comunica a ANPD e os titulares (LGPD, art. 48). O prazo regulamentar da ANPD para essa comunicação é de **3 dias úteis**; **confirmar o texto vigente**.
5. **Corrigir:** eliminar a causa, restaurar o serviço.
6. **Aprender:** relatório com causa e ações em até [10] dias úteis. Atualizar o RIPD.

## 6. Modelo de comunicação ao cliente

> Assunto: Incidente de segurança no AxPonto, [data]
> Informamos que em [data e hora] identificamos [descrição]. Dados possivelmente afetados: [lista]. Titulares: [número]. Medidas já tomadas: [lista]. Próximos passos: [lista]. Contato: [nome, e-mail, telefone]. Enviaremos atualização em [prazo].

## 7. Treinamento e revisão

Toda pessoa com acesso ao sistema recebe treinamento anual. Esta política é revisada a cada [12] meses.
