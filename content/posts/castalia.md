+++
date = '2026-11-16T07:40:20-03:00'
draft = false
title = 'Diário de Castália'
featureimage = "img/castalia.png"
+++

# Castalia — Ghost Newspaper Clone (GitHub Pages + Firebase)

Aplicação Single-Page Application (SPA) inspirada no CMS **Ghost** e no tema editorial **Newspaper**, desenvolvida com **React + TypeScript + Vite + Tailwind CSS**, pronta para publicação no **GitHub Pages** (com migração opcional para Firebase Hosting) e backend no **Firebase** (**Cloud Firestore**, **Firebase Authentication** e opcionalmente **Firebase Storage**).

## Arquitetura

- **Leitor Público (`/`, `/post/:slug`, `/tag/:tag`)**:
  - Estética editorial clássica (masthead com fonte `chomsky.otf`, ticker *Últimas*, grid jornalístico de 3 colunas, leitura de artigos em Markdown sanitizado com `rehype-sanitize`).
  - Cache offline persistente do Firestore (`persistentLocalCache` + `persistentMultipleTabManager`).
- **Painel Administrativo (`/admin/login`, `/admin`, `/admin/editor`, `/admin/editor/:slug`)**:
  - Carregado sob demanda via `React.lazy()` + `Suspense` e protegido por `AuthGuard` e regras de segurança Firebase baseadas no `ADMIN_UID`.
  - Editor Markdown com preview ao vivo, seleção de tags, upload/compressão WebP client-side ou URL externa de imagens, e trava de slug após publicação.
- **GitHub Pages + URLs Limpas**:
  - `vite.config.ts` usa `base: '/'` por padrão (para o domínio customizado `castalia.willy.dev.br` ou Firebase Hosting; configurável via `VITE_BASE_PATH=/castalia/` para subcaminho padrão do `github.io`).
  - `BrowserRouter` usa `basename={import.meta.env.BASE_URL}` combinado com `public/404.html` + restauração de rota em `index.html`, `public/.nojekyll` e `public/CNAME` para suportar URLs limpas no GitHub Pages.

