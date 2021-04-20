---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: Saiba mais sobre a função distinta
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 14%

---


# distinct {#distinct}

Retorna os valores distintos da lista sem valores nulos.

## Categoria

Lista

## Sintaxe da função

`distinct(<parameter>)`

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

`distinct(<listInteger>)`

Retorna uma lista de números inteiros.

`distinct(<listDecimal>)`

Retorna uma lista de decimais.

`distinct(<listString>)`

Retorna uma lista de cadeias de caracteres.

`distinct(<listDateTimeOnly>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`distinct(<listDateTime>)`

Retorna uma lista de datetimes.

`distinct(<listBoolean>)`

Retorna uma lista de booleanos.

`distinct(<listDuration>)`

Retorna uma lista de durações.

## Exemplos

`distinct([10,2,10,null])`

Retorna `[10, 2]`.
