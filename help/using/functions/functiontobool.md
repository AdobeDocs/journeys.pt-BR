---
title: toBool
description: Saiba mais sobre a função toBool
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# toBool {#toBool}

Converte um valor de argumento em um valor booliano, dependendo de seu tipo.

* Da string: tente converter o valor da string como booleano, de &quot;true&quot; se o valor da string for &quot;true&quot;; caso contrário, false
* De numérico: true se o valor numérico não for igual a 0, caso contrário, false

## Categoria

Conversão

## Sintaxe da função

`toBool(<parameter>)`

## Parâmetros

* decimal
* booleano
* string
* integer

## Assinaturas e tipos retornados

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Retorne um booleano.

## Exemplos

`toBool("true")`

`toBool(1)`

Retorna true.

`toBool("this is not a boolean")`

Retorna false.
