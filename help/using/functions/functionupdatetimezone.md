---
product: adobe campaign
title: updateTimeZone
description: Saiba mais sobre a função updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: tm+mt
source-wordcount: '58'
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

Retorna 28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Se o valor do campo de carimbo de data/hora for `2021-11-16T16:55:12.939318+01:00`, a função retornará `2021-11-17T02:55:12.942115+11:00`.
