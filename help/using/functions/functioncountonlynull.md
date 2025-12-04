---
product: adobe campaign
title: countOnlyNull
description: Saiba mais sobre a função countOnlyNull
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
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
