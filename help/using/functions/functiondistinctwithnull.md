---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: Saiba mais sobre a função distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%

---


# distinctWithNull {#distinctWithNull}

Retorna os valores distintos da lista. Se a lista tiver pelo menos um valor nulo, um valor nulo estará na lista retornada.

## Categoria

Lista

## Sintaxe da função

`distinctWithNull(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Assinaturas e tipos retornados

`distinctWithNull(<listInteger>)`

Retorna uma lista de números inteiros.

`distinctWithNull(<listDecimal>)`

Retorna uma lista de decimais.

`distinctWithNull(<listString>)`

Retorna uma lista de cadeias de caracteres.

`distinctWithNull(<listDateTimeOnly>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`distinctWithNull(<listDateTime>)`

Retorna uma lista de datetimes.

`distinctWithNull(<listBoolean>)`

Retorna uma lista de booleanos.

`distinctWithNull(<listDuration>)`

Retorna uma lista de durações.

## Exemplos

`distinctWithNull([10,2,10,null])`

Retorna [10, 2, null]
