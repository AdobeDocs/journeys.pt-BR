---
title: Lista de campos de evento de etapa
description: Lista de campos de evento de etapa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 16%

---

# Lista de campos de evento de etapa {#sharing-field-list}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Os campos de evento de etapa são organizados por categoria.

* Campos de informações de depuração
* Campos de jornada
* Campos de perfil
* Campos de evento de serviço

## debugInfo

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| requestId | String | A ID da solicitação usada pelo Journey Orchestration para rastrear o fluxo de uma solicitação. |

## jornada

Esse grupo de campos é usado no esquema de jornada (em relação a journeyStepEvent). Ele contém os seguintes campos:

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | Identificador para a Jornada fornecida |
| VersionID | String | Id da versão do jornada. Essa id representa a identidade de uma jornada |
| name | String | Nome da jornada |
| descrição | String | Descrição da jornada |
| version | String | versão, representada como `major`.`minor` |

## perfil

Este grupo de campos é específico do journeyStepEvent: este evento está relacionado ao jornada e não tem o identityMap, que descreve a identidade do perfil, se houver.

Para journeyStepEvent, também é necessário adicionar campos relacionados à identidade:

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | O identificador de perfil identifica o perfil enviado/usado em uma jornada. Por exemplo: foo@adobe.com. |
| namespace | String | Este campo descreve o namespace referenciado pelo perfil usado na Jornada. Por exemplo: Email, ECID |

## serviceEvents

Este mixin contém todos os campos correspondentes a um trabalho de exportação de perfil.

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | O identificador do trabalho de exportação de segmento acionado |
| status | String | O status do trabalho de exportação de segmento: em fila, iniciado, concluído |
| exportCountTotal | Número inteiro | O valor máximo possível do trabalho de exportação de segmento |
| exportCountRealized | Número inteiro | O número real de segmentos exportados através do trabalho |
| exportCountFailed | Número inteiro | O número de segmentos que falharam ao exportar pelo trabalho |
| exportSegmentID | String | O identificador do segmento sendo exportado |
| eventType | String | O tipo de evento que indica se é um evento de erro do evento info: Info, Error |
| eventCode | String | O código de erro que indica o motivo para eventType correspondente |

## stepEvents

Esta categoria contém os campos de evento de etapa originais. Consulte esta [seção](../building-journeys/sharing-legacy-fields.md).
