---
product: adobe campaign
title: campos de busca de dados de eventos journeyStep
description: campos de busca de dados de eventos journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 7%

---

# campos de busca de dados de eventos journeyStep {#sharing-fetch-fields}

Este mixin será compartilhado por journeyStepEvent e journeyStepProfileEvent.

Durante um processamento de etapa, podemos ter N busca de dados em grupos de campos.

## fetchTotalTime

Tempo total gasto na busca de dados em milissegundos durante o processamento da etapa.

Tipo: longo

## fetchTypeInError

Define se a busca com erro está no Adobe Experience Platform ou em uma fonte de dados personalizada.

Tipo: sequência de caracteres

Valores:
* aep
* personalizado

## fetchError

Tipo de erro que ocorre quando a busca de dados é processada.

Tipo: sequência de caracteres

Valores:
* http
* limite
* tempo limite
* error

## fetchErrorCode

Código do erro de busca. Presente se o erro tiver um código, como um HTTP. Por exemplo, se actionExecError for http, o código 404 representará o erro HTTP 404.

Tipo: sequência de caracteres

## fetchOriginError

Um tempo limite pode ocorrer, em dois casos:

* na primeira tentativa, a ação é executada. Nesse caso, a execução não é concluída, portanto, não há erro subjacente
* em uma tentativa: nesse caso, actionExecOrigError/actionExecOrigErrorCode descreve o erro encontrado na tentativa antes da tentativa.

Por exemplo, os dados estão sendo obtidos do Unified Profile Service e um erro HTTP 500 é retornado na primeira tentativa. A busca é repetida, mas a duração das 2 tentativas excede o tempo limite. Em seguida, a execução da ação é marcada como tempo limite. A parte da ação será semelhante a:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: sequência de caracteres

## fetchOriginErrorCode

O código de erro fornecido pelo sistema [!DNL Journey Orchestration] O está consultando. Por exemplo, pode ser um 404, 500, etc.

Tipo: sequência de caracteres

## fetchCount

Quantas vezes os dados são obtidos, independentemente do tipo de fonte.

Tipo: longo

## fetchPlatformTotalTime

A quantidade total de tempo gasto para buscar os dados do Adobe Experience Platform em milhões. Observação: este período é calculado a partir do momento em que o mecanismo envia o evento de enriquecimento ao serviço de enriquecimento e recebe a resposta.

Tipo: longo

## fetchPlatformCount

Quantas vezes os dados são obtidos do Adobe Experience Platform.

Tipo: longo

## fetchCustomTotalTime

Tempo para buscar os dados personalizados em milissegundos. Observação: este período é calculado a partir do momento em que o mecanismo envia o evento de enriquecimento ao serviço de enriquecimento e recebe a resposta

Tipo: longo

## fetchCustomCount

Quantas vezes os dados personalizados são obtidos de sistemas externos.

Tipo: longo
