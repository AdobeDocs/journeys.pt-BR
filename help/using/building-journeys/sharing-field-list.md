---
title: Lista de campos de evento de etapa
description: Lista de campos de evento de etapa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 4291dfc91c2fb29d294416ceed022ee00842c870
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 14%

---

# Lista de campos de evento de etapa {#sharing-field-list}

Os campos de evento Step são organizados por categoria.

* Campos de informações de depuração
* Campos de jornada
* Campos de perfil
* Campos de evento de serviço

## debugInfo

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| requestId | String | A ID de solicitação usada pelo Journey Orchestration para rastrear o fluxo de uma solicitação. |

## jornada

Esse grupo de campos é usado no schema de jornada (em relação a journeyStepEvent). Ele contém os seguintes campos:

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | Identificador para a Jornada em questão |
| VersionID | String | Id da versão do jornada. Essa id representa a identidade de uma jornada |
| name | String | Nome da jornada |
| descrição | String | Descrição da jornada |
| version | String | versão, representada como `major`.`minor` |

## perfil

Esse grupo de campos é específico para journeyStepEvent: esse evento está relacionado ao jornada e não tem o identityMap, descrevendo a identidade do perfil, se houver.

Para journeyStepEvent, também precisamos adicionar campos relacionados à identidade:

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | O identificador de perfil identifica o perfil enviado/usado em uma jornada. Por exemplo: foo@adobe.com. |
| namespace | String | Este campo descreve o Namespace referenciado pelo Perfil usado na Jornada. Por exemplo: Email, ECID |

## serviceEvents

Esse mixin contém todos os campos correspondentes a um trabalho de exportação de perfil.

| Nome do campo | Tipo | Descrição |
|---|---|------------|
| ID | String | O identificador do trabalho de exportação de segmentos acionado |
| status | String | O status do trabalho de exportação do segmento: em fila, iniciado, concluído |
| exportCountTotal | Número inteiro | O valor máximo possível do trabalho de exportação de segmento |
| exportCountRealized | Número inteiro | O número real de segmentos exportados por meio da tarefa |
| exportCountFailed | Número inteiro | O número de segmentos que falharam ao exportar através da tarefa |
| exportSegmentID | String | O identificador do segmento que está sendo exportado |
| eventType | String | O tipo de evento que indica se é um evento de erro do evento de informações: Informações, Erro |
| eventCode | String | O código de erro que indica o motivo para eventType correspondente |

## stepEvents

Esta categoria contém os campos de evento da etapa original. Consulte esta [seção](../building-journeys/sharing-legacy-fields.md).
