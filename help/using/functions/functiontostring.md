---
title: toString
description: Saiba mais sobre a função toString
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
source-wordcount: '112'
ht-degree: 4%

---


# toString {#toString}

Converte um valor de argumento em um valor de string, dependendo de seu tipo. For more information on data types, refer to [](../expression/data-types.md).

## Categoria

Conversão

## Sintaxe da função

`toString(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| dateTime | converte a data em formato de data UTC |
| dateTimeOnly | converte a data em formato de data UTC |
| duração | converter no número correspondente de milissegundos como uma string |
| fuso horário | converter na representação da cadeia de caracteres de ID de fuso horário (ID do JODA) |
| integer | converte para representação de string do valor (1 se torna &quot;1&quot;) |
| decimal | converte para representação de string do valor (1,5 se torna &quot;1,5&quot;) |
| booleano | converter o valor booliano como &#39;true&#39; se for verdadeiro, &#39;false&#39; se for falso |

## Assinaturas e tipo retornado

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Retorna uma string.

## Exemplo

`toString(4)`

Retorna &quot;4&quot;.
