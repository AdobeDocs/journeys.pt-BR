---
product: adobe campaign
title: toDateOnly
description: Saiba mais sobre a função toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

Converte um valor de argumento em um valor somente de data.

## Categoria

Conversão

## Sintaxe da função

`toDateOnly(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data no formato ISO-8601 ou &quot;AAAA-MM-DD&quot; (formato Data XDM) | string |
| data | data |

## Assinaturas e tipos retornados

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`toDateOnly("2016-08-18")`

retorna um objeto dateOnly representando 2016-08-18.
