---
product: adobe campaign
title: endWithIgnoreCase
description: Saiba mais sobre a função endWithIgnoreCase
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Verifica se a primeira string de argumento termina com uma string específica (segunda string de argumento), não considerando o caso.

## Categoria

String

## Sintaxe da função

`endWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| sufixo | string |

## Assinatura e tipo retornado

`endWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`endWithIgnoreCase("rowing is great', "AT")`

Retorna true.
