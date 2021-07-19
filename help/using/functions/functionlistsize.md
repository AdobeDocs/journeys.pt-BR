---
product: adobe campaign
title: listSize
description: Saiba mais sobre a função listSize
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: c0d34a8d-33e9-4c7b-9b7d-a1b21ed96d35
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 34%

---

# listSize {#listSize}

Conta o número de elementos na lista.

## Categoria

Lista

## Sintaxe da função

`listSize(<parameters>)`

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

## Assinaturas e tipo retornado

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Retorna um número inteiro.

## Exemplo

`listSize([10,2,3])`

Retorna 3.
