---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Saiba mais sobre a função notEqualWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Verifique se a primeira string de argumento com a segunda string de argumento é diferente, ignorando considerações de caso.

## Categoria

String

## Sintaxe da função

`notEqualWithIgnoreCase(<parameters>)`

## Parâmetros

* string

## Assinatura e tipo retornado

`notEqualWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
