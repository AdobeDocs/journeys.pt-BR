---
product: adobe campaign
title: countWithNull
description: Saiba mais sobre a função countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# countWithNull {#countWithNull}

Conta todos os elementos da lista, incluindo valores nulos.

## Categoria

Agregação

## Sintaxe da função

`countWithNull(<listAny>)`

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

## Assinatura e tipo retornado

`countWithNull(<listAny>)`

Returns an integer.

## Exemplo

`countWithNull([10,2,10,null])`

Returns 4.
