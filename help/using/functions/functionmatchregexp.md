---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Saiba mais sobre a função matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 5%

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

Aqui, você verifica se a sequência de caracteres satisfaz a expressão normal (sintaxe java): start com &quot;Hello&quot;, qualquer tipo de corda e termina com &quot;World&quot;.
