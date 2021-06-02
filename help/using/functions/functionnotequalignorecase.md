---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Saiba mais sobre a função notEqualWithIgnoreCase
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 15%

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
