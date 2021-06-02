---
product: adobe campaign
title: startWith
description: Saiba mais sobre a função startWith
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# startWith {#startWith}

Retorna true se o segundo parâmetro for um prefixo do primeiro.

## Categoria

String

## Sintaxe da função

`startWith(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-------------|--------|
| string | string |
| prefixo | string |

## Assinatura e tipo retornado

`startWith(<string>,<string>)`

Retorne um booleano.

## Exemplo

`startWith("Hello World", "Hello")`

Retorna true.

`startWith("Hello World", "World")`

Retorna false.
