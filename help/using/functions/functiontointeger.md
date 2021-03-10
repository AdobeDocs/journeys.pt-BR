---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Saiba mais sobre a função toInteger
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 8%

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
