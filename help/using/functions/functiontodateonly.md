---
product: adobe campaign
title: toDateOnly
description: Saiba mais sobre a função toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 18%
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
