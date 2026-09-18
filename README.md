# Site oficial do Tokly

Site estático do Tokly, um bot do Telegram que recebe links públicos do TikTok e entrega vídeo ou áudio MP3. O projeto usa somente HTML e CSS locais, sem frameworks, rastreamento, formulários ou JavaScript obrigatório.

## Estrutura

- `index.html`: página inicial.
- `privacy/index.html`: Política de Privacidade.
- `terms/index.html`: Termos de Uso.
- `404.html`: página para endereços inexistentes.
- `styles.css`: identidade visual e responsividade.
- `assets/`: favicon e outros ativos locais.
- `_headers` e `_redirects`: segurança e roteamento no Netlify.
- `robots.txt`, `sitemap.xml` e `site.webmanifest`: descoberta e metadados.

## Prévia local

Abra um terminal nesta pasta e execute:

```powershell
python -m http.server 8080
```

Depois, acesse `http://localhost:8080` no navegador. Encerre o servidor com `Ctrl+C`.

## Testes

Com Python 3 instalado, execute na raiz do projeto:

```powershell
python -m unittest discover -s tests -v
```

Os testes verificam rotas, links, conteúdo público, metadados, acessibilidade básica e ausência de recursos externos obrigatórios.

## Publicação manual no Netlify

1. Gere um ZIP contendo os arquivos e pastas públicos desta raiz — os arquivos devem ficar na raiz do ZIP, não dentro de uma pasta adicional.
2. Não inclua `.git`, `tests`, `docs`, caches ou relatórios de desenvolvimento no ZIP público.
3. No painel do Netlify, abra o projeto do Tokly e use a área de deploy manual para enviar o ZIP ou a pasta descompactada.
4. Aguarde a publicação e verifique a página inicial, `/privacy/`, `/terms/` e um endereço inexistente para confirmar a página 404.
5. Confirme também o botão do bot, a navegação em celular e computador, o cadeado HTTPS e `https://toklybot.netlify.app/sitemap.xml`.

O arquivo `_redirects` mantém as rotas existentes e devolve status 404 real para endereços desconhecidos. O arquivo `_headers` aplica políticas de segurança e cache compatíveis com o conteúdo estático.

## Alterações seguras

- Bot do Telegram: procure por `https://t.me/toklyappbot` nos arquivos HTML.
- Contatos: procure por `contatojrconceicao@gmail.com` e `@bartnovaks2` nos arquivos HTML.
- Limites do serviço: procure por `45 MB`, `20` e `UTC−3` na página inicial e nas páginas legais; mantenha as informações consistentes.
- Cores, espaçamento e efeitos: altere os tokens no início de `styles.css`.
- Endereço público: se o domínio mudar, atualize os links canônicos dos HTMLs, `robots.txt` e `sitemap.xml` em conjunto.

Nunca coloque o token do bot, senhas, chaves de API ou outros segredos neste site ou no ZIP de publicação. O token deve permanecer apenas nas variáveis de ambiente privadas do serviço que executa o bot.
