# Categorização Supervisionada de Frases — CERAMIDAS

Este projeto tem como objetivo realizar a categorização supervisionada de frases em português, utilizando técnicas de processamento de linguagem natural (PLN) com a biblioteca SpaCy. O foco está em identificar as palavras mais relevantes de cada categoria a partir de um conjunto de frases, e posteriormente classificar novas frases de acordo com essas categorias.

## Funcionalidades

- **Pré-processamento de texto:** Remoção de acentos, lematização e filtragem de palavras genéricas.
- **Extração de palavras-chave:** Identificação das 10 palavras mais frequentes e relevantes para cada categoria.
- **Classificação de frases:** Algoritmo que sugere as 3 categorias mais prováveis para uma nova frase, baseado nas palavras-chave extraídas.
- **Exportação de resultados:** Geração de um arquivo CSV (`resultado.csv`) com as palavras mais relevantes por categoria.

## Como funciona

1. **Leitura dos dados:** O projeto lê um arquivo Excel (`rawdata.xlsx`) contendo frases e suas respectivas categorias.
2. **Processamento:** Cada frase é processada para remover acentos, lematizar palavras e eliminar termos genéricos.
3. **Contagem e seleção:** As palavras mais frequentes de cada categoria são selecionadas e salvas.
4. **Classificação:** Uma função permite classificar novas frases, retornando as categorias mais prováveis.

## Requisitos

- Python 3.12+
- pandas
- spacy==3.5.3
- pt_core_news_sm (modelo SpaCy para português)
- unicodedata

## Instalação

1. Instale as dependências:
   ```bash
   pip install pandas spacy==3.5.3
   python -m spacy download pt_core_news_sm
   ```

2. Coloque o arquivo `rawdata.xlsx` na mesma pasta do projeto.

## Como usar

- Execute o notebook `dicionario.ipynb` para processar os dados e gerar o arquivo `resultado.csv`.
- Utilize a função `classificar_frase(frase, df_resultado)` para classificar novas frases.

## Exemplo de uso

```python
print(classificar_frase('gostei de tudo', df_resultado))
```

## Observações

- O projeto pode ser expandido para incluir novas categorias ou adaptar a lista de palavras genéricas.
- O desempenho da classificação depende da qualidade e quantidade dos dados de entrada. 