---
product: adobe campaign
solution: Journey Orchestration
title: count
description: Saiba mais sobre a contagem de funções
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 24%

---


# count {#count}

Conta os elementos da lista que não levam em conta os valores nulos.

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
