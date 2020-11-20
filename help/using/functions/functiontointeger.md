---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Saiba mais sobre a função toInteger
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

Converte um valor de argumento em um número inteiro.

## Categoria

Conversão

## Sintaxe da função

`toInteger(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | converte o valor da string como um número inteiro |
| dateTime | converte a data como o número de milissegundos (milissegundos) |
| decimal | converte em número inteiro removendo a parte decimal (por exemplo: 1,5 passa a ser 1) |
| booleano | converte o valor booliano como 1 se for verdadeiro, 0 se for falso |

## Assinaturas e tipo retornado

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Retorna um número inteiro.

## Exemplos

`toInteger(4)`

Retorna 4.
