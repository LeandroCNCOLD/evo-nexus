# CN COLD AI Nexus — implementação

## Objetivo
Evoluir o EvoNexus para uma plataforma interna de agentes de IA da CN COLD, preservando a versão original e respeitando licenças e atribuições.

## Entrega incremental e critérios de aceite
1. **Segurança P0**: bloquear exposição pública do terminal, exigir autenticação e autorização por operação (HTTP e WebSocket), validar origem e isolamento de sessões, testes negativos.
2. **Núcleo**: corrigir tickets arquivados, consistência banco/arquivos, timeouts, recuperação de tarefas e concorrência entre workers.
3. **Comercial**: carteira, histórico, cobertura de contatos de 30 dias e rankings calculados por regras auditáveis, sem dados fictícios.
4. **Nomus**: conector server-side com credenciais em segredo, importação idempotente, paginação, checkpoint, retentativas e estados incompleto/concluído. Não escrever no ERP sem autorização explícita.
5. **Agentes**: execução isolada, aprovação humana para ações externas, custo por execução, logs e trilha de auditoria.
6. **Homologação**: testes unitários, integração, migrações reversíveis, backup e ensaio de restauração. Nenhuma publicação em produção sem validação.

## Arquitetura
React/TypeScript + Flask/Python + PostgreSQL/pgvector + workers isolados, Docker/VPS. Lovable pode servir para redesenhar o frontend, mantendo o backend próprio.

## Restrições
- Não substituir nem sobrescrever main antes de revisão.
- Não expor tokens, segredos, dados pessoais ou terminal diretamente à internet.
- Nomus continua fonte oficial de pedidos/processos comerciais; atividades e análises pertencem à camada própria.
- Manter avisos de licença e esclarecer condições de marca antes de rebranding do frontend.
- Não declarar integrações ativas sem testes reais.
