---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Guia do Journey Orchestration
user-guide-description: Fornece instruções passo a passo para implementar e criar jornadas.
index: true
feature: Journeys
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---


# Manual do [!DNL Journey Orchestration] {#using}

+ [Documentação do produto](journey-orchestration-home.md)
+ Novidades {#release-notes}
   + [Notas de versão](using/release-notes/release-notes.md)
   + [Atualizações de documentação](using/release-notes/documentation-updates.md)
   + [Atualização para Journey Optimizer](using/release-notes/upgrade-to-ajo.md)
+ Primeiros passos com o [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Sobre o  [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Limitações](using/about/limitations.md)
   + [Introdução](using/about/get-started.md)
   + [Interface do usuário](using/about/user-interface.md)
   + [Gerenciamento de acesso](using/about/access-management.md)
   + [Solução de problemas](using/about/troubleshooting.md)
   + [Integração com sistemas externos](using/about/external-systems.md)
+ Configurar um evento {#events-journeys}
   + Sobre eventos {#about-events}
      + [Princípio geral](using/event/about-events.md)
      + [Ciclo de dados](using/event/about-data-cycle.md)
      + [Criação de um evento](using/event/about-creating.md)
      + [Aproveitar o Adobe Analytics](using/event/about-analytics.md)
      + [Sobre esquemas ExperienceEvent](using/event/experience-event-schema.md)
      + [Etapas adicionais para enviar eventos](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Definir os campos de carga](using/event/defining-the-payload-fields.md)
   + [Selecionar o namespace](using/event/selecting-the-namespace.md)
   + [Definir a chave de evento](using/event/defining-the-event-key.md)
   + [Visualizar a carga](using/event/previewing-the-payload.md)
+ Configurar uma fonte de dados {#data-source-journeys}
   + [Sobre fontes de dados](using/datasource/about-data-sources.md)
   + [Grupos de campos](using/datasource/field-groups.md)
   + [Fonte de dados da Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Fontes de dados externas](using/datasource/external-data-sources.md)
+ Configurar uma ação {#action-journeys}
   + [Sobre ações](using/action/action.md)
   + [Trabalhar com o Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [Trabalhar com o Adobe Campaign v7/v8](using/action/acc-action.md)
   + Usar um sistema de terceiros {#action-third-party}
      + [Sobre a configuração de ação personalizada](using/action/about-custom-action-configuration.md)
      + [Configurar o URL](using/action/url-configuration.md)
      + [Definição dos parâmetros de ação](using/action/defining-the-message-parameters.md)
+ Utilização de segmentos {#configuring-segment}
   + [Sobre segmentos](using/segment/about-segments.md)
   + [Criação de um segmento](using/segment/creating-a-segment.md)
   + [Uso de segmentos em condições](using/segment/using-a-segment.md)
+ Construir uma jornada {#building-journeys}
   + Sobre a construção de jornada {#about-journey-building}
      + [Criar uma jornada](using/building-journeys/journey.md)
      + [Usar o designer de jornada](using/building-journeys/using-the-journey-designer.md)
      + [Alterar propriedades](using/building-journeys/changing-properties.md)
      + [Versões de jornada](using/building-journeys/journey-versions.md)
      + [Encerrar uma jornada](using/building-journeys/terminating-a-journey.md)
      + [Gerenciamento de fuso horário](using/building-journeys/timezone-management.md)
      + [Perfis de teste](using/building-journeys/creating-test-profiles.md)
   + Atividades {#about-journey-building}
      + Atividades de eventos {#events-activities}
         + [Sobre atividades de eventos](using/building-journeys/event-activities.md)
         + [Eventos gerais](using/building-journeys/general-events.md)
         + [Eventos de reação](using/building-journeys/reaction-events.md)
         + [Eventos de qualificação de segmento](using/building-journeys/segment-qualification-events.md)
      + Atividades de orquestração {#orchestration-activities}
         + [Sobre atividades de orquestração](using/building-journeys/about-orchestration-activities.md)
         + [Atividade de condição](using/building-journeys/condition-activity.md)
         + [Terminar atividade](using/building-journeys/end-activity.md)
         + [Atividade Aguardar](using/building-journeys/wait-activity.md)
      + Atividades de ação {#action-activities}
         + [Sobre atividades de ação](using/building-journeys/about-action-activities.md)
         + [Uso do Adobe Campaign Standard](using/building-journeys/using-adobe-campaign-actions.md)
         + [Uso do Adobe Campaign v7/v8](using/building-journeys/using-adobe-campaign-classic.md)
         + [Usar ações personalizadas](using/building-journeys/using-custom-actions.md)
         + [Mudar de uma jornada para outra](using/building-journeys/jump.md)
         + [Atualizar perfil](using/building-journeys/update-profiles.md)
   + [Testar a jornada](using/building-journeys/testing-the-journey.md)
   + [Publicar a jornada](using/building-journeys/publishing-the-journey.md)
   + Compartilhamento de etapas de jornada com a Adobe Experience Platform {#sharing-journey-steps}
      + [Visão geral do compartilhamento de etapas da jornada](using/building-journeys/sharing-overview.md)
      + [Lista de campos de evento de etapa](using/building-journeys/sharing-field-list.md)
      + Campos de evento de etapa herdado {#legacy-step-event-fields}
         + [Sobre campos herdados](using/building-journeys/sharing-legacy-fields.md)
         + [campos comuns de eventos journeySteps](using/building-journeys/sharing-common-fields.md)
         + [campos de execução de ação de eventos journeyStep](using/building-journeys/sharing-execution-fields.md)
         + [campos de busca de dados de eventos journeyStep](using/building-journeys/sharing-fetch-fields.md)
         + [campos de identidade do evento journeyStep](using/building-journeys/sharing-identity-fields.md)
         + [campos de jornada](using/building-journeys/sharing-journey-fields.md)
      + [Exemplos de consultas](using/building-journeys/query-examples.md)
+ Criar expressões {#building-advanced-conditions-journeys}
   + [Visão geral](using/expression/expressionadvanced.md)
   + Sintaxe {#syntax}
      + [Generalidades](using/expression/generalities.md)
      + [Instrução condicional](using/expression/conditional-instruction.md)
      + [Tipos de dados](using/expression/data-types.md)
      + [Referências de campo](using/expression/field-references.md)
      + [Funções de gerenciamento de coleções](using/expression/collection-management-functions.md)
      + [Operadores](using/expression/operators.md)
      + [Propriedades da jornada](using/expression/journey-properties.md)
      + [Exemplos](using/expression/advanced-editor-use-cases.md)
   + Funções {#main-functions-journey}
      + [Funções principais](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Agregação {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [contagem](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversão {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Data {#date}
         + [currentTimeInMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + Lista {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filtro](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [no](using/functions/functionin.md)
         + [interseção](using/functions/functionintersect.md)
         + [limite](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Matemática {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + String {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [comprimento](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Criação de relatórios{#journey-reports}
   + [Sobre relatórios de jornada](using/reporting/about-journey-reports.md)
   + [Criação de relatórios de jornada](using/reporting/creating-your-journey-reports.md)
   + [Métricas e dimensões](using/reporting/metrics-and-dimensions.md)
+ Integração com serviços inteligentes{#use-case-advanced}
   + [Sobre a integração de IA](using/ai-services/ai-services-overview.md)
   + [Aproveitamento da IA do cliente](using/ai-services/leveraging-customer-ai.md)
+ Casos de uso{#use-cases-journeys}
   + Envio de um email personalizado{#use-case-simple}
      + [Sobre o caso de uso simples](using/usecase/about-the-simple-use-case.md)
      + [Configuração do evento](using/usecase/configuring-the-event.md)
      + [Configuração da fonte de dados](using/usecase/configuring-the-data-source.md)
      + [Construção da jornada](using/usecase/simple-uc-building-the-journey.md)
   + Construção de uma jornada entre canais{#use-case-advanced}
      + [Sobre o caso de uso avançado](using/usecase/about-the-advanced-use-case.md)
      + [Configuração de eventos](using/usecase/configuring-the-events.md)
      + [Configuração de fontes de dados](using/usecase/configuring-the-data-sources.md)
      + [Construção da jornada](using/usecase/building-the-journey.md)
   + [Envio de uma mensagem usando o Campaign v7/v8](using/usecase/campaign-classic-use-case.md)
   + [Envio dinâmico de coleções usando ações personalizadas](using/usecase/collections.md)
+ Trabalho com APIs{#working-with-apis}
   + [Introdução às APIs de jornadas](using/api/journeys-apis.md)
   + [API de limite](using/api/capping.md)
   + [API de limitação](using/api/throttling.md)
