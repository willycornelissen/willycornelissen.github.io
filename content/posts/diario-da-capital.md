+++
date = '2026-08-20T14:50:00-03:00'
draft = false
title = 'Diário da Capital'
featureimage = "img/diario-da-capital.jpg"
+++

# Diário da Capital

Jornal digital estático: edições com resumos (gerados por LLM) das últimas
notícias de fontes cadastradas. Site público no GitHub Pages; edições geradas
sob demanda pelo administrador via GitHub Actions.

## Site

[https://clipping.willy.dev.br](https://clipping.willy.dev.br)

## Repositório

[https://github.com/willycornelissen/clipping](https://github.com/willycornelissen/clipping)

## Recursos

- **Edições sob demanda** — o administrador dispara o workflow "Gerar Edição";
  o bot coleta as notícias, gera os resumos com LLM, commita a edição e o site
  é republicado automaticamente.
- **Fontes declarativas** — cadastro de fontes em `data/sources.yml`, com
  suporte a RSS (preferível) e scraping via seletores CSS para sites sem feed.
- **LLM plugável** — qualquer API compatível com o esquema OpenAI (OpenAI,
  OpenRouter, DeepSeek, Groq, Ollama, Gemini) via secrets/variables do Actions.
- **Resiliência** — se uma fonte estiver fora do ar, a edição é gerada sem ela.
- **Domínio próprio** — publicado em `clipping.willy.dev.br`.

## Stack

- **Frontend:** React 19 + Vite + React Router.
- **Geração:** scripts em Node (`generator/`) com `rss-parser` e `cheerio`.
- **Deploy:** GitHub Actions → GitHub Pages (source: GitHub Actions).
- **Testes:** Vitest + Testing Library.

## Estrutura

| Caminho | Conteúdo |
| --- | --- |
| `generator/` | Scripts de geração das edições |
| `src/` | Site React |
| `data/` | Fontes (`sources.yml`) e edições |
| `.github/workflows/` | Actions (`deploy.yml`, `gerar-edicao.yml`) |