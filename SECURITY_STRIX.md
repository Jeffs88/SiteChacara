# Plano de integração Strix — segurança do Espaço Recanto Verde

**Status:** estudo e preparação; nenhuma instalação ou teste de intrusão executado. **Alvo autorizado neste momento:** apenas um clone de desenvolvimento isolado, quando o código do produto estiver disponível. Nunca presumir autorização para atingir o domínio publicado.

## Origem oficial
- Repositório Apache-2.0: https://github.com/usestrix/strix
- Documentação de integração com Codex: https://docs.strix.ai/integrations/coding-agents
- CLI: https://docs.strix.ai/usage/cli
- Preços: https://www.strix.ai/pricing

## Objetivo
Adotar segurança como etapa de revisão de código, ambiente de homologação e entrega. Prioridade: autorização entre contas de reservas e arquivos, sessão/autenticação, administração/financeiro, upload/download de documentos e endpoints do chatbot/integrações.

## Arquitetura proposta
Codex (orquestra tarefas) -> skills oficiais Strix -> Strix CLI em ambiente de teste isolado -> relatório JSON/SARIF -> revisão e correção em branch -> novo teste em homologação -> aprovação humana.

## Implantação em fases
1. **Análise estática:** examinar skill e origem do instalador. Selecionar as skills `penetration-testing-with-strix`, `find-security-vulnerabilities-in-code`, `fix-security-vulnerabilities-with-strix` e posteriormente `ci-security-scanning-with-strix`. A documentação oficial usa `npx skills add usestrix/strix`; a execução de comandos de instalação exige revisão do pacote e dependências.
2. **Pré-requisitos:** confirmar Docker disponível e permissões no ambiente Codex; avaliar a alternativa Strix Cloud sem Docker. A versão self-hosted precisa de uma chave/endpoint LLM (ou modelo local compatível) e pode gerar custos de tokens. A assinatura ChatGPT não implica crédito de API.
3. **Laboratório:** importar uma cópia limpa e **sem dados reais** do site e do sistema Laravel, em repositório privado. Configurar staging separado e sem acesso à produção.
4. **Primeiro teste controlado:** somente após autorização explícita do proprietário para os alvos locais/staging; executar modo `quick` com orçamento de IA baixo e número de turnos limitados. Registrar escopo e relatórios. Não executar contra `espacorecantoverde.com.br` ou serviços reais por padrão.
5. **Correção:** corrigir achados confirmados em branches, executar testes funcionais e revalidar em staging; revisão humana antes de merge/deploy.
6. **CI:** preparar GitHub Actions após estabilizar aplicação e cobrança, com gatilhos que não iniciem testes intrusivos contra produção automaticamente.

## Segurança operacional (obrigatória)
- Não realizar scan/ataques/exploits em produção, em terceiros, em hosts externos ou infraestrutura compartilhada sem autorização específica e escopo aprovado.
- Não usar contas de clientes reais nem processar dados pessoais em ferramentas externas.
- Isolar o container com limites de recursos/rede e segregar dados, conexões e segredos.
- A CLI Strix documenta que diretórios passados como alvo local são montados **com permissão de escrita** e podem ser modificados. Usar clone descartável/snapshot e descartar alterações que não tenham sido revisadas.
- Não executar instalação via `curl | bash` nem permitir auto-fix, testes destrutivos, varreduras de rede ou CI automático sem revisão/autorização.
- Relatórios de vulnerabilidades não devem ser publicados no repositório público. Evitar inclusão dos artefatos `strix_runs/` em commits.
- A opção `--max-budget` é aproximada: gastos podem ultrapassar ligeiramente o teto em chamadas concorrentes; validar custos e cotas do provedor.
- Verificar requisitos legais/contratuais do provedor de hospedagem antes de executar testes intrusivos.

## Referência de comando, **NÃO EXECUTAR AGORA**
Após aprovar e provisionar staging/LLM/Docker, exemplo genérico (trocar CAMINHO_DO_CLONE pelo clone isolado):
```sh
strix -n --target CAMINHO_DO_CLONE --scan-mode quick --max-budget 5 --max-turns 60
```
- `-n` modo sem interface; `--scan-mode quick` modo rápido.
- `--max-budget` define orçamento estimado de LLM, não custo total de infraestrutura.
- Saídas podem incluir JSON e SARIF, para revisão privada.

## Situação atual
O repositório `Jeffs88/SiteChacara` continha apenas `.gitkeep` na `main` no início do projeto, sem código de aplicação. Ainda não há alvo local válido para pentest. A implementação operante só começa após importar código e criar ambiente isolado de homologação.
