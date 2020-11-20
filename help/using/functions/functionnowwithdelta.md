---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Saiba mais sobre a função nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

Retorna o datetime atual, incluindo um deslocamento. Se uma ID de fuso horário for especificada, o deslocamento de fuso horário será aplicado. For more information on data types, refer to [this page](../expression/data-types.md).

## Categoria

Data

## Sintaxe da função

`nowWithDelta(<parameters>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| delta | valor inteiro positivo ou negativo |
| parte da data | anos, meses, dias, horas, minutos ou segundos como uma sequência |
| id de fuso horário | representação da string do valor do fuso horário. Para obter mais informações, consulte Tipos [de](../expression/data-types.md)dados. A ID de fuso horário deve ser uma constante de string. Não pode ser uma referência de campo nem uma expressão. |

## Assinaturas e tipo retornado

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Retorna dateTime.

## Exemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Retorna dateTime exatamente 2 horas atrás.
