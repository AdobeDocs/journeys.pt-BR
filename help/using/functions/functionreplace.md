---
product: adobe campaign
title: replace
description: Saiba mais sobre a substituição de função
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 10%

---

# replace {#replace}

Substitui a primeira ocorrência que corresponde à string de destino pela string de substituição na string base.

A substituição prossegue do início da string para o final, por exemplo, a substituição de &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

## Categoria

String

## Sintaxe da função

`replace(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|--------------|
| base | string |
| target | string (RegExp) |
| substituição | string |

## Assinatura e tipo retornado

`replace(<base>,<target>,<replacement>)`

Retorne uma string.

## Exemplo 1

`replace("Hello World", "l", "x")`

Retorna &quot;Mundo Hexlo&quot;.

## Exemplo 2 {#example_2}

Como o parâmetro de destino é RegExp, dependendo da string que você deseja substituir, talvez seja necessário evitar alguns caracteres. Exemplo:

* string a ser avaliada: `|OFFER_A|OFFER_B`
* fornecido por um atributo de perfil `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Sequência de caracteres a ser substituída: `|OFFER_A`
* Sequência de caracteres substituída por: `''`
* Você precisa adicionar `\\` antes da `|` caractere.

A expressão é:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

A string retornada é: `|OFFER_B`

Você também pode criar a cadeia de caracteres a ser substituída de um determinado atributo:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
