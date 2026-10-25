# Estratégia de testes

## Núcleo

- Transferências internas mantêm total consolidado.
- Operações com várias entradas são atômicas.
- Estornos preservam história e reconciliam saldos.
- Pagamentos parciais reduzem a obrigação corretamente.
- Pagamentos de fatura não duplicam despesa.
- Parcelas somam exatamente o valor original.
- Compras nas bordas do fechamento de fatura usam política correta.
- Recorrências executadas novamente não duplicam obrigações.
- Importações duplicadas não duplicam lançamentos.
- Webhooks duplicados, atrasados e fora de ordem não causam efeitos extras.
- Mudanças de competência e liquidação aparecem nos relatórios corretos.
- Operações multimoedas preservam valores históricos e taxas utilizadas.

## Segurança

- Usuário de uma organização não acessa dados de outra.
- Tentativas de elevar permissões falham no servidor.
- Revogação de autorização produz efeito nos acessos seguintes.
- Auditoria registra ações críticas sem dados secretos.

## Resiliência

- Requisições concorrentes não provocam saldo incorreto.
- Falha de conexão não produz escrita parcial.
- Fila reprocessada não duplica operação.
- Backup restaurado mantém invariantes financeiras.

## Interface

- Acessibilidade em teclado e leitores de tela.
- Valores e indicadores abrem suas fontes.
- Estados de carregamento/erro/vazio claros.
- Responsividade em mobile e desktop.

Registrar comando, ambiente, data e evidência dos testes executados. Não marcar como aprovado apenas por expectativa.
