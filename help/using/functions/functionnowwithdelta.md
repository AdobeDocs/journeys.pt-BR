---
product: adobe campaign
title: nowWithDelta
description: Saiba mais sobre a função nowWithDelta
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 6%

---

# nowWithDelta {#nowWithDelta}

Retorna a data e hora atual, incluindo um deslocamento. Se um ID de fuso horário for especificado, o deslocamento de fuso horário será aplicado. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

## Categoria

Data

## Sintaxe da função

`nowWithDelta(<parameters>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| delta | valor inteiro positivo ou negativo |
| parte da data | anos, meses, dias, horas, minutos ou segundos como uma string |
| id de fuso horário | representação de string do valor de fuso horário. Para obter mais informações, consulte [Tipos de dados](../expression/data-types.md). A ID de fuso horário deve ser uma constante de string. Não pode ser uma referência de campo nem uma expressão. |

## Assinaturas e tipo retornado

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Retorna dateTime.

## Exemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Retorna dateTime exatamente 2 horas atrás.
