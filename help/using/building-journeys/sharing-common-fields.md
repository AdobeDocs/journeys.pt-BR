---
product: adobe campaign
title: campos comuns de eventos journey steps
description: campos comuns de eventos journey steps
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# campos comuns de eventos journey steps {#sharing-common-fields}

Este mixin será compartilhado por journeyStepEvent e journeyStepProfileEvent.

Esses são os campos XDM comuns que [!DNL Journey Orchestration] envia para a Adobe Experience Platform. Campos comuns serão enviados para cada etapa processada em uma jornada. Campos mais específicos são usados para ações e enriquecimentos personalizados.

Alguns desses campos só estão disponíveis em padrões de processamento específicos (execução de ação, busca de dados etc.) para limitar o tamanho dos eventos.

## entrada

Indica se o usuário inseriu a jornada. Se não estiver presente, assumimos que o valor é false.

Tipo: booleano

Valores: true/false

## reentrada

Indica se o usuário inseriu novamente a jornada com a mesma instância. Se não estiver presente, assumimos que o valor é false.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica se a instância terminou (com sucesso ou não).

Tipo: booleano

## eventID

ID do evento em processamento, para o processamento da etapa. Se o evento for externo, o valor será seu eventId. Se o evento for interno, o valor será o eventId interno (como scheduledNotificationReceived, performedAction, etc.).

Tipo: sequência de caracteres

## nodeID

ID do nó do cliente (da tela).

Tipo: sequência de caracteres

## stepID

Identificador exclusivo da etapa que está sendo processada.

Tipo: sequência de caracteres

## stepName

Nome da etapa que está sendo processada.

Tipo: sequência de caracteres

## stepType

Tipo da etapa.

Tipo: sequência de caracteres

Valores possíveis:

* Condição
* Ação
* Scheduler
* Temporizador

## stepStatus

Status da etapa, representando o status da etapa, quando seu processamento foi concluído (e o evento da etapa foi acionado).

Tipo: sequência de caracteres

O status pode ser:

* encerrado: a etapa não tem transição e seu processamento foi encerrado com êxito.
* erro: o processamento da etapa gerou um erro.
* transições: a etapa está aguardando um evento passar para outra etapa.
* capped: a etapa falhou em um erro de limite, gerado durante uma ação ou enriquecimento.
* tempo limite: a etapa falhou em um erro de tempo limite, gerado durante uma ação ou enriquecimento.
* instanceTimedout: a etapa interrompeu o processamento porque a instância atingiu o tempo limite.

## journeyID

ID da jornada.

Tipo: sequência de caracteres

## journeyVersionID

ID da versão do jornada. No caso de journeyStepEvent, essa id representa a referência de identidade para a jornada.

Tipo: sequência de caracteres

## journeyVersionName

Nome da versão do jornada.

Tipo: sequência de caracteres

## journeyVersion

Versão da versão do jornada.

Tipo: sequência de caracteres

## instanceID

ID interna da instância do jornada.

Tipo: sequência de caracteres

## externalKey

Chave externa extraída do evento para processá-lo.

Tipo: sequência de caracteres

## parentStepID

ID da etapa principal da etapa processada atual na instância.

Tipo: sequência de caracteres

## parentStepName

Nome da etapa principal da etapa atual.

Tipo: sequência de caracteres

## parentTransitionID

Id da transição que trouxe a instância para a etapa processada.

Tipo: sequência de caracteres

## parentTransitionName

Nome da transição que levou a instância à etapa processada.

Tipo: sequência de caracteres

## inTest

Indicado se essa jornada está no modo de teste ou não.

Tipo: booleano

## processingTime

Tempo total em milissegundos desde a entrada da etapa da instância até o final do processamento.

Tipo: longo

## instanceType

Indica o tipo de instância, se for batch ou unitário.

Tipo: sequência de caracteres

Valores: batch/unitário

## recurrenceIndex

Índice da recorrência se a jornada for em lote e recorrente (a primeira execução tem recurrenceIndex = 1).

Tipo: longo

## isBatchToUnitary

Indica se esta instância unitária foi disparada de uma instância em lote.

Tipo: booleano

## batchExternalKey

Chave externa para evento batch.

Tipo: sequência de caracteres

## batchInstanceID

essa é a ID da instância do lote.

Tipo: sequência de caracteres

## batchUnitaryBranchID

se a instância tiver sido acionada a partir de uma instância de lote, ID de ramificação unitária.

Tipo: sequência de caracteres
