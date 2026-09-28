# Gestão de Estampagem DTF — pacote PWA

Este ficheiro ZIP contém a app pronta a ser publicada como PWA (Progressive Web App):

```
index.html          → a aplicação
manifest.json        → identidade da app (nome, ícones, cor)
sw.js                 → permite funcionar offline
icons/                → ícones em vários tamanhos
```

## Passo 1 — Colocar os ficheiros online (URL fixo e público)

O PWABuilder precisa de um URL público para "ler" a app. Opções gratuitas e simples:

- **Netlify Drop** (mais simples): vai a https://app.netlify.com/drop e arrasta a pasta
  para lá. Em segundos recebes um URL (ex: `https://algo-aleatorio.netlify.app`).
- **GitHub Pages**: cria um repositório, faz upload destes ficheiros, ativa "Pages" nas
  definições do repositório.
- **Vercel**: semelhante ao Netlify, também com plano gratuito.

Qualquer uma serve — o importante é ficares com um URL do tipo `https://.../index.html`
ou `https://.../` acessível publicamente.

## Passo 2 — Gerar o instalável com o PWABuilder

1. Vai a https://www.pwabuilder.com
2. Cola o URL que obtiveste no Passo 1
3. Clica em "Start" — o PWABuilder analisa o `manifest.json` e o `sw.js` automaticamente
4. Na secção Android, escolhe "Package for stores" (ou similar) para gerares um `.apk`
   ou `.aab` pronto a instalar ou a submeter à Google Play

## Nota importante sobre os dados

Dentro do Claude, os dados (clientes, orçamentos, encomendas...) são partilhados
automaticamente por toda a equipa. Fora do Claude — ou seja, quando instalas esta versão
a partir do teu próprio hosting — a app passa a guardar os dados **apenas no aparelho**
onde está instalada (não há partilha automática entre telemóveis).

Se mais tarde precisares mesmo de dados partilhados numa app instalada fora do Claude,
isso implica ligar a app a uma base de dados na nuvem (ex: Firebase, Supabase) — é um
passo adicional de engenharia que posso ajudar a preparar, mas não está incluído neste
pacote.
