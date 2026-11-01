# Instruções de trabalho para agentes — Espaço Recanto Verde

## Finalidade
Este repositório é a área de desenvolvimento do projeto **Espaço Recanto Verde**. A primeira etapa é organizar o fluxo de design e desenvolvimento com Codex; a aplicação existente **não está versionada aqui** neste momento.

## Limites obrigatórios
- **Não** assumir que os arquivos deste repositório representam o site publicado.
- **Não** implantar, reiniciar serviços, editar DNS, alterar dados, reservas, pagamentos, contratos ou o servidor de produção sem autorização explícita para a operação específica.
- Trabalhar em branches de funcionalidade, preservar a `main`, apresentar diff e testes antes de solicitar merge.
- Não incluir em commits: senhas, chaves, tokens, arquivos `.env`, backups, documentos pessoais, dados de clientes, informações financeiras privadas ou credenciais de produção. Este repositório é **público**.
- Não inventar arquitetura nem credenciais. Inspecionar os arquivos reais antes de sugerir mudanças. Na ausência do código do site, limitar-se a planejamento, protótipos e documentação.
- O projeto de reservas existente é separado do site institucional; preservar fluxos e dados reais, salvo mudança aprovada.
- Skills externas são código/instruções de terceiros. Revisar seu conteúdo e dependências antes de executar scripts, comandos ou enviar dados.

## Objetivos de produto — website
- Transmitir o caráter de chácara e espaço para eventos com visual contemporâneo, elegante, natural e confiável.
- Priorizar navegação mobile, fotografias verdadeiras, informações claras do espaço, galeria e conversão para WhatsApp/consulta de disponibilidade.
- Nunca apresentar preços públicos de locação sem aprovação do proprietário.
- Não oferecer pernoite nem fazer promessas operacionais não verificadas.
- Incorporar movimento sutil quando útil, respeitando `prefers-reduced-motion`, legibilidade e performance.
- Priorizar Core Web Vitals, SEO básico, acessibilidade, links funcionais e imagens otimizadas.

## Método
1. **Inventário**: verificar se o código real foi disponibilizado; identificar stack, rotas e integração com reservas.
2. **Diagnóstico**: encontrar problemas de experiência, responsividade, performance, acessibilidade e conversão.
3. **Propostas**: apresentar até três direções visuais, com justificativa e aprovação antes da implementação.
4. **Protótipo**: criar uma prévia isolada e responsiva; nunca substituir produção na fase de avaliação.
5. **Implementação**: alterar só o código necessário, com checkpoints e commits pequenos.
6. **Validação**: rodar verificações disponíveis; registrar o que foi testado, o que depende do servidor e o que não foi possível verificar.
7. **Entrega**: disponibilizar preview/diff e solicitar aprovação para publicação.

## Skills
- Usar `.agents/skills/recanto-verde-ui/SKILL.md` para iniciativas de redesign, componentes, UX e revisão visual.
- Skills de terceiros, como `extract-ds`, `plan-screen`, `to-wireframe` e `img-to-html`, devem ser instaladas e revisadas no ambiente Codex conforme `CODEX_SETUP.md`. Sua presença não é pressuposta.

## Comunicação
Responder em português do Brasil, com decisões técnicas justificadas, riscos explícitos, entregas verificáveis e nenhuma alegação de implantação sem evidência.
