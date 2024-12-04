# Cálculo de Moda no Power BI com DAX

## Descrição
Este repositório contém um exemplo de medida DAX para calcular a **moda** (valor mais frequente) no Power BI. A moda é útil para analisar dados categóricos e identificar padrões que outras métricas, como média ou mediana, não revelam.

---

## Código
```DAX
VAR TabelaFrequencia =
   SUMMARIZE(
       NOME DA TABELA,
       NOME DA TABELA[NOME DA COLUNA],
       "Frequencia", COUNT(NOME DA TABELA[NOME DA COLUNA])
   )
VAR MaiorFrequencia =
   MAXX(
       TabelaFrequencia,
       [Frequencia]
   )
RETURN
   CONCATENATEX(
       FILTER(TabelaFrequencia, [Frequencia] = MaiorFrequencia),
       NOME DA TABELA[NOME DA COLUNA],
       ","
   )

