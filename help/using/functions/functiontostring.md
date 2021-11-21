---
product: adobe campaign
title: toString
description: Saiba mais sobre a função toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

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
| dateTime | converte a data em formato de data UTC |
| dateTimeOnly | converte a data em formato de data UTC |
| duration | converter no número correspondente de milissegundos como uma string |
| fuso horário | converter em representação da cadeia de caracteres de id do fuso horário (ID do JODA) |
| integer | converte em representação de string do valor (1 se torna &quot;1&quot;) |
| decimal | converte em representação de string do valor (1,5 se torna &quot;1,5&quot;) |
| booleano | converter o valor booleano como &#39;true&#39; se for verdadeiro, &#39;false&#39; se for falso |

## Assinaturas e tipo retornado

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Retorne uma string.

## Exemplo

`toString(4)`

Retorna &quot;4&quot;.
