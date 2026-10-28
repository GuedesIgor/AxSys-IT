# 14 · Hospedagem própria no SRVAD1 com IIS

> **Decisão do dono (Rodada 12):** o AxPonto será hospedado em servidor próprio da AxSys IT, o **SRVAD1**, com **IIS** (Windows Server). Resolve a pergunta Q-25 e dispensa provedor de hospedagem de terceiros.

## 1. O que muda

| Tema | Efeito |
|---|---|
| Suboperador de hospedagem | Deixa de existir. A AxSys passa a operar a infraestrutura. O Anexo B do contrato de operador foi atualizado |
| Responsabilidade | Disponibilidade, segurança, cópias e atualização do servidor passam a ser da AxSys |
| LGPD | O dado fica em servidor no Brasil, sob controle da AxSys. É preciso cuidar da segurança física e do acesso |
| Tecnologia do app real (Q-09) | Precisa rodar bem no Windows com IIS. Proposta: ASP.NET Core na versão LTS vigente, com PostgreSQL ou SQL Server. Decisão técnica ainda aberta |

## 2. Pontos de atenção antes de publicar para clientes

Estes itens decidem se a hospedagem própria é segura e confiável o bastante para guardar dado biométrico.

| # | Ponto | Por que importa |
|---|---|---|
| 1 | **O que o SRVAD1 já faz?** O nome sugere servidor de Active Directory. **Não se deve expor aplicação pública na internet em um controlador de domínio.** Se for esse o caso, usar outra máquina (ou máquina virtual) para o AxPonto | Comprometer o app comprometeria toda a rede da empresa |
| 2 | **HTTPS com certificado válido e domínio próprio** (por exemplo, `ponto.axsys.com.br`) | Câmera e localização do navegador só funcionam em HTTPS. Sem isso o sistema não opera |
| 3 | **Link de internet e IP fixo** na unidade onde o servidor fica, com provedor que garanta disponibilidade | Servidor em escritório depende do link e da energia do local |
| 4 | **Energia estável** (nobreak) e, ideal, gerador ou segundo ponto | Queda de energia derruba o ponto de todos os clientes |
| 5 | **Firewall e isolamento** (zona separada da rede interna), só portas 80 e 443 abertas, acesso administrativo por VPN | Reduz a superfície de ataque |
| 6 | **Cópias de segurança fora do local**, cifradas, com teste de restauração | Incêndio, furto ou falha de disco não podem apagar os dados dos clientes |
| 7 | **Atualizações do Windows e do IIS** em rotina, com janela avisada | Falhas conhecidas são a principal porta de entrada |
| 8 | **Monitoramento e alerta** (disponibilidade, disco, certificado a vencer) | Descobrir a queda antes do cliente |
| 9 | **Chave de cifra do modelo facial** fora do banco de dados, protegida | Vazamento do banco não pode expor rostos |
| 10 | **Segurança física:** sala trancada, acesso registrado | Dado biométrico em máquina acessível a qualquer pessoa |
| 11 | **Proteção contra ataque de negação de serviço** | Um servidor único cai com facilidade |

## 3. O nível de serviço de 99,5% é viável?

O contrato prevê 99,5% de disponibilidade (cerca de 3 horas e 40 minutos de queda por mês). Com **um servidor, um link e um nobreak**, isso é difícil de sustentar. Opções:
1. Manter 99,5% e investir em segundo link, nobreak e servidor reserva.
2. Começar com **99% (cerca de 7 horas por mês)** no piloto e elevar depois de medir a disponibilidade real. Exige alterar a cláusula 6 do contrato SaaS.
3. Adotar na primeira fase "melhor esforço", só para clientes-piloto, com aviso claro.

Recomendação: opção 2 durante o piloto.

## 4. Publicar o protótipo no IIS

O protótipo é um arquivo único, sem servidor de aplicação. Serve para demonstração em `demo.axsys.com.br` (ou similar), **nunca no mesmo site do sistema real**, porque tem usuários e senhas fictícios.

1. No IIS, instalar o módulo **URL Rewrite**.
2. Copiar a pasta `prototipo/` (com `index.html` e `web.config`) para o servidor, por exemplo `C:\inetpub\axponto-demo`.
3. Criar um site apontando para a pasta, com binding HTTPS e o certificado.
4. Conferir o acesso por HTTPS. O `web.config` já força HTTPS, remove o cabeçalho de versão do servidor, liga cabeçalhos de segurança e pede aos buscadores que não indexem.
5. Testar: login com `ana.lima@axsys.test` e a batida de ponto completa.

O protótipo **não carrega nada de fora**: a fonte Inter (licença SIL Open Font) agora vai embutida no arquivo, sem consulta ao Google. Isso evita enviar o IP dos visitantes a terceiros e atende à diretriz de não depender de fornecedores externos.

## 5. Publicar o sistema real (quando existir)

Esboço, a detalhar com a escolha da tecnologia:
- Site IIS com pool de aplicação próprio, identidade de baixo privilégio.
- ASP.NET Core Hosting Bundle instalado.
- Banco de dados em máquina ou serviço separado, sem acesso direto da internet.
- Segredos (strings de conexão, chaves) fora do repositório e fora dos arquivos de configuração do site.
- Registros de acesso e de auditoria gravados em disco separado.
- Processo de implantação com cópia anterior guardada para voltar atrás (rollback).

## 6. Decisões em aberto

- O SRVAD1 é um controlador de domínio? Se for, qual máquina usar.
- Onde fica fisicamente o servidor, e qual o link de internet e a energia do local.
- Domínio e certificado (quem emite e renova).
- Plano de cópias fora do local.
- Valor do SLA da primeira fase.
