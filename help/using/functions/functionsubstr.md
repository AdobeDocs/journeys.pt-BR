---
product: adobe campaign
title: substr
description: Saiba mais sobre a função substr
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 9%

---

# substr {#substr}

Retorna a substring da expressão da string entre o índice begin e o índice end. Se o índice final não estiver definido, ele estará entre o índice inicial e o final.

## Categoria

String

## Sintaxe da função

`substr(<parameters>)`

## Parâmetros

| Parâmetro | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Assinatura e tipo retornado

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retorne uma string.

## Exemplo

`substr("Hello World",6)`

Retorna &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Retorna &quot;Hello&quot;.
