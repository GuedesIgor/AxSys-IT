# 06 · Fluxos

## F1 · Registrar o ponto

```mermaid
sequenceDiagram
    actor C as Colaborador
    participant S as Sistema
    C->>S: Entra com e-mail e senha
    S-->>C: Tela "Registrar ponto"
    S->>C: Pede permissão de localização
    alt Negou ou bloqueou
        C-->>S: Sem localização
        S-->>C: Botões bloqueados e aviso "Localização obrigatória"
    else Permitiu
        C-->>S: Latitude, longitude e precisão
        S-->>C: Mostra mapa com a posição
        C->>S: Clica no botão destacado
        S-->>C: Validação facial com prova de vida (2 desafios)
        C->>S: Faz os gestos
        S-->>C: Rosto confere: pede confirmação com hora e mapa
        C->>S: Confirma
        S->>S: Grava hora do servidor, local e log
        S-->>C: Comprovante com número e local
    end
```

## F2 · Esqueci de bater o ponto

```mermaid
sequenceDiagram
    actor C as Colaborador
    participant S as Sistema
    actor G as Gestor
    C->>S: Abre Meu espelho, vê dia Incompleto
    C->>S: Ajustar, informa horário e justificativa
    S-->>C: Solicitação pendente
    S-->>G: Contador em Aprovações
    alt Aprova
        G->>S: Aprovar
        S->>S: Atualiza espelho, marca origem "ajuste", log
        S-->>C: Situação Aprovado
    else Recusa
        G->>S: Recusar com motivo
        S-->>C: Situação Recusado com resposta
    end
```

## F3 · Login

```mermaid
flowchart TD
    A[Informa e-mail e senha] --> B{Usuário existe?}
    B -->|Não| X[Erro genérico]
    B -->|Sim| C{Ativo?}
    C -->|Não| Y[Conta inativa, procure o RH]
    C -->|Sim| D{Bloqueado?}
    D -->|Sim| Z[Conta bloqueada, procure o RH]
    D -->|Não| E{Senha correta?}
    E -->|Não| F[Conta tentativas, bloqueia na 3ª]
    E -->|Sim| G[Entra na tela inicial do perfil]
```

## F4 · Novo colaborador

```mermaid
flowchart LR
    RH[RH abre Colaboradores] --> N[Novo colaborador]
    N --> V{Nome, e-mail válido e único?}
    V -->|Não| E[Mostra erro no formulário]
    V -->|Sim| FC{Rosto cadastrado com prova de vida?}
    FC -->|Não| E2[Não salva: cadastro facial obrigatório]
    FC -->|Sim| OK[Cria com senha provisória]
    OK --> L[Registra na auditoria]
```

## F5 · Registrar no quiosque

```mermaid
sequenceDiagram
    actor C as Colaborador
    participant K as Quiosque
    participant S as Sistema
    C->>K: Informa matrícula e PIN
    K->>S: Valida conta e dia
    alt Inválido, inativo, em ausência ou jornada concluída
        S-->>K: Mensagem de erro
    else Válido
        S-->>K: Próxima batida com mapa da unidade
        K-->>C: Validação facial com prova de vida
        C->>K: Confirma
        S->>S: Grava com local da unidade e origem "quiosque"
        S-->>K: Comprovante
    end
```

## F6 · Batida fora da área da empresa

```mermaid
flowchart TD
    A[Confirma batida] --> B{Unidade tem cerca?}
    B -->|Não, home office| OK[Registra]
    B -->|Sim| C{Dentro do raio?}
    C -->|Sim| OK
    C -->|Não| D{Modo configurado}
    D -->|Permitir| W[Registra e avisa o gestor]
    D -->|Justificar| J[Pede motivo] --> W
    D -->|Bloquear| X[Impede o registro]
    W --> EX[Aparece no painel de exceções]
```

## F7 · Solicitar ausência

```mermaid
sequenceDiagram
    actor C as Colaborador
    participant S as Sistema
    actor G as Gestor
    C->>S: Escolhe tipo, período e observação
    S->>S: Confere saldo de férias e sobreposição
    S-->>G: Contador em Aprovações
    alt Aprova
        G->>S: Aprovar
        S->>S: Atualiza escala, espelho e banco de horas
    else Recusa
        G->>S: Recusar com motivo
        S-->>C: Situação Recusada com resposta
    end
```

## F8 · Fechamento do mês

```mermaid
flowchart TD
    A[Mês termina] --> B[Colaborador confere e assina o espelho]
    B --> C{Há problema?}
    C -->|Sim| D[Pede ajuste] --> E[Gestor decide] --> B
    C -->|Não| F[Gestor aprova o espelho]
    F --> G[RH confere o painel de exceções]
    G --> H[RH fecha o mês]
    H --> I[Mês travado: sem novos ajustes]
    I --> J[RH exporta eventos de folha, AFD e AEJ]
```

## F9 · Registro offline

```mermaid
flowchart LR
    A[Sem internet] --> B{Offline permitido?}
    B -->|Não| X[Batida bloqueada]
    B -->|Sim| C[Salva no aparelho como pendente]
    C --> D[Internet volta]
    D --> E[Sincronizar]
    E --> F[Registro enviado, alerta some]
```

## F10 · Ponto sem localização

```mermaid
sequenceDiagram
    actor C as Colaborador
    participant S as Sistema
    actor G as Gestor
    C->>S: Tenta bater o ponto
    S-->>C: Localização negada ou indisponível, botão bloqueado
    C->>S: Registrar sem localização
    S-->>C: Pede validação facial e justificativa obrigatória
    C->>S: Envia
    S->>S: Guarda como PENDENTE (não conta no espelho)
    S-->>C: Protocolo "pendente de aprovação"
    S-->>G: Aviso e contador em Aprovações
    G->>S: Lê justificativa, motivo técnico, aparelho e hora
    alt Aprova
        G->>S: Justificativa da aprovação (obrigatória)
        S->>S: Entra no espelho como "sem localização"
        S-->>C: Aprovado, com a justificativa do gestor
    else Recusa
        G->>S: Justificativa da recusa (obrigatória)
        S-->>C: Recusado, com a justificativa do gestor
    else Passou o prazo (2 dias úteis)
        S-->>G: Lembrete no último dia
        S->>S: Vencido: marca como escalado ao RH
    end
```
