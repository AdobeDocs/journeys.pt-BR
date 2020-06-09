---
title: eventos de jorneystep campos comuns
description: eventos de jorneystep campos comuns
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# eventos de jorneystep campos comuns {#sharing-common-fields}

Esse mixin será compartilhado por meio de jornadaStepEvent e de jornadaStepProfileEvent.

Esses são os campos XDM comuns que [!DNL Journey Orchestration] enviam para a Adobe Data Platform. Campos comuns serão enviados para cada etapa que for processada em uma jornada. Campos mais específicos são usados para ações e enriquecimentos personalizados.

Alguns desses campos estão disponíveis apenas em padrões de processamento específicos (execução de ação, busca de dados etc.) para limitar o tamanho dos eventos.

## entrada

Indica se o usuário entrou na jornada. Se não estiver presente, presumimos que o valor é falso.

Tipo: booleano

Valores: true/false

## reentrada

Indica se o usuário entrou novamente na jornada com a mesma instância. Se não estiver presente, presumimos que o valor é falso.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica se a instância terminou (com êxito ou não).

Tipo: booleano

## eventID

ID do Evento no processamento, para o processamento da etapa. Se o evento for externo, o valor será eventId. Se o evento for interno, o valor será eventId interno (como por exemplo, SchedulNotificationReceived, executeAction etc.).

Tipo: string

## nodeID

ID do nó cliente (da tela).

Tipo: string

## stepID

Id exclusiva da etapa que está sendo processada no momento.

Tipo: string

## stepName

Nome da etapa que está sendo processada no momento.

Tipo: string

## stepType

Tipo da etapa.

Tipo: string

Valores possíveis:

* Condição
* Ação
* Agendador
* Temporizador

## stepStatus

O status da etapa, que representa o status da etapa, quando seu processamento foi concluído (e o evento da etapa acionado).

Tipo: string

O status pode ser:

* encerrada: a etapa não tem transição e seu processamento foi concluído com êxito.
* erro: o processamento da etapa gerou um erro.
* transições: a etapa está aguardando que um evento seja transição para outra etapa.
* limitado: a etapa falhou em um erro de limitação, gerado durante uma ação ou enriquecimento.
* tempo limite: a etapa falhou em um erro de tempo limite, gerado durante uma ação ou enriquecimento.
* instanceTimedout: a etapa parou o processamento, pois a instância atingiu o tempo limite.

## IDdajornada

ID da viagem.

Tipo: string

## IDdaVersãoDoCaminho

ID da versão da jornada. Esta id representa a referência de identidade para a jornada, no caso de jornadaStepEvent.

Tipo: string

## JourVersionName

Nome da versão da jornada.

Tipo: string

## JourVersion

Versão da jornada.

Tipo: string

## instanceID

ID interna da instância da jornada.

Tipo: string

## externalKey

Chave externa extraída do evento para processá-la.

Tipo: string

## parentStepID

ID da etapa do pai da etapa processada atual na instância.

Tipo: string

## parentStepName

Nome da etapa do pai da etapa atual.

Tipo: string

## parentTransitionID

Id da transição que trouxe a instância para a etapa processada.

Tipo: string

## parentTransitionName

Nome da transição que trouxe a instância para a etapa processada.

Tipo: string

## inTest

Indicado se esta viagem está ou não no modo de ensaio.

Tipo: booleano

## processingTime

Tempo total em milissegundos desde a entrada da etapa da instância até o final do processamento.

Tipo: long

## instanceType

Indica o tipo de instância, se for lote ou unitário.

Tipo: string

Valores: lote/unidade

## frequencyIndex

Índice de recorrência se a jornada for em lote e recorrente (a primeira execução tem recorrênciaIndex = 1).

Tipo: long

## isBatchToUnitário

Indica se esta instância unitária foi acionada a partir de uma instância em lote.

Tipo: booleano

## batchExternalKey

Chave externa do evento batch.

Tipo: string

## batchInstanceID

essa é a ID da instância do lote.

Tipo: string

## batchUnitárioBranchID

se a instância tiver sido acionada a partir de uma instância em lote, uma ID de ramificação unitária.

Tipo: string
