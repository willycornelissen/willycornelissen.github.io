+++
date = '2026-03-03T09:00:10-03:00'
draft = false
title = 'Bitcoin Panel'
+++

# Bitcoin Panel CLI

Uma ferramenta de linha de comando (CLI) escrita em Go para consultar a cotação atual do Bitcoin em Dólar (USD) e Real (BRL), com suporte a fallback automático entre APIs.

## 🚀 Funcionalidades

- **Cotação em tempo real:** Mostra o valor do Bitcoin em USD e BRL.
- **Resiliência:** Se a API principal (**CoinGecko**) falhar, a aplicação consulta automaticamente uma fonte secundária (**Blockchain.info**).
- **Saída Formatada:** Exibe os dados em uma tabela limpa e organizada no terminal.
- **Transparência:** Informa qual fonte (API) foi utilizada para obter a cotação exibida.

## 🛠️ Tecnologias Utilizadas

- [Go](https://go.dev/) (v1.22+)
- [Cobra](https://github.com/spf13/cobra) - Framework para aplicações CLI.
- [Tablewriter](https://github.com/olekukonko/tablewriter) - Formatação de tabelas no terminal.

## 📋 Pré-requisitos

Certifique-se de ter o Go instalado em sua máquina. Você pode verificar rodando:

```bash
go version
```

## 🔧 Instalação e Execução

1.  **Clonar o repositório ou baixar os arquivos:**
    ```bash
    git clone <url-do-repositorio>
    cd bitcoin-panel
    ```

2.  **Instalar dependências:**
    ```bash
    go mod tidy
    ```

3.  **Executar diretamente:**
    ```bash
    go run main.go
    ```

## 🏗️ Gerando o Executável

Para compilar a aplicação e gerar um binário:

```bash
go build -o bitcoin-panel main.go
```

Após o build, você pode executar o programa usando:

```bash
./bitcoin-panel
```

## 📊 Exemplo de Saída

```text
+-------------+--------------+-----------------+
|    MOEDA    |    VALOR     |      FONTE      |
+-------------+--------------+-----------------+
| Dólar (USD) | $ 67107.13   | CoinGecko       |
| Real (BRL)  | R$ 347883.37 | CoinGecko       |
+-------------+--------------+-----------------+
```