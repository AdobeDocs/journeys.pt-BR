---
product: adobe campaign
title: distinctCount
description: Saiba mais sobre a função distinctCount
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 29%

---

# distinctCount{#distinctCount}

Conta o número de valores diferentes que ignoram os valores nulos.

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
