## Guia de Uso do Código Python para Geração de Resumos

Este documento fornece instruções detalhadas sobre como usar o código Python fornecido para gerar resumos profissionais a partir de arquivos de texto. O código utiliza a API do Google Generative AI e a biblioteca `python-docx` para criar documentos Word.

## Pré-requisitos

Antes de executar o código, você precisa garantir que as seguintes bibliotecas estejam instaladas:

- `google-generativeai`
- `python-docx`
- `nltk`

Você pode instalar essas bibliotecas usando o seguinte comando:

```
bash
pip install -r requirements.txt
```

## Estrutura do Projeto

O código deve ser organizado da seguinte forma:

```
text/seu_projeto
│
├── gpt.py
├── config.json
└── seu_arquivo.txt
```

- **gpt.py**: O arquivo que contém o código para gerar o resumo.
- **config.json**: Um arquivo de configuração que deve conter a chave da API do Google e o caminho base para os arquivos.(Sugiro a criação de uma pasta dentro da raiz do projeto para separar o código dos arquivos .txt e .docx)
- **seu_arquivo.txt**: O arquivo de texto que você deseja resumir.

## Configuração do Arquivo `config.json`

O arquivo `config.json` deve ter o seguinte formato:

```
json{
  "GOOGLE_API_KEY": "sua_chave_api_aqui",
  "caminho_base": "caminho/para/seu_arquivo"
}
```

Substitua `"sua_chave_api_aqui"` pela sua chave de API do Google e `"caminho/para/seu_arquivo"` pelo caminho base do arquivo de texto que você deseja resumir (sem a extensão).

## Executando o Código

Para executar o código, siga os passos abaixo:

1. **Prepare seu arquivo de texto**: Certifique-se de que o arquivo de texto que você deseja resumir esteja no formato `.txt` e que o caminho esteja correto no arquivo `config.json`.

2. 

   **Execute o script**: No terminal, navegue até o diretório onde o arquivo `gpt.py` está localizado e execute o seguinte comando:

   

   ```
   bash
   python gpt.py
   ```

   

3. **Verifique o resultado**: O resumo será gerado e salvo em um arquivo `.docx` no mesmo diretório, com o nome baseado no caminho base definido no `config.json`.

## Funcionalidades do Código

- **Carregamento de Configurações**: O código carrega a configuração a partir do arquivo `config.json`, incluindo a chave da API e o caminho base.
- **Leitura de Arquivo de Texto**: O conteúdo do arquivo de texto é lido e processado para gerar um resumo.
- **Processamento de Texto**: O texto é tokenizado, e as stopwords são removidas para análise de frequência de palavras.
- **Geração de Resumo**: Um prompt é enviado para a API do Google Generative AI, solicitando um resumo profissional baseado no conteúdo original.
- **Salvamento do Resumo**: O resumo gerado é salvo em um arquivo Word, formatado de acordo com as especificações.

## Considerações Finais

Certifique-se de que a chave da API do Google esteja ativa e que você tenha as permissões necessárias para usar a API. O código foi projetado para gerar resumos de maneira eficiente, mas a qualidade do resumo pode variar dependendo do conteúdo do texto original.