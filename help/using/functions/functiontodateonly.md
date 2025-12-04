---
product: adobe campaign
title: toDateOnly
description: Saiba mais sobre a função toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# toDateOnly{#toDateOnly}

Converte um valor de argumento em um valor somente de data.

## Categoria

Conversão

## Sintaxe da função

`toDateOnly(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data no formato ISO-8601 ou &quot;AAAA-MM-DD&quot; (formato Data XDM) | sequência de caracteres |
| data | data |

## Assinaturas e tipos retornados

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`toDateOnly("2016-08-18")`

retorna um objeto dateOnly que representa 18 de agosto de 2016.
