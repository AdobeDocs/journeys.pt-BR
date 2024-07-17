---
product: adobe campaign
title: replaceAll
description: Saiba mais sobre a função replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 10%

---

# replaceAll {#replaceAll}

Substitui todas as ocorrências correspondentes à cadeia de caracteres de destino pela cadeia de caracteres de substituição na cadeia de caracteres base.

A substituição continua do início da string até o fim. Por exemplo, substituir &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

## Categoria

String

## Sintaxe da função

`replaceAll(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|--------------|
| base | sequência de caracteres |
| público-alvo | string (RegExp) |
| substituição | sequência de caracteres |

## Assinatura e tipo retornado

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Retorna uma string.

## Exemplo{#example}

`replaceAll("Hello World", "l", "x")`

Retorna &quot;Hexxo Worxd&quot;.

Como o parâmetro de destino é um RegExp, dependendo da cadeia de caracteres que você deseja substituir, talvez seja necessário usar escape em alguns caracteres. Consulte o exemplo em [esta página](../functions/functionreplace.md#example_2).
