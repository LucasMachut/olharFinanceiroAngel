# Olhar financeiro — Angel

Calculadora de preços e painel para fotógrafo, em português brasileiro.

Ela parte de um salário mensal pretendido, deduz o valor de uma hora de trabalho,
acrescenta uma margem fixa, e precifica cada trabalho a partir do tempo que ele
realmente toma. O painel acompanha o que foi proposto, faturado e recebido.

**[Manual de uso](manual.html)** — leia antes de usar. Explica a lógica inteira,
cada parâmetro, e o que conferir na aba Parâmetros.

## O cálculo

```
1h do seu tempo = salário mensal pretendido ÷ (dias faturáveis × 4 × horas por dia)
1h vendida      = 1h do seu tempo ÷ (1 − margem)
preço           = custos diretos + (horas × 1h vendida) × multiplicador de prazo
```

O controle do piso por hora é feito sobre `(preço − custos diretos) ÷ horas`.
Custos diretos são adiantados e devolvidos iguais: nunca são remuneração, e
incluí-los no controle deixaria passar trabalhos no prejuízo.

O campo «dias faturáveis por semana» conta os dias vendidos a um cliente, não os
dias trabalhados. Prospecção, orçamento e administrativo são cobertos pela
margem, não pelas horas do trabalho.

## Os dados

Tudo vive no `localStorage` do navegador. Sem conta, sem servidor, sem nuvem.
O botão **Copiar o JSON**, na aba Parâmetros, exporta o estado inteiro — é o
backup e a forma de levar os ajustes para outro computador.

## Os arquivos

| Arquivo | Conteúdo |
|---|---|
| `index.html` | O aplicativo inteiro: calculadora, permuta, parâmetros, painel |
| `manual.html` | O manual de uso |
| `.github/workflows/pages.yml` | Publicação automática no GitHub Pages a cada push em `main` |

## Publicar

`Settings → Pages → Source: GitHub Actions`, depois um push em `main`.

Os valores de partida são os do [@lucasmachut__](https://instagram.com/lucasmachut__)
e servem só de exemplo coerente. Troque-os na aba Parâmetros.
