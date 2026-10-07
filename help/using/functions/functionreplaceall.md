---
product: adobe campaign
title: replaceAll
description: Saiba mais sobre a função replaceAll
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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
| target | string (RegExp) |
| substituição | sequência de caracteres |

## Assinatura e tipo retornado

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Retorna uma string.

## Exemplo{#example}

`replaceAll("Hello World", "l", "x")`

Retorna &quot;Hexxo Worxd&quot;.

Como o parâmetro de destino é um RegExp, dependendo da cadeia de caracteres que você deseja substituir, talvez seja necessário usar escape em alguns caracteres. Consulte o exemplo em [esta página](../functions/functionreplace.md#example_2).
