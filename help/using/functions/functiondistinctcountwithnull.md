---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: Saiba mais sobre a função differentCountWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 25%

---


# distinctCountWithNull {#distinctCountWithNull}

Conta o número de valores diferentes incluindo os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`distinctCountWithNull(<listAny>)`

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

`distinctCountwithNull(<listAny>)`

Retorna um número inteiro.

## Exemplo

`distinctCountWithNull([10,2,10,null])`

Retorna 3.
