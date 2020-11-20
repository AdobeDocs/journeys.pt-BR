---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Saiba mais sobre a função toDecimal
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

---


# toDecimal {#toDecimal}

Converte um valor de argumento em um valor decimal, dependendo de seu tipo.

## Categoria

Conversão

## Sintaxe da função

`toDecimal(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | converte o valor da string como um decimal |
| dateTime | converte a data como o número de milissegundos (milissegundos) |
| booleano | converte o valor booliano como 1 se for verdadeiro, 0 se for falso |
| integer | converte para um decimal (por exemplo).: 1 se torna 1,0) |

## Assinaturas e tipos retornados

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Retorna um decimal.

## Exemplos

`toDecimal("4.0")`

Retorna 4.0.
