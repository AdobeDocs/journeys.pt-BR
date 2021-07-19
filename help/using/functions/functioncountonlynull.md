---
product: adobe campaign
title: countOnlyNull
description: Saiba mais sobre a função countOnlyNull
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 34%

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

## Assinatura e tipo retornado

`countOnlyNull(<listAny>)`

Retorna um número inteiro.

## Exemplo

`count([10,2,10,null])`

Retorna 1.
