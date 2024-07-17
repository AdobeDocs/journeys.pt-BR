---
product: adobe campaign
title: countOnlyNull
description: Saiba mais sobre a função countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# countOnlyNull {#countOnlyNull}

Conta o número de valores nulos na lista.

## Categoria

Agregação

## Sintaxe da função

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Retorna um inteiro.

## Exemplo

`countOnlyNull([10,2,10,null])`

Retorna 1.
