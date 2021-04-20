---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Saiba mais sobre a função matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 6%

---


# matchRegExp {#matchRegExp}

Retorna true se a string no primeiro parâmetro corresponder à expressão regular no segundo parâmetro. Para obter mais informações, consulte [esta página](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

String

## Sintaxe da função

`matchRegExp(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| string | string |
| regexp | string |

## Assinatura e tipo retornado

`matchRegExp(<string>,<string>)`

Retorna um verdadeiro.

## Exemplo

`matchRegExp("Hello World", "Hello\s+World")`

Retorna true.

Explicação:

Aqui, você verifica se a string satisfaz a expressão regular (sintaxe java): começa com &quot;Hello&quot;, depois qualquer tipo de string e termina com &quot;World&quot;.
