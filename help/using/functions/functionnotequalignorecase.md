---
title: notEqualWithIgnoreCase
description: Saiba mais sobre a função notEqualWithIgnoreCase
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Verifique se a primeira string de argumento com a segunda string de argumento é diferente, ignorando considerações de maiúsculas e minúsculas.

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
