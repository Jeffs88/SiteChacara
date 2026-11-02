# Ferramentas planejadas — Projeto Codex + agente de IA

Registro de planejamento atualizado em 01/11/2026.
**A presença de uma ferramenta nesta lista não significa que ela esteja instalada ou aprovada para uso em produção.** Antes de executar instaladores, revisar dependências, licenças, permissões, política de dados e custos.

| Ferramenta | Uso proposto | Status |
| --- | --- | --- |
| Codex (Cloud / CLI) | Agente de desenvolvimento e orquestração de tarefas | Codex Cloud acessado; instalação local não confirmada |
| rtadewald/skills — `to-wireframe`, `plan-screen`, `extract-ds`, `img-to-html` | Planejamento visual e reconstrução de interfaces | Revisadas estaticamente; instalação e testes ainda não confirmados |
| Modificações equivalentes a File Tree, Reflect, Blast Radius, Token Weather e Cache Tax | Observabilidade, aprendizado por regras, segurança e consumo de contexto | Avaliar equivalentes compatíveis com Codex |
| Strix AI — https://github.com/usestrix/strix | Auditoria de segurança de código e aplicações em homologação | Planejado; não executar varredura de produção; ver `SECURITY_STRIX.md` |
| OmniRoute — https://github.com/cheaper-inference/OmniRoute | Gateway de IA, regras e fallback | Planejado; ver `OMNIROUTE.md` |
| **FreeLLMAPI — https://github.com/tashfeenahmed/freellmapi** | **Gateway de modelos e quotas de APIs gratuitas; comparação com OmniRoute** | **Adicionado à lista; ainda não instalado** |

## Planejamento para FreeLLMAPI
1. Quando chegarmos à etapa de instalação dos gateways, revisar o repositório, licença, versões, Docker, segurança das credenciais e termos dos provedores.
2. Instalar somente em laboratório isolado do servidor Dell/Debian ou ambiente de testes aprovado; nenhuma porta pública sem autenticação.
3. Fazer ensaio comparativo **FreeLLMAPI x OmniRoute** com cenários idênticos: taxa de sucesso, latência, fallback, limites de requisições, qualidade dos modelos, registro de custos e esforço operacional.
4. **Não presumir custo zero nem disponibilidade garantida**: os planos gratuitos pertencem aos provedores e podem ter restrições.
5. Escolher **um gateway principal** com base nos testes; manter o outro apenas se houver benefício concreto sem duplicação desnecessária.
6. Não encaminhar dados reais de clientes da chácara a modelos gratuitos sem revisão de privacidade/LGPD e autorização apropriada.

## Ordem sugerida
1. Consolidar ambiente Codex e skills de desenvolvimento visual.
2. Receber cópia segura do código e criar homologação isolada.
3. Preparar Strix para análise de segurança exclusivamente em ambiente autorizado.
4. Comparar e selecionar OmniRoute ou FreeLLMAPI para o agente operacional.

A instalação de qualquer uma dessas ferramentas requer validação específica de compatibilidade e autorização antes de alterar produção.
