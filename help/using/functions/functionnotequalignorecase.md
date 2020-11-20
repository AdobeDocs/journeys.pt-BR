---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Saiba mais sobre a função notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
