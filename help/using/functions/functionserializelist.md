---
title: serializeList
description: Saiba mais sobre a função serializeList
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
| Cadeia de caracteres | Cadeia de caracteres |
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
