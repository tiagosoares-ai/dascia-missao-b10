# dascia-missao-b10 · Landing page ARKON

Landing page demonstrativa da **ARKON**, marca em desenvolvimento voltada à Engenharia de IA para empresas.
Projeto educacional da formação em Engenharia de IA na **DascIA** (missão B10).

> **Aviso:** a ARKON é uma marca em desenvolvimento; a landing page é o projeto demonstrativo e educacional. Textos, serviços e a simulação do terminal são ilustrativos. O botão de contato é apenas demonstrativo: não há e-mail, formulário nem coleta de dados, e nenhuma credencial no projeto.

## Stack
HTML5, CSS3 e JavaScript puro. Sem frameworks, sem build, sem dependências.

## Estrutura
```
index.html            Página única (HTML semântico)
assets/css/           tokens → base → components → sections
assets/js/main.js     Menu mobile, animações de scroll, ano do rodapé
assets/img/og-image.png  Imagem de pré-visualização social (1200×630)
_headers              Cabeçalhos de segurança (Cloudflare Pages)
robots.txt, sitemap.xml, favicon.svg
CLAUDE.md             Contexto e regras para o Claude Code
```

## Rodar localmente
```bash
python3 -m http.server 8000
# abra http://localhost:8000
```

## Publicar no Cloudflare Pages
1. Envie o repositório ao GitHub.
2. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git.
3. Framework preset: **None** · Build command: *(vazio)* · Output directory: `/`.
4. **Confirmar a URL definitiva (obrigatório após o deploy).** A URL `https://dascia-missao-b10.pages.dev/` é uma suposição baseada no nome do projeto. Depois do deploy, confira o endereço real e, se for diferente, substitua-o em:
   - `index.html`: `canonical`, `og:url`, `og:image`, `twitter:image` e o `url` do JSON-LD;
   - `robots.txt` (linha `Sitemap`);
   - `sitemap.xml` (`<loc>`).

   Dica: `grep -rn "pages.dev" .` lista todos os pontos. Para testar o cartão social, use o depurador de compartilhamento da rede desejada depois do deploy.

## Decisões
- **Mobile-first:** CSS base para celular; `min-width` amplia para telas maiores.
- **Acessibilidade:** HTML semântico, foco visível, link de pular conteúdo, menu com `aria-expanded`, `prefers-reduced-motion`.
- **Segurança:** CSP restritiva sem scripts/estilos inline, `.gitignore` bloqueando segredos.
- **Fontes:** pilha de fontes do sistema (zero requisições e zero tracking). Fontes self-hosted podem ser adicionadas depois em `assets/fonts/`.
- **Imagem Open Graph:** `assets/img/og-image.png` foi gerada a partir de um template HTML renderizado no Chromium (1200×630). Para alterá-la, recrie o PNG com as mesmas dimensões.
- **Sem alegações comerciais:** a página não traz métricas, clientes ou depoimentos; tudo é rotulado como demonstrativo.

## Revisão pré-deploy (resumo)
Lighthouse (local, Chromium headless): Performance, Acessibilidade, Boas práticas e SEO em 100, em mobile e desktop. axe-core sem violações. Layout testado de 320px a 1920px sem rolagem horizontal. A compressão (Brotli/gzip) e o cache são aplicados pelo Cloudflare Pages; um servidor local simples não os aplica.
