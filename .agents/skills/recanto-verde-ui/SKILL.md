---
name: recanto-verde-ui
description: Planejamento, diagnóstico e implementação segura de interfaces para o Espaço Recanto Verde, com foco em experiência mobile, conversão e identidade natural.
---

# Recanto Verde UI

## Condições de entrada
Confirmar a presença do código-fonte ou de um mock de referência. Sem o código do site, não presumir implementação existente nem afirmar que houve modificação do site de produção.

## Fluxo
1. Registrar objetivo da mudança, páginas afetadas e métricas desejadas (conversão, tempo de carregamento, acessibilidade).
2. Inspecionar stack, arquivos, estilos e ativos existentes antes de editar.
3. Preservar identidade da chácara, imagens reais e caminhos de contato/reserva. Não divulgar preços.
4. Propor três direções visuais objetivas e selecionar uma antes de refatorações extensas.
5. Desenvolver em branch e ambiente isolado, com componentes reutilizáveis e responsividade testada.
6. Testar navegação, formulário/CTA, menus, acessibilidade, performance e modo mobile.
7. Entregar diff, preview e lista de riscos. Não publicar sem autorização específica.

## Referências de terceiros
- https://github.com/rtadewald/skills/tree/main/plan-screen
- https://github.com/rtadewald/skills/tree/main/extract-ds
- https://github.com/rtadewald/skills/tree/main/img-to-html

A skill extract-ds copia um site local pronto para gerar catálogo Overview e Components com duas etapas de aprovação; não equivale a extrair o código completo de um site remoto.
A skill img-to-html depende de outras skills e possivelmente de APIs pagas. Avaliar licenças, scripts, riscos e custos antes de instalar.
