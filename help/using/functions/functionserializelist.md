---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: Saiba mais sobre a função serializeList
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 16%

---


# serializeList {#serializeList}

Converte a lista (qualquer tipo) fornecida no primeiro parâmetro em uma string. O segundo parâmetro representa o separador a ser usado. O terceiro parâmetro é um valor booleano que indica se cada elemento da expressão deve incluir aspas.

## Categoria

Lista

## Sintaxe da função

`serializeList(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| String | String |
| Booleano | Booleano |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listPoint |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Assinatura e tipo retornado

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Retorne uma string.

## Exemplo

`serializeList(["Hello","World"], " ", false)`

Retorna &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Retorna &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
