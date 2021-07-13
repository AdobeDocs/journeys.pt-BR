---
product: adobe campaign
title: campos de execução de ação de eventos journeyStep
description: campos de execução de ação de eventos journeyStep
feature: Jornadas
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 13%

---

# campos de execução de ação de eventos journeyStep {#sharing-execution-fields}

Esse mixin será compartilhado por journeyStepEvent e journeyStepProfileEvent.

Se a etapa tiver uma ação a ser processada, esses campos serão adicionados ao payload do evento.

## actionID

ID da ação que está sendo executada.

Tipo: sequência de caracteres

## actionName

Nome da ação. Se nenhum nome tiver sido definido, o stepName será executado.

Tipo: sequência de caracteres

## actionType

Tipo da ação.

Tipo: sequência de caracteres

## actionParameterized

Indica se a ação está parametrizada ou não.

Tipo: booleano

## actionExecutionTime

O tempo (em milissegundos) necessário para executar uma ação atual.

Tipo: long

## actionExecutionError

Tipo de erro que ocorre quando a ação é chamada.

Tipo: sequência de caracteres

Valores:
* http
* limite
* timeout
* error

## actionExecutionErrorCode

Código para erro de execução de ação. Apresentar se o erro tiver um código, como um HTTP.

Tipo: sequência de caracteres

## actionExecutionOriginError

Um tempo limite pode ocorrer, em dois casos:

* na primeira tentativa, uma ação é executada. Nesse caso, a execução não está concluída, portanto, não há erro subjacente
* em uma nova tentativa: nesse caso, o actionExecOrigError/actionExecOrigErrorCode descreve o erro encontrado na tentativa antes da nova tentativa.

Por exemplo, um email está sendo enviado e um erro HTTP 500 é retornado na primeira tentativa. A busca é repetida, mas a duração das 2 tentativas excede o tempo limite. Em seguida, a execução da ação é marcada como tempo limite. A parte de ação terá a seguinte aparência:

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

Código de erro de actionExecOrigError.

Tipo: sequência de caracteres

## actionBusinessType

Indica o tipo de ação.

Valores:

* construção
* Email ACS
* SMS ACS
* Envio ACS
* cliente
* Epsilon
* ...

Tipo: sequência de caracteres

## deliveryJobID

Este artigo descreve a ID de trabalho de delivery para a Jornada em lote.

Tipo: sequência de caracteres

## batchDeliveryID

Este artigo descreve a ID de delivery da Jornada em lote.

Tipo: sequência de caracteres

## fromSegmentTrigger

Isso descreve se a Jornada em lote é acionada pelo Segmento do público-alvo.

Tipo: booleano

## actionSchedulerCount

Contagem de solicitações de notificação do programador enviadas ao serviço do programador durante o processamento da etapa.

Tipo: long
