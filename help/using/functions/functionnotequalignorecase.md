---
product: adobe campaign
title: notEqualIgnoreCase
description: Saiba mais sobre a função notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Verifique se a primeira string do argumento com a segunda string do argumento é diferente, ignorando as considerações sobre maiúsculas e minúsculas.

## Categoria

String

## Sintaxe da função

`notEqualIgnoreCase(<parameters>)`

## Parâmetros

* sequência de caracteres

## Assinatura e tipo retornado

`notEqualIgnoreCase(<string>,<string>)`

Retorna um valor booleano.

## Exemplo

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
