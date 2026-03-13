+++
date = '2026-03-12T10:29:35-03:00'
draft = false
title = 'Portuguese TTS'
featureimage = "img/tts.jpg"
+++

# Portuguese TTS CLI

Uma ferramenta de linha de comando para converter arquivos de texto (.txt) em áudio MP3 em português utilizando o Piper TTS offline.

## Repositório

[https://github.com/willycornelissen/pt-tts](https://github.com/willycornelissen/pt-tts)

## Características
- Converte .txt para .mp3 em português brasileiro e europeu.
- Escolha entre vozes masculina (Faber - BR) e feminina (Tugão - PT).
- Operação 100% offline.
- Interface simplificada com geração automática de nome de arquivo.

## Pré-requisitos
- Python 3.9+
- [FFmpeg](https://ffmpeg.org/) (necessário pelo pydub para codificação MP3)

## Instalação
1. Clone o repositório.
2. Crie e ative um ambiente virtual.
3. Instale as dependências:
   ```bash
   pip install .
   ```

## Uso

A forma mais simples de usar é fornecendo apenas o arquivo de texto:
```bash
pt-tts arquivo.txt
```
*Isso criará um arquivo `arquivo.mp3` usando a voz feminina por padrão.*

### Opções de Voz
- Para usar voz **masculina**:
  ```bash
  pt-tts arquivo.txt -m
  ```
- Para usar voz **feminina** (explícito):
  ```bash
  pt-tts arquivo.txt -f
  ```

### Especificando o Arquivo de Saída
Você também pode especificar um nome personalizado para o arquivo de áudio:
```bash
pt-tts entrada.txt saida_customizada.mp3
```

## Modelos
A ferramenta utiliza modelos Piper ONNX localizados no diretório `models/`:
- `models/pt_BR-faber-medium.onnx` (Masculino)
- `models/pt_PT-tugao-medium.onnx` (Feminino)

