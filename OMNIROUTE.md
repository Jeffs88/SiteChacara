# OmniRoute — estudo para o projeto de agente de IA

Status: **registrado para avaliação; não instalado**. Registro de 01/11/2026.

## Referências confirmadas
- Site oficial: https://www.omniroute.online/
- Repositório apontado pelo site: https://github.com/cheaper-inference/OmniRoute
- Projeto open-source, licença MIT (conferir licença no commit escolhido antes da implantação).

## O que faz
Gateway/proxy de modelos de IA: unifica provedores em um endpoint compatível com OpenAI; oferece encaminhamento por regras, fallback quando há indisponibilidade ou quota insuficiente, controles de limites e gastos, opções de compressão de contexto, dashboard e integração MCP. Pode atender clientes de desenvolvimento como Codex CLI e aplicações próprias que utilizam APIs compatíveis.

## Aplicação planejada
- **Agente operacional próprio** (ERP e reservas da chácara, WhatsApp, futuros fluxos): testar como roteador de modelos, com logs sem dados pessoais e fallback explícito.
- **Desenvolvimento com Codex CLI**: avaliar endpoint customizado separadamente. Não pressupor que a interface Codex Cloud/ChatGPT permita substituir seu backend pelo OmniRoute.
- **Infraestrutura**: avaliar piloto isolado via Docker no servidor Dell Debian 13, sem interferir nos containers existentes. Proteger dashboard e API, jamais expor a porta sem autenticação e TLS.

## Decisões e riscos
1. Serviço self-hosted pode ser gratuito; **uso dos provedores/modelos pode ser cobrado**. Plano ChatGPT Plus não substitui contrato/créditos de API.
2. Reduções alegadas de 15–95% de tokens aplicam-se a contextos elegíveis; medir qualidade, custo e latência com o nosso tráfego antes de aceitar promessas.
3. Verificar tratamento de dados pessoais e retenção/logging, sobretudo dados de reservas, clientes e contratos (LGPD).
4. Validar credenciais/consentimento e termos de uso de cada provedor. Não usar sessões web ou cookies como substituto não autorizado de API.
5. Isolar credenciais em secrets, controlar acesso, registrar métricas sem conteúdo sensível e definir timeout/circuit breaker.
6. Nenhuma instalação em produção ou mudança no Codex será realizada antes da análise de dependências e autorização específica.

## Próximos testes (somente após aprovação)
- Revisar código, cadeia de dependências e configuração Docker da release fixada.
- Subir instância em ambiente de desenvolvimento; configurar dois provedores/modelos com autorização.
- Testar resposta normal, fallback forçado, quotas, custo e proteção de dados.
- Comparar com chamadas diretas e considerar manutenção operacional.
