---
product: adobe campaign
title: updateTimeZone
description: Saiba mais sobre a função updateTimeZone
feature: Journeys
role: Developer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 10%

---

# updateTimeZone {#updateTimeZone}

Retorna uma nova data e hora, com um novo fuso horário no mesmo instante.

## Categoria

Data

## Sintaxe da função

`updateTimeZone(<parameters>)`

## Parâmetros

* id do fuso horário: string
* dateTime

## Assinatura e tipo retornado

`updateTimeZone(<dateTime>,<timeZone id>)`

Retorna um datetime.

## Exemplos

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Retorna 28/08/2019:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Se o valor do campo de carimbo de data/hora for `2021-11-16T16:55:12.939318+01:00`, a função retornará `2021-11-17T02:55:12.942115+11:00`.
