---
product: adobe campaign
title: campos comuns de eventos journeystep
description: campos comuns de eventos journeystep
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# campos comuns de eventos de passos de jornada {#sharing-common-fields}

Esse mixin será compartilhado por journeyStepEvent e journeyStepProfileEvent.

Esses são os campos XDM comuns que [!DNL Journey Orchestration] envia para o Adobe Experience Platform. Campos comuns serão enviados para cada etapa que é processada em uma jornada. Campos mais específicos são usados para ações e enriquecimentos personalizados.

Alguns desses campos estão disponíveis apenas em padrões de processamento específicos (execução de ação, busca de dados etc.) para limitar o tamanho dos eventos.

## entrada

Indica se o usuário inseriu a jornada. Se não estiver presente, assumimos que o valor é false.

Tipo: booleano

Valores: true/false

## reentrada

Indica se o usuário entrou novamente na jornada com a mesma instância. Se não estiver presente, assumimos que o valor é false.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica se a instância terminou (com êxito ou não).

Tipo: booleano

## eventID

ID do evento no processamento, para o processamento da etapa. Se o evento for externo, o valor será eventId. Se o evento for interno, o valor será eventId interno (como scheduledNotificationReceived, executionAction, etc.).

Tipo: string

## nodeID

ID do nó do cliente (na tela).

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
* Scheduler
* Temporizador

## stepStatus

Status da etapa, representando o status da etapa, quando o processamento foi concluído (e o evento de etapa foi acionado).

Tipo: string

O status pode ser:

* encerrado: a etapa não tem transição e seu processamento foi concluído com êxito.
* erro: o processamento da etapa gerou um erro.
* transições: a etapa está aguardando a transição de um evento para outra etapa.
* limitado: a etapa falhou em um erro de limitação, gerado durante uma ação ou enriquecimento.
* tempo limite: a etapa falhou em um erro de tempo limite, gerado durante uma ação ou enriquecimento.
* instanceTimedout: a etapa interrompeu o processamento porque a instância atingiu o tempo limite.

## journeyID

ID da jornada.

Tipo: string

## journeyVersionID

ID da versão do jornada. Essa id representa a referência de identidade para a jornada, no caso de journeyStepEvent.

Tipo: string

## journeyVersionName

Nome da versão do jornada.

Tipo: string

## journeyVersion

Versão da versão do jornada.

Tipo: string

## instanceID

ID interna da instância do jornada.

Tipo: string

## externalKey

Chave externa extraída do evento para processá-la.

Tipo: string

## parentStepID

ID da etapa principal da etapa processada atual na instância.

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

Indicado se essa jornada está no modo de teste ou não.

Tipo: booleano

## processingTime

Tempo total em milissegundos desde a entrada da etapa da instância até o fim do processamento.

Tipo: long

## instanceType

Indica o tipo de instância, se for em lote ou unitário.

Tipo: string

Valores: lote/unidade

## periodicidadeIndex

Índice da recorrência se a jornada for em lote e recorrente (a primeira execução tem recorrênciaIndex = 1).

Tipo: long

## isBatchToUnitary

Indica se essa instância unitária foi acionada a partir de uma instância de lote.

Tipo: booleano

## batchExternalKey

Chave externa para o evento batch.

Tipo: string

## batchInstanceID

essa é a ID da instância de lote.

Tipo: string

## batchUnitaryBranchID

se a instância tiver sido acionada a partir de uma instância de lote, a ID de ramificação unitária.

Tipo: string
