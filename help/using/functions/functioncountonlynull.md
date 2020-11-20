---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Saiba mais sobre a função countOnlyNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 26%

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
