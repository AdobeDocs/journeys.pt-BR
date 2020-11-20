---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: Saiba mais sobre a função serializeList
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 16%

---


# serializeList {#serializeList}

Converte a lista (qualquer tipo) fornecida no primeiro parâmetro em uma string. O segundo parâmetro representa o separador a ser usado. O terceiro parâmetro é um valor booliano que indica se cada elemento da expressão deve incluir aspas.

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

Retorna uma string.

## Exemplo

`serializeList(["Hello","World"], " ", false)`

Retorna &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Retorna &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
