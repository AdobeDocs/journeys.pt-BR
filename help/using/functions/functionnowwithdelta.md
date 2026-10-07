---
product: adobe campaign
title: nowWithDelta
description: Saiba mais sobre a função nowWithDelta
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
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
source-wordcount: '110'
ht-degree: 7%
---
# nowWithDelta {#nowWithDelta}

Retorna o datetime atual incluindo um deslocamento. Se uma ID de fuso horário for especificada, o deslocamento de fuso horário será aplicado. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

## Categoria

Data

## Sintaxe da função

`nowWithDelta(<parameters>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| delta | valor inteiro positivo ou negativo |
| parte de data | anos, meses, dias, horas, minutos ou segundos como uma string |
| id do fuso horário | representação da string do valor do fuso horário. Para obter mais informações, consulte [Tipos de dados](../expression/data-types.md). A ID do fuso horário deve ser uma constante de sequência. Não pode ser uma referência de campo nem uma expressão. |

## Assinaturas e tipo retornado

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Retorna dateTime.

## Exemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Retorna dateTime exatamente 2 horas atrás.
