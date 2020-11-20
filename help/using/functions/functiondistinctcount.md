---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: Saiba mais sobre a função differentCount
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 25%

---


# distinctCount{#distinctCount}

Conta o número de valores diferentes ignorando os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

Retorna um número inteiro.

## Exemplo

`distinctCount([10,2,10,null])`

Retorna 2.
