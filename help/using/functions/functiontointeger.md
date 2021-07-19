---
product: adobe campaign
title: toInteger
description: Saiba mais sobre a função toInteger
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 15%

---

# toInteger {#toInteger}

Converte um valor de argumento em um inteiro.

## Categoria

Conversão

## Sintaxe da função

`toInteger(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | converte o valor da string como um inteiro |
| dateTime | converte a data como o número de milissegundos (milissegundos de época) |
| decimal | é convertido em inteiro pela remoção da parte decimal (por exemplo: 1,5 passa a 1) |
| booleano | converte o valor booleano como 1 se verdadeiro, 0 se falso |

## Assinaturas e tipo retornado

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Retorna um número inteiro.

## Exemplos

`toInteger("4")`

Retorna 4.
