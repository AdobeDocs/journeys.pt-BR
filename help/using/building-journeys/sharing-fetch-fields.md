---
product: adobe campaign
solution: Journey Orchestration
title: campos de busca de dados de eventos journeyStep
description: campos de busca de dados de eventos journeyStep
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---


# campos de busca de dados de eventos journeyStep {#sharing-fetch-fields}

Esse mixin será compartilhado por meio de jornadaStepEvent e de jornadaStepProfileEvent.

Durante o processamento de uma etapa, podemos ter N busca de dados em grupos de campos.

## fetchTotalTime

Tempo total gasto na busca de dados em milis durante o processamento da etapa.

Tipo: long

## fetchTypeInError

Define se a busca por erro está no Adobe Experience Platform ou em uma fonte de dados personalizada.

Tipo: string

Valores:
* áep
* custom

## fetchError

Tipo de erro que ocorre quando a busca de dados é processada.

Tipo: string

Valores:
* http
* limite
* tempo
* error

## fetchErrorCode

Código para erro de busca. Apresente se o erro tiver um código, como um HTTP. Por exemplo, se actionExecError for http, o código 404 representará o erro HTTP 404.

Tipo: string

## fetchOriginError

Pode ocorrer um tempo limite, em dois casos:

* na primeira tentativa, a ação é executada. Nesse caso, a execução não está concluída, portanto, não há erro subjacente
* em uma nova tentativa: nesse caso, actionExecOrigError/actionExecOrigErrorCode descreve o erro encontrado na tentativa antes da nova tentativa.

Por exemplo, os dados estão sendo buscados do Serviço de Perfil Unificado e um erro HTTP 500 é retornado na primeira tentativa. A busca é repetida, mas a duração das 2 tentativas excede o tempo limite. Em seguida, a execução da ação é marcada como tempo limite. A parte de ação terá a seguinte aparência:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: string

## fetchOriginErrorCode

O código de erro fornecido pelo sistema [!DNL Journey Orchestration] está sendo consultado. Por exemplo, pode ser 404, 500 etc.

Tipo: string

## fetchCount

Quantas vezes os dados são buscados, independentemente do tipo de fonte.

Tipo: long

## fetchPlatformTotalTime

O tempo total necessário para obter os dados do Adobe Experience Platform em millis. Observação: esse tempo é calculado a partir do momento em que o mecanismo envia o evento do enriquecimento para o serviço do enriquecimento e recebe a resposta.

Tipo: long

## fetchPlatformCount

Quantas vezes os dados são obtidos da Adobe Experience Platform.

Tipo: long

## fetchCustomTotalTime

Quantidade de tempo para buscar os dados personalizados em millis. Observação: esse tempo é calculado a partir do momento em que o mecanismo envia o evento do enriquecimento para o serviço do enriquecimento e recebe a resposta

Tipo: long

## fetchCustomCount

Quantas vezes os dados personalizados são obtidos de sistemas externos.

Tipo: long
