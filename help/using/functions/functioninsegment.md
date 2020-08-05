---
title: inSegment
description: Saiba mais sobre a função noSegment
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
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

A função retornará **[!UICONTROL true]** se o indivíduo dentro da instância da jornada fizer parte do segmento Adobe Experience Platform chamado &quot;homens acima de 50&quot;, caso contrário, **[!UICONTROL false]** .
