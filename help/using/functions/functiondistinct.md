---
product: adobe campaign
title: distinct
description: Saiba mais sobre a função distinta
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 18%

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
| Lista | listDateOnly |

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

`distinct(<listDateOnly>)`

Retorna uma lista de datas.

`distinct(<listBoolean>)`

Retorna uma lista de booleanos.

`distinct(<listDuration>)`

Retorna uma lista de durações.

## Exemplos

`distinct([10,2,10,null])`

Devoluções `[10, 2]`.
