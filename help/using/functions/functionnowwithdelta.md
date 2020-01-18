---
title: nowWithDelta
description: Saiba mais sobre a função nowWithDelta
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# nowWithDelta {#nowWithDelta}

Retorna o datetime atual, incluindo um deslocamento. Se uma ID de fuso horário for especificada, o deslocamento de fuso horário será aplicado. Para obter mais informações sobre tipos de dados, consulte [](../expression/data-types.md).

## Categoria

Data

## Sintaxe da função

`nowWithDelta(<parameters>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| delta | valor inteiro positivo ou negativo |
| parte da data | anos, meses, dias, horas, minutos ou segundos como uma sequência |
| id de fuso horário | representação da string do valor do fuso horário. Para obter mais informações, consulte [](../expression/data-types.md). A ID de fuso horário deve ser uma constante de string. Não pode ser uma referência de campo nem uma expressão. |

## Assinaturas e tipo retornado

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Retorna dateTime.

## Exemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Retorna dateTime exatamente 2 horas atrás.
