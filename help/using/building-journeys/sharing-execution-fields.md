---
title: campos de execução de ação de eventos journeyStep
description: campos de execução de ação de eventos journeyStep
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---


# campos de execução de ação de eventos journeyStep {#sharing-execution-fields}

Esse mixin será compartilhado por meio de jornadaStepEvent e de jornadaStepProfileEvent.

Se a etapa tiver uma ação a ser processada, esses campos serão adicionados à carga do evento.

## actionID

ID da ação que está sendo executada.

Tipo: string

## actionName

Nome da ação. Se nenhum nome tiver sido definido, StepName será executado.

Tipo: string

## actionType

Tipo da ação.

Tipo: string

## actionParameterized

Indica se a ação foi parametrizada ou não.

Tipo: booleano

## actionExecutionTime

O tempo (em milissegundos) necessário para executar uma ação atual.

Tipo: long

## actionExecutionError

Tipo de erro que ocorre quando a ação é chamada.

Tipo: string

Valores:
* http
* limite
* timeout
* error

## actionExecutionErrorCode

Código para erro de execução de ação. Apresente se o erro tiver um código, como um HTTP.

Tipo: string

## actionExecutionOriginError

Pode ocorrer um tempo limite, em dois casos:

* na primeira tentativa, uma ação é executada. Nesse caso, a execução não está concluída, portanto, não há erro subjacente
* em uma nova tentativa: nesse caso, actionExecOrigError/actionExecOrigErrorCode descreve o erro encontrado na tentativa antes da nova tentativa.

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

Tipo: string

## actionExecutionOriginCode

Código de erro de actionExecOrigError.

Tipo: string

## actionBusinessType

Indica o tipo de ação.

Valores:

* edifício
* Email ACS
* SMS ACS
* Empurramento ACS
* cliente
* Epsilon
* ...

Tipo: string

## deliveryJobID

Esta descreve a ID de trabalho do delivery para o lote Jornada.

Tipo: string

## batchDeliveryID

Esta descreve a ID do delivery para o lote Jornada.

Tipo: string

## fromSegmentTrigger

Isso descreve se a jornada em lote é acionada a partir do segmento de Audiência.

Tipo: booleano

## actionSchedulerCount

Contagem de solicitações de notificação de scheduler enviadas ao serviço de scheduler durante o processamento da etapa.

Tipo: long
