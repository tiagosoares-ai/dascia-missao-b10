# CLAUDE.md · dascia-missao-b10

Landing page estática da ARKON (empresa fictícia). Projeto educacional; o usuário é iniciante em Engenharia de IA, então explique decisões de forma didática. Responda em pt-BR.

## Regras
- Somente HTML5, CSS3 e JS vanilla. **Não adicionar dependências nem etapa de build.**
- Mobile-first: estilos base para celular, ampliar com `@media (min-width: ...)`.
- Cores, fontes e espaçamentos só via variáveis em `assets/css/tokens.css`.
- Sem scripts ou estilos inline (a CSP em `_headers` bloqueia). Exceção: JSON-LD no `<head>`.
- **Nunca** incluir credenciais, chaves, e-mails ou dados reais. Se precisar de exemplo, use `example.com`, nunca apresentado como contato verdadeiro.
- **Não inventar informações comerciais** (métricas, clientes, depoimentos, preços). A página deve continuar identificada como projeto demonstrativo e a ARKON como empresa fictícia.
- Ao mudar o domínio, atualizar `canonical`, `og:*`, `twitter:image`, JSON-LD, `robots.txt` e `sitemap.xml` (ver README).
- Não usar logos ou marcas de terceiros.
- Acessibilidade WCAG AA: semântica, contraste, foco visível, teclado, `prefers-reduced-motion`.
- Um único `<h1>`. Textos em pt-BR.
- Não fazer commit, push ou deploy sem autorização explícita do usuário.

## Estrutura
CSS: `tokens.css` → `base.css` → `components.css` → `sections.css`. JS: `assets/js/main.js`.

## Verificação
```bash
python3 -m http.server 8000
```
Checar de 320px a 1920px: sem rolagem horizontal, sem erros no console, navegação por teclado, Lighthouse ≥ 95.
