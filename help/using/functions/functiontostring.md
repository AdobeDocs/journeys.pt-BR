---
product: adobe campaign
title: toString
description: Saiba mais sobre a função toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 9%
---
# toString {#toString}

Converte um valor de argumento em um valor de string, dependendo de seu tipo. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

## Categoria

Conversão

## Sintaxe da função

`toString(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| dateTime | converte a data no formato de data UTC |
| dateTimeOnly | converte a data no formato de data UTC |
| duração | converta para o número correspondente de milissegundos como uma string |
| inteiro | converte para representação em string do valor (1 torna-se &quot;1&quot;) |
| decimal | converte para representação em string do valor (1,5 torna-se &quot;1,5&quot;) |
| booleano | converta o valor booleano como &#39;true&#39; se verdadeiro, &#39;false&#39; se falso |

## Assinaturas e tipo retornado

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Retorna uma string.

## Exemplo

`toString(4)`

Retorna &quot;4&quot;.
