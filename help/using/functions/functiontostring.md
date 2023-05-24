---
product: adobe campaign
title: toString
description: Saiba mais sobre a função toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '102'
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
