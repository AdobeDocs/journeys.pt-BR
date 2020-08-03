---
title: distinctCountWithNull
description: Saiba mais sobre a função differentCountWithNull
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
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
