---
product: adobe campaign
solution: Journey Orchestration
title: Funções
description: Saiba mais sobre funções
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 71%

---


# Funções {#concept_p1r_qj5_dgb}

Uma função pode ter assinaturas diferentes (um conjunto diferente de parâmetros ordenados). Uma assinatura de função pode ter expressões 0-N como parâmetros ordenados.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Cada função tem um tipo específico retornado.

Esta é a lista de funções suportadas.

## Funções principais

| Categoria | Função |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Agregação | [avg](../functions/functionavg.md) |
| Agregação | [count](../functions/functioncount.md) |
| Agregação | [countOnlyNull](../functions/functioncountonlynull.md) |
| Agregação | [countWithNull](../functions/functioncountwithnull.md) |
| Agregação | [distinctCount](../functions/functiondistinctcount.md) |
| Agregação | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Agregação | [max](../functions/functionmax.md) |
| Agregação | [min](../functions/functionmin.md) |
| Agregação | [sum](../functions/functionsum.md) |
| Conversão | [toBool](../functions/functiontobool.md) |
| Conversão | [toDateTime](../functions/functiontodatetime.md) |
| Conversão | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Conversão | [toDecimal](../functions/functiontodecimal.md) |
| Conversão | [toDuration](../functions/functiontoduration.md) |
| Conversão | [toInteger](../functions/functiontointeger.md) |
| Conversão | [toString](../functions/functiontostring.md) |
| Data | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Data | [inLastDays](../functions/functioninlastdays.md) |
| Data | [inLastHours](../functions/functioninlasthours.md) |
| Data | [inLastMonths](../functions/functioninlastmonths.md) |
| Data | [inLastYears](../functions/functioninlastyears.md) |
| Data | [inNextDays](../functions/functioninnextdays.md) |
| Data | [inNextHours](../functions/functioninnexthours.md) |
| Data | [inNextMonths](../functions/functioninnextmonths.md) |
| Data | [inNextYears](../functions/functioninnextyears.md) |
| Data | [now](../functions/functionnow.md) |
| Data | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Data | [setHours](../functions/functionsethours.md) |
| Data | [setDays](../functions/functionsetdays.md) |
| Lista | [distinct](../functions/functiondistinct.md) |
| Lista | [distinctCount](../functions/functiondistinctcount.md) |
| Lista | [in](../functions/functionin.md) |
| Lista | [listSize](../functions/functionlistsize.md) |
| Lista | [serializeList](../functions/functionserializelist.md) |
| Lista | [sort](../functions/functionsort.md) |
| Matemática | [random](../functions/functionrandom.md) |
| Matemática | [round](../functions/functionround.md) |
| String | [concat](../functions/functionconcat.md) |
| String | [contain](../functions/functioncontain.md) |
| String | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| String | [endWith](../functions/functionendwith.md) |
| String | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| String | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| String | [indexOf](../functions/functionindexof.md) |
| String | [isEmpty](../functions/functionisempty.md) |
| String | [isNotEmpty](../functions/functionisnotempty.md) |
| String | [lastIndexOf](../functions/functionlastindexof.md) |
| String | [length](../functions/functionlength.md) |
| String | [lower](../functions/functionlower.md) |
| String | [matchRegExp](../functions/functionmatchregexp.md) |
| String | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| String | [replace](../functions/functionreplace.md) |
| String | [replaceAll](../functions/functionreplaceall.md) |
| String | [startWith](../functions/functionstartwith.md) |
| String | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| String | [substr](../functions/functionsubstr.md) |
| String | [trim](../functions/functiontrim.md) |
| String | [upper](../functions/functionupper.md) |
| String | [uuid](../functions/functionuuid.md) |