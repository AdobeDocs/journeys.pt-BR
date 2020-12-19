---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Saiba mais sobre a função noSegment
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 7%

---


# inSegment {#inSegment}

Verifica se um indivíduo pertence a um determinado segmento.

O nome do segmento deve ser uma constante de string. Não pode ser uma referência de campo nem uma expressão.

Os segmentos são definidos no [Adobe Experience Platform](https://platform.adobe.com/segment/overview). O editor de expressões fornece uma lista de segmentos preenchida automaticamente.

>[!NOTE]
>
>Você pode recuperar até 100 segmentos.

## Categoria

Adobe Experience Platform

## Sintaxe da função

`inSegment(<parameter>)`

## Parâmetros

| Parâmetro | Descrição | Tipo |
|--- |--- |--- |
| Segmento | O nome do segmento | `<string>` |

## Assinatura e tipo retornado

`inSegment(<string>)`

Retorna um booleano.

## Exemplo

`inSegment("men over 50")`

Explicação:

A função retornará **[!UICONTROL true]** se o indivíduo dentro da instância de jornada fizer parte do segmento Adobe Experience Platform chamado &quot;men above 50&quot;, senão **[!UICONTROL false]**.
