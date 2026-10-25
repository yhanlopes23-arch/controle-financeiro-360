# Requisitos funcionais e não funcionais

## Perfis de uso

- Pessoa física e família, com divisão autorizada de despesas.
- Profissional autônomo, prestador de serviços, MEI, pequena e média empresa.
- Multiempresa, filiais, departamentos e equipes.
- Módulos especializados futuros: comércio, e-commerce, obras, imóveis, rural, condomínios e organizações sem fins lucrativos.

## RF-01 — Identidade e organizações

Autenticação segura, múltiplas organizações, papéis, permissões por recurso e segregação de dados. Ações com impacto monetário devem ser autorizadas no servidor.

## RF-02 — Contas financeiras

Contas correntes, dinheiro, carteiras digitais, contas de investimento e caixa. Saldo inicial tem contrapartida registrada. Saldo disponível, previsto e contábil são distintos.

## RF-03 — Movimentações

Receitas, despesas, transferências, ajustes e estornos, com categoria, subcategoria, data de ocorrência, competência, vencimento, liquidação, moeda, beneficiário, anexos e origem. Busca, filtros, importações e exportação.

## RF-04 — Cartões

Limites, datas de corte/vencimento, compras parceladas, faturas, pagamentos parciais, estornos, tarifas, juros, compras internacionais, políticas do emissor. Pagamento da fatura liquida obrigação, não duplica despesa.

## RF-05 — Contas a pagar/receber

Parcelas, cobrança, pagamento parcial, inadimplência, multas, juros, desconto, renegociação, conciliação e documentos.

## RF-06 — Planejamento

Orçamento por categoria, envelope, usuário, projeto ou centro de custo; alertas, replanejamento e metas com aportes efetivamente realizados.

## RF-07 — Relatórios e painel

Saldos, fluxo de caixa, receitas e despesas, compromissos, comparativos, posição de cartões, patrimônio e indicadores empresariais. Cada métrica deve permitir inspecionar sua composição.

## RF-08 — Dívidas e investimentos

Empréstimos, cronogramas SAC/PRICE, pagamentos antecipados, investimentos e valorização patrimonial, com metodologia explicitada; preços sem cotação confiável devem exibir data da última atualização.

## RF-09 — Módulos empresariais

Clientes, fornecedores, contratos, assinaturas, projetos, centros de custo, rateios, aprovações, DRE gerencial, inadimplência, custos, margem e capital de giro.

## RF-10 — Integrações

Importação CSV/OFX/XLSX com prévia, validação, deduplicação e reversão controlada. Conectores externos dependem de credenciais, autorização, consentimento e compatibilidade. Pix, Open Finance e documentos fiscais somente por canais permitidos.

## RF-11 — Automações e IA

Recorrências, lembretes, alertas e regras configuráveis; IA explicável com escopo de dados e permissão explícitos, sem executar pagamentos ou alterar saldos silenciosamente.

## RF-12 — Colaboração

Presença e atualizações em tempo real somente de itens permitidos. Uso de controle de versão, transações e resolução de conflitos para alterações concorrentes.

## Requisitos não funcionais

- RNF-01: precisão financeira com representação monetária exata.
- RNF-02: idempotência e transações atômicas.
- RNF-03: logs de auditoria sem segredos.
- RNF-04: isolamento entre organizações e menor privilégio.
- RNF-05: proteção de dados e retenção adequada à LGPD.
- RNF-06: acessibilidade, responsividade e desempenho observável.
- RNF-07: backups protegidos e restauração testada.
- RNF-08: monitoramento de integrações, jobs e filas.
- RNF-09: plano de custos, limites e migrações.
- RNF-10: testes automatizados para casos comuns, bordas e falhas.

## Critério transversal de aceite

Uma funcionalidade precisa ter interface operacional, validação, persistência, autorização, tratamento de falhas, auditabilidade e testes adequados. Build verde, isoladamente, não comprova o funcionamento.
