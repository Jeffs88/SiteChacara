# Preparação do Codex — Espaço Recanto Verde

## Estado verificado em 01/11/2026
O repositório GitHub `Jeffs88/SiteChacara` estava sem código da aplicação (apenas `.gitkeep` na branch principal). Esta branch introduz somente instruções e estrutura para desenvolvimento, não o site real e não faz deploy.

## Para começar no Codex Cloud
1. Acessar https://chatgpt.com/codex e conectar a conta GitHub `Jeffs88`, se necessário.
2. Selecionar o repositório `Jeffs88/SiteChacara`.
3. Trabalhar na branch `codex/setup-recanto-verde-20261101` ou criar uma branch derivada.
4. Ler `AGENTS.md` e `.agents/skills/recanto-verde-ui/SKILL.md`.
5. Adicionar o código-fonte real do site **sem segredos ou dados privados** a uma branch separada, após revisar o conteúdo. Nunca compartilhar `.env` e backups.
6. Solicitar diagnóstico e um protótipo isolado antes de qualquer integração com produção.

## Instalação das skills de Rodrigo Tadewald
Fonte: https://github.com/rtadewald/skills

Conferir primeiro os arquivos `SKILL.md` e suas dependências. No Codex compatível com o instalador de skills, solicitar em uma sessão:

> Instale a skill do repositório https://github.com/rtadewald/skills no caminho extract-ds. Antes de executar seus scripts, revise dependências e explique as permissões necessárias. Faça o mesmo para plan-screen, to-wireframe e img-to-html apenas após verificar compatibilidade.

Algumas funcionalidades dependem de outras skills, de um navegador local e de serviços externos pagos; não presumir que funcionam no Codex Cloud sem testes.

## Critérios para execução
- Produção é somente leitura até autorização pontual.
- Branch, commits, testes e preview antes do merge.
- Nunca copiar dados de clientes, contratos ou credenciais para o GitHub.
- O sistema de reservas deve ser tratado como aplicação separada.
