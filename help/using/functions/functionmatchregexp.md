---
title: matchRegExp
description: Saiba mais sobre a função matchRegExp
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

Retorna true se a string no primeiro parâmetro corresponder à expressão regular no segundo parâmetro. For more information, see [this page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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
