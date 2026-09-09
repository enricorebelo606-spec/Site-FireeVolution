# FireeVolution

Site da FireeVolution com:
- Login e criação de conta na interface.
- Menu de conta.
- Painel de administrador.
- Conta autorizada para a extensão Chrome: `enricorebelo606@gmail.com`.
- Visual mantido no estilo escuro/laranja original.

## Importante sobre autenticação real

O projeto original é um site HTML estático. Por isso, o fluxo incluído no `index.html` é uma **demonstração local** usando `localStorage`.

Para colocar em produção:
1. Use Firebase Authentication, Supabase Auth ou um backend próprio.
2. Nunca salve senhas no `localStorage`.
3. Faça o login Google via OAuth/OIDC no servidor.
4. O servidor deve verificar o token Google e aceitar a conta da extensão somente quando o e-mail for `enricorebelo606@gmail.com`.
5. A extensão Chrome deve validar a sessão/token com o backend; não confie em uma checagem feita apenas no JavaScript da página.
6. O painel de admin também deve ser protegido no backend.

Os links Stripe existentes foram preservados.


## Produto ZIP por assinatura

O Painel de Admin agora tem um seletor de arquivo `.zip` para escolher o arquivo do produto e campos para nome, preço e periodicidade da assinatura (diária, mensal ou anual).

**Importante:** em uma página HTML estática, o navegador não envia automaticamente o ZIP para o servidor nem cria uma assinatura Stripe. O painel salva apenas a configuração localmente. Para vender o ZIP de verdade, o próximo passo é ligar esse botão ao backend/Stripe, fazer upload do arquivo para armazenamento privado e liberar o download somente para assinantes ativos.
