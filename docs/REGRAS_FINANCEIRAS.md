# Invariantes financeiras e consistência

1. **Razão equilibrado:** em cada lançamento contábil aprovado, débitos e créditos devem se equilibrar na moeda e unidade de escrituração apropriadas.
2. **Representação exata:** evitar float/double para dinheiro. Utilizar decimal exato ou inteiro de menor unidade monetária, conforme a moeda.
3. **Saldo derivável:** todo saldo precisa ser reconciliável com lançamentos imutáveis, abertura, estornos e ajustes justificados.
4. **Transferência neutra:** mover dinheiro entre contas da mesma entidade não gera resultado econômico por si só. Tarifas associadas geram lançamentos próprios.
5. **Separação temporal:** distinguir competência, ocorrência, vencimento, autorização e liquidação.
6. **Parcelas e faturas:** compra, obrigação e liquidação não são despesas independentes a serem somadas indistintamente.
7. **Estornos auditáveis:** não apagar operações efetivadas para ocultar efeito; criar evento reversor vinculado, quando aplicável.
8. **Idempotência:** mesma operação externa, arquivo, webhook ou job não deve contabilizar duas vezes o efeito financeiro.
9. **Atomicidade:** múltiplas linhas de uma operação são aplicadas integralmente ou nenhuma é aplicada.
10. **Concorrência:** alteração com versão obsoleta deve ser rejeitada ou resolvida, sem sobrescrita silenciosa.
11. **Autorização no servidor:** identidade e organização devem ser validadas para cada leitura, gravação e exportação.
12. **Fechamento:** períodos fechados exigem autorização e procedimento rastreado para ajustes.
13. **Orçamento não é saldo:** compromissos e previsões não podem ser confundidos com dinheiro disponível.
14. **Moeda:** conservar moeda de origem, taxa utilizada, base e eventuais diferenças cambiais em operações multimoedas.
15. **Arredondamento:** diferença residual de centavos deve ter distribuição determinística e documentada.

## Exemplos de aceitação

- Transferir R$ 200,00 da conta A (R$ 1.000,00) à B (R$ 300,00): A = R$ 800,00, B = R$ 500,00, patrimônio consolidado = R$ 1.300,00.
- Dividir R$ 100,00 em 3 parcelas: resultados em centavos somam exatamente R$ 100,00 (por exemplo R$ 33,34 + R$ 33,33 + R$ 33,33).
- Receber R$ 350,00 de uma obrigação de R$ 1.000,00 sem juros: saldo = R$ 650,00.
- Pagar uma fatura já composta por despesas reconhecidas: baixar a dívida e a conta pagadora, não duplicar despesas.
