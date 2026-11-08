# IA Estendida — pacote completo

Pacote consolidado a partir dos arquivos disponíveis nesta conversa, com nomes padronizados para publicação em hospedagem estática/GitHub Pages.

## Arquivos principais
- `index.html`: portal/plataforma.
- `profissional.html`: curso profissional com demonstração gratuita na interface e acesso integral condicionado à licença.
- `kids.html`: módulo infantil.
- `termos.html`, `privacidade.html`, `contrato.html`: documentos institucionais/jurídicos.
- `Apostila_Pratica_IA_Estendida_14_Etapas.pdf` e `apostila-aplicativo.html`: materiais de apoio.
- `certificado-padrao.js`, `qr-local.js` e `certificado-premium-modelo.html`: componentes de certificado/QR disponíveis.

## Publicação
1. Faça backup da versão atual.
2. Extraia todos os arquivos para a raiz da mesma branch publicada no GitHub Pages.
3. Preserve os nomes dos arquivos.
4. Teste login, demonstração, compra, retorno de acesso, progresso e validação do certificado.

## Licenciamento e webhook
A interface do curso está preparada para consultar `iae_my_access()` e exibir a demonstração para quem ainda não tem licença. O backend Supabase e a Edge Function `iae-kiwify-webhook` foram preparados anteriormente. **A ativação real depende de cadastrar o segredo `IAE_KIWIFY_WEBHOOK_TOKEN` no Supabase e configurar a URL/eventos correspondentes no painel Kiwify.** Não há credenciais nem segredos neste ZIP.

Produto Kiwify: `f107be20-d645-11f1-91c1-5744ca950a55`  
Checkout: `https://pay.kiwify.com.br/A1SE8Tb`  
Preço configurado na interface: R$ 49,90  
Validade prevista: 12 meses após confirmação do pagamento.

## Limitações conhecidas antes da publicação
- O conteúdo do curso ainda está incorporado no HTML; a demonstração na interface não impede inspeção do código-fonte. Para proteção robusta, o conteúdo integral precisa ser servido por endpoint autenticado ou armazenamento protegido.
- Os arquivos `certificado-premium.css` e `certificado-arte-premium.png`, referenciados pela documentação/HTML anterior, não estavam entre os arquivos disponíveis e não foram inventados nem incluídos. Verifique esses recursos antes de considerar a publicação final do certificado premium.
- O ZIP reúne os arquivos disponíveis; não substitui teste real de compra, webhook, autenticação e emissão/validação de certificado em produção.

Copyright © 2026 Nailson Rodrigues de Lima / Lima Virtual Cursos.
