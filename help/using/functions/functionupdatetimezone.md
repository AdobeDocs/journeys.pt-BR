---
product: adobe campaign
title: updateTimeZone
description: Saiba mais sobre a função updateTimeZone
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

---


# updateTimeZone {#updateTimeZone}

Retorna uma nova data/hora, com um novo fuso horário no mesmo instante.

## Categoria

Data 

## Sintaxe da função

`updateTimeZone(<parameters>)`

## Parâmetros

* id de fuso horário: string
* dateTime

## Assinatura e tipo retornado

`updateTimeZone(<dateTime>,<timeZone id>)`

Retorna um datetime.

## Exemplo

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Retorna 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
