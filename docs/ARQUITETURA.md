# Arquitetura — proposta sujeita a decisão

**Status: estudo inicial.** Nenhuma stack foi definitivamente selecionada.

## Camadas

1. **Interface**: dashboard, navegação e formulários com acessibilidade.
2. **API e autorização**: validação, papéis, escopo por organização e fluxos de aprovação.
3. **Domínio**: lançamentos, pagamentos, parcelas, faturas, estornos e conciliação.
4. **Persistência transacional**: razão, linhas, obrigações, versões e auditoria.
5. **Processos assíncronos**: importação, relatórios, recorrências e notificações.
6. **Integrações**: adaptadores com idempotência, limites, consentimentos e reprocessamento seguro.
7. **Observabilidade e recuperação**: métricas, logs, alarmes e restauração.

## Alternativas a avaliar

| Critério | PostgreSQL + API TypeScript | Firestore + Functions/Workers |
| --- | --- | --- |
| Razão financeiro relacional | Natural, com restrições e transações SQL | Requer modelagem cuidadosa e consistência transacional explicitada |
| Dados relacionais e relatórios | SQL e consultas robustas | Pode exigir materializações e mais leituras |
| Colaboração em tempo real | Canal adicional/WebSockets/realtime | Streams/observadores nativos conforme plataforma |
| Escalabilidade e custo | Dependem de hospedagem, queries e operações | Dependem de leituras, escritas e serviços acionados |
| Migrações e manutenção | Migrações relacionais tradicionais | Migrações de documentos e índices |

A comparação exige teste de custo, integridade, consistência e requisitos de operação reais. Proibido escolher somente pela facilidade de prototipação.

## Entidades candidatas

users, organizations, memberships, roles, permissions, accounts, journal_transactions, journal_entries, categories, payables, receivables, settlements, cards, purchases, card_statements, budgets, goals, loans, investments, customers, suppliers, cost_centers, projects, audit_events, import_batches, integration_connections, webhook_events.

## Decisões pendentes

- Escolher stack e provedor de infraestrutura.
- Estabelecer esquema de moedas, precisão e câmbio.
- Definir separação entre livro de caixa e competência.
- Definir escopo de multiempresa no MVP.
- Escolher autenticação, autorização e modelo de segregação.
- Selecionar serviço de filas e observabilidade.
- Revisar custos e requisitos regulatórios dos conectores.

## Regra de migração

Qualquer mudança de banco ou mecanismo financeiro exige plano, validação de equivalência de saldos, testes históricos e rollback.
