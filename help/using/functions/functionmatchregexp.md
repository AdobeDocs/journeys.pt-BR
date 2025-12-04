---
product: adobe campaign
title: matchRegExp
description: Saiba mais sobre a função matchRegExp
feature: Journeys
role: Developer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# matchRegExp {#matchRegExp}

Retornará true se a cadeia de caracteres no primeiro parâmetro corresponder à expressão regular no segundo parâmetro. Para obter mais informações, consulte [esta página](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

String

## Sintaxe da função

`matchRegExp(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| sequência de caracteres | sequência de caracteres |
| regexp | sequência de caracteres |

## Assinatura e tipo retornado

`matchRegExp(<string>,<string>)`

Retorna um valor booleano.

## Exemplo

`matchRegExp("username@adobe.com", "*adobe")`

Retorna verdadeiro.
