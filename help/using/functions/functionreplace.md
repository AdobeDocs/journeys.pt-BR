---
product: adobe campaign
title: replace
description: Saiba mais sobre a substituição de função
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 12%

---

# replace {#replace}

Substitui a primeira ocorrência correspondente à string de destino pela string de substituição na string de base.

A substituição continua do início da string até o fim. Por exemplo, substituir &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

## Categoria

String

## Sintaxe da função

`replace(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|--------------|
| base | sequência de caracteres |
| destino | string (RegExp) |
| substituição | sequência de caracteres |

## Assinatura e tipo retornado

`replace(<base>,<target>,<replacement>)`

Retorna uma string.

## Exemplo 1

`replace("Hello World", "l", "x")`

Retorna &quot;Hexlo World&quot;.

## Exemplo 2 {#example_2}

Como o parâmetro de destino é um RegExp, dependendo da cadeia de caracteres que você deseja substituir, talvez seja necessário usar escape em alguns caracteres. Exemplo:

* cadeia de caracteres a ser avaliada: `|OFFER_A|OFFER_B`
* fornecido por um atributo de perfil `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Cadeia de caracteres a ser substituída: `|OFFER_A`
* Cadeia de caracteres substituída por: `''`
* É necessário adicionar `\\` antes do caractere `|`.

A expressão é:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

A cadeia de caracteres retornada é: `|OFFER_B`

Também é possível criar a cadeia de caracteres a ser substituída a partir de um determinado atributo:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
