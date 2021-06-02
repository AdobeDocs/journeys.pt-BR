---
product: adobe campaign
title: count
description: Saiba mais sobre a contagem de funções
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 27%

---

# count {#count}

Conta os elementos da lista que não consideram os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`count(<listAny>)`

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

`count(<listAny>)`

Retorna um número inteiro.

## Exemplo

`count([10,2,10,null])`

Retorna 3.
