---
product: adobe campaign
title: replace
description: Saiba mais sobre a substituição de função
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
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
| target | string (RegExp) |
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
