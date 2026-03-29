+++
date = '2026-03-28T21:43:45-03:00'
draft = false 
title = 'Photo Label'
featureimage = "img/bitcoin.webp"
+++

# Photo Label

Um visualizador de imagens simples construído com Go e a biblioteca de interface gráfica Fyne.

## Repositório

[https://github.com/willycornelissen/photo-label](https://github.com/willycornelissen/photo-label)

## Recursos
- Carregar imagens via linha de comando.
- Suporte para JPEG, PNG, GIF, BMP e WebP.
- Integração com desktop Linux (clique duplo para abrir imagens).
- Mantém a proporção da imagem ao redimensionar.
- **Novo**: Visualização de descrições (labels) em janelas flutuantes com suporte a Markdown.
- **Novo**: Integração com a API Google Gemini para descrever fotos automaticamente.

## Pré-requisitos
- Go 1.22+
- Compilador C (para o Fyne)
- Headers de desenvolvimento OpenGL
- **Opcional**: Variável de ambiente `GOOGLE_API_KEY` para as funções de IA.

## Compilação
```bash
go build -o photo-label src/main.go
```

## Instalação (Linux)
```bash
./scripts/install-linux.sh ./photo-label
```
