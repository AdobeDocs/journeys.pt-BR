---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Saiba mais sobre a função noSegment
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---


# inSegment {#inSegment}

Verifica se um indivíduo pertence a um determinado segmento.

>[!NOTE]
>
>Você pode recuperar até 100 segmentos.

O nome do segmento deve ser uma constante de string. Não pode ser uma referência de campo nem uma expressão.

Os segmentos são definidos no [Adobe Experience Platform](https://platform.adobe.com/segment/overview). O editor de expressão fornece uma lista de segmentos preenchida automaticamente.

>[!NOTE]
>
>Somente os indivíduos com os status de participação do segmento **Realizado** e **Existente** serão considerados membros do segmento. Para obter mais informações sobre como avaliar um segmento, consulte a [documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

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

A função retornará **[!UICONTROL true]** se o indivíduo na instância do jornada fizer parte do segmento do Adobe Experience Platform chamado &quot;homens acima de 50&quot;, caso contrário, **[!UICONTROL false]**.
