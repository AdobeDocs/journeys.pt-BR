---
product: adobe campaign
title: campos de execução de ação de eventos journeyStep
description: campos de execução de ação de eventos journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 5%

---

# campos de execução de ação de eventos journeyStep {#sharing-execution-fields}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Este mixin será compartilhado por journeyStepEvent e journeyStepProfileEvent.

Se a etapa tiver uma ação a ser processada, esses campos serão adicionados à carga do evento.

## actionID

ID da ação que está sendo executada.

Tipo: sequência de caracteres

## actionName

Nome da ação. Se nenhum nome tiver sido definido, stepName será usado.

Tipo: sequência de caracteres

## actionType

Tipo de ação.

Tipo: sequência de caracteres

## actionParameterized

Indica se a ação tem ou não parâmetros.

Tipo: booleano

## actionExecutionTime

O tempo (em milissegundos) necessário para executar uma ação atual.

Tipo: longo

## actionExecutionError

Tipo de erro que ocorre quando a ação é chamada.

Tipo: sequência de caracteres

Valores:
* http
* limite
* timeout
* erro

## actionExecutionErrorCode

Código do erro de execução da ação. Presente se o erro tiver um código, como um HTTP.

Tipo: sequência de caracteres

## actionExecutionOriginError

Um tempo limite pode ocorrer, em dois casos:

* na primeira tentativa, uma ação é executada. Nesse caso, a execução não é concluída, portanto, não há erro subjacente
* em uma tentativa: nesse caso, actionExecOrigError/actionExecOrigErrorCode descreve o erro encontrado na tentativa antes da tentativa.

Por exemplo, um email está sendo enviado e um erro HTTP 500 é retornado na primeira tentativa. A busca é repetida, mas a duração das 2 tentativas excede o tempo limite. Em seguida, a execução da ação é marcada como tempo limite. A parte da ação será semelhante a:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Tipo: sequência de caracteres

## actionExecutionOriginCode

Código de erro do actionExecOrigError.

Tipo: sequência de caracteres

## actionBusinessType

Indica o tipo de ação.

Valores:

* interno
* Email do ACS
* SMS DO ACS
* ACS Push
* cliente
* Épsilon
* ...

Tipo: sequência de caracteres

## deliveryJobID

Isso descreve a ID da tarefa de entrega para a Jornada em lote.

Tipo: sequência de caracteres

## batchDeliveryID

Isso descreve a Id de delivery da Jornada em lote.

Tipo: sequência de caracteres

## fromSegmentTrigger

Descreve se a Jornada em lote é acionada a partir do segmento do público-alvo.

Tipo: booleano

## actionSchedulerCount

Contagem de solicitações de notificação do agendador enviadas ao serviço do agendador durante o processamento da etapa.

Tipo: longo
