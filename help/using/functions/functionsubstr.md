---
product: adobe campaign
title: substr
description: Saiba mais sobre a função substr
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# substr {#substr}

Retorna a subcadeia de caracteres da expressão de cadeia de caracteres entre o índice inicial e o índice final. Se o índice final não estiver definido, ele será entre o índice inicial e o final.

## Categoria

String

## Sintaxe da função

`substr(<parameters>)`

## Parâmetros

| Parâmetro | tipo |
|-------------|----------|
| sequência de caracteres | sequência de caracteres |
| beginIndex | inteiro |
| endIndex | inteiro |

## Assinatura e tipo retornado

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retorna uma string.

## Exemplo

`substr("Hello World",6)`

Retorna &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Retorna &quot;Olá&quot;.
