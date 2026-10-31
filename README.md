# Gestão PagTudo — MVP 1.0

Protótipo web responsivo para validar os três fluxos priorizados: cadastro de produtos, criação de checkout/cobrança demonstrativa e acompanhamento de eventos de webhook simulados.

## Executar

1. Extraia o ZIP.
2. Abra `index.html` em um navegador moderno ou publique a pasta em um host estático (GitHub Pages/Cloudflare Pages).
3. Os dados são salvos no `localStorage` do navegador.
4. Em Configurações, use **Carregar dados de exemplo** para explorar o painel.

Não há build, dependência npm ou API externa no protótipo.

## O que funciona neste MVP

- Navegação entre Visão geral, Produtos, Vendas e cobranças, Webhooks e Configurações.
- Cadastro, edição e exclusão de produtos (não permite excluir produto já vinculado a cobrança).
- Validação de nome e preço, busca de produtos e estados vazios.
- Criação de cobrança local, seleção de Pix/boleto/cartão e prévia de checkout.
- Simulação de confirmação via webhook e registro de evento; a cobrança confirmada não é processada novamente como recebimento.
- Filtro de cobranças, cancelamento local, exportação JSON e dados de exemplo.
- Layout responsivo, navegação por teclado e rótulos acessíveis básicos.

## Limitações importantes

- Pix, boleto e cartão são apenas opções visuais neste protótipo. Nenhum QR Code, boleto bancário, autorização de cartão ou pagamento real é gerado.
- Links de checkout são prévias internas, não URLs públicas para compradores.
- Webhooks são simulados no navegador. Não existe endpoint público receptor nem validação de assinatura/token nesta versão.
- Não há login, isolamento de vendedores, banco remoto, conciliação, split, saque ou operação financeira real.
- O armazenamento local não deve ser usado como base de dados de produção.

## Próxima etapa para produção

1. Criar projeto Supabase dedicado e configurar Auth.
2. Aplicar o modelo de dados em `supabase/schema.sql`; revisar grants/RLS e exposição da Data API no projeto.
3. Criar Edge Functions autenticadas para criar cliente/cobrança no Asaas e endpoint separado para receber webhooks.
4. Guardar `ASAAS_API_KEY` e `ASAAS_WEBHOOK_TOKEN` somente nos Secrets das Edge Functions. Nunca incluir segredos no frontend.
5. Configurar primeiro o Sandbox Asaas, testar todos os estados e duplicidades, e só então avaliar produção.

## Fontes técnicas

- Asaas: https://docs.asaas.com/docs/visao-geral
- Criar cobrança: https://docs.asaas.com/reference/criar-nova-cobranca
- Guia de cobrança: https://docs.asaas.com/docs/guia-de-cobrancas
- Webhooks Asaas: https://docs.asaas.com/docs/webhooks
- Supabase Edge Functions: https://supabase.com/docs/guides/functions
- Supabase Secrets: https://supabase.com/docs/guides/functions/secrets
