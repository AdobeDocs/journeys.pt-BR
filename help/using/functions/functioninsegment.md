---
product: adobe campaign
title: inSegment
description: Saiba mais sobre a função no segmento
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 6%

---

# inSegment {#inSegment}

Verifica se um indivíduo pertence a um determinado segmento.

>[!NOTE]
>
>Você pode recuperar até 100 segmentos.

O nome do segmento deve ser uma constante de sequência. Não pode ser uma referência de campo nem uma expressão.

Segmentos são definidos na [Adobe Experience Platform](https://platform.adobe.com/segment/overview). O editor de expressão fornece uma lista de segmentos preenchida automaticamente.

Os segmentos podem ter três status:

* existente: a entidade continua a estar no segmento.
* realizado: a entidade está informando o segmento.
* encerrado: a entidade está saindo do segmento.

Apenas indivíduos com os status de participação de segmento **Realizado** e **Existente** serão considerados membros do segmento. Para obter mais informações sobre como avaliar um segmento, consulte a [documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=pt-BR#interpret-segment-results).

`IF inSegment('segmentName') == true` significa que você tem um segmentMembership com o status inserido/existente.

`ELSE inSegment('segmentName') == false` significa que você tem um segmentMembership com status encerrado.

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

Retorna um valor booleano.

## Exemplo

`inSegment("men over 50")`

Explicação:

A função retornará **[!UICONTROL true]** se o indivíduo na instância do jornada fizer parte do segmento do Adobe Experience Platform chamado &quot;homens acima de 50&quot;, caso contrário **[!UICONTROL false]**.
