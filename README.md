# Marmitas do ano

Sistema de uma página pra planejar a compra do mês, as 14 marmitas da semana e o que comer hoje. Roda no GitHub Pages, sem servidor.

## Arquivos

| Arquivo | Pra quê |
|---|---|
| `index.html` | O sistema inteiro |
| `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Instalar como app na tela do celular |
| `sw.js` | Guarda o site no celular pra abrir sem internet (no mercado, por exemplo) |
| `.nojekyll` | Avisa o GitHub Pages pra publicar os arquivos do jeito que estão |

## Publicar no GitHub Pages

1. No GitHub: **New repository**, nome `marmitas` (ou outro), **Public**, **Create repository**.
2. **Add file → Upload files**, arrasta todos os arquivos desta pasta e clica em **Commit changes**.
   Se o `.nojekyll` não aparecer pra arrastar (o Windows às vezes esconde), tudo bem: o site funciona sem ele.
3. **Settings → Pages**. Em *Build and deployment*: Source **Deploy from a branch**, Branch **main**, pasta **/ (root)**, **Save**.
4. Em 1 ou 2 minutos o site abre em `https://SEU-USUARIO.github.io/marmitas/`.

## Usar o seu domínio

1. **Settings → Pages → Custom domain**: escreve o domínio (exemplo: `marmitas.seudominio.com.br`) e **Save**. O GitHub cria sozinho um arquivo `CNAME` no repositório.
2. No painel onde o domínio está registrado (Registro.br, Hostinger, Cloudflare etc.), cria o DNS:
   - **Subdomínio** (`marmitas.seudominio.com.br`): registro **CNAME**, nome `marmitas`, valor `SEU-USUARIO.github.io`
   - **Domínio sem nada na frente** (`seudominio.com.br`): 4 registros **A** com
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153` e `185.199.111.153`.
     Pro `www`, um **CNAME** `www` → `SEU-USUARIO.github.io`.
   - No Cloudflare, deixa a nuvem **cinza** (DNS only) até o HTTPS ficar pronto.
3. Espera o DNS propagar (de minutos a algumas horas). Quando o GitHub mostrar *DNS check successful*, marca **Enforce HTTPS**.

## Os dados

- Tudo que você marca e anota salva sozinho no navegador, a cada toque.
- Cada endereço guarda os próprios dados: `SEU-USUARIO.github.io/marmitas` e o seu domínio são endereços diferentes. **Configura o domínio antes de começar a usar**, ou conecta o GitHub em Ajustes, que aí os dados vão junto.
- **Ajustes → Salvar sozinho no GitHub** guarda os dados num gist secreto da sua conta, sozinho, uns segundos depois de cada mudança. A chave fica só no aparelho. **Nunca coloca a chave em nenhum arquivo deste repositório.**

## Atualizar o sistema

**Add file → Upload files**, manda o `index.html` novo (ele substitui o antigo) e **Commit changes**. Na próxima vez que o site abrir com internet, já vem a versão nova. Os dados não se perdem.

## Instalar no celular

- **Android (Chrome):** abre o site, menu **⋮** → **Instalar app** ou **Adicionar à tela inicial**.
- **iPhone (Safari):** abre o site, **Compartilhar** → **Adicionar à Tela de Início**.
