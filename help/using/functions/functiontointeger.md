---
product: adobe campaign
title: toInteger
description: Saiba mais sobre a função toInteger
feature: Journeys
role: Developer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
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
source-wordcount: '75'
ht-degree: 13%
---
# toInteger {#toInteger}

Converte um valor de argumento em um inteiro.

## Categoria

Conversão

## Sintaxe da função

`toInteger(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| sequência de caracteres | converte o valor da string em um inteiro |
| dateTime | converte a data no número de milissegundos (milissegundos da época) |
| decimal | converte em um inteiro removendo a parte decimal (exemplo: 1,5 torna-se 1) |
| booleano | converte o valor booleano como 1 se verdadeiro, 0 se falso |

## Assinaturas e tipo retornado

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Retorna um número inteiro.

## Exemplos

`toInteger("4")`

Retorna 4.
