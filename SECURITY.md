# Política inicial de segurança

- Não versionar credenciais, tokens, senhas, chaves privadas, arquivos de ambiente reais ou extratos com dados pessoais.
- Segredos ficam em gerenciadores apropriados e nunca no frontend.
- Toda API exige autenticação e autorização no servidor.
- Toda query sensível deve ser limitada ao escopo da organização.
- Logs não devem expor dados bancários desnecessários.
- Dados de produção não devem alimentar ambientes de desenvolvimento sem anonimização e autorização apropriadas.
- Dependências, permissões e exposição de segredos devem ser avaliadas antes de publicação.
- Não tratar um protótipo como produto seguro para dados financeiros reais.
