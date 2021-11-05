---
product: adobe campaign
title: containIgnoreCase
description: Saiba mais sobre a função containIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# containIgnoreCase {#containIgnoreCase}

Verifica se a segunda string de argumento está contida na primeira string de argumento, sem considerar o caso.

## Categoria

String

## Sintaxe da função

`containIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| string pesquisada | string |

## Assinatura e tipo retornado

`containIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`containIgnoreCase("rowing is great", "GREAT")`

Retorna true.
