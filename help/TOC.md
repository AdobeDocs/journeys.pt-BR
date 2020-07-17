---
product: Journeys
audience: end-user
user-guide-title: Ajuda do Journey Orchestration
index: true
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 78%

---


# [!DNL Journey Orchestration] Ajuda {#using}

+ [Documentação do produto](journey-orchestration-home.md)
+ Novidades {#release-notes}
   + [Notas de versão](using/release-notes/release-notes.md)
   + [Atualizações da documentação](using/release-notes/documentation-updates.md)
+ Starting with [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Sobre o [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Introdução](using/about/get-started.md)
   + [Interface do usuário](using/about/user-interface.md)
   + [Gerenciamento de acesso](using/about/access-management.md)
   + [Solução de problemas](using/about/troubleshooting.md)
+ Configurar um evento {#events-journeys}
   + [Sobre eventos](using/event/about-events.md)
   + [Sobre schemas ExperienceEvent](using/event/experience-event-schema.md)
   + [Definir campos de carga](using/event/defining-the-payload-fields.md)
   + [Selecionar namespace](using/event/selecting-the-namespace.md)
   + [Definir a chave de evento](using/event/defining-the-event-key.md)
   + [Adicionar uma condição](using/event/adding-a-condition.md)
   + [Visualizar a carga](using/event/previewing-the-payload.md)
   + [Etapas adicionais para enviar eventos](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configurar uma fonte de dados {#data-source-journeys}
   + [Sobre fontes de dados](using/datasource/about-data-sources.md)
   + [Grupos de campos](using/datasource/field-groups.md)
   + [Fonte de dados da Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Fontes de dados externas](using/datasource/external-data-sources.md)
+ Configurar uma ação {#action-journeys}
   + [Sobre ações](using/action/action.md)
   + [Trabalhar com o Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Usar um sistema de terceiros {#action-third-party}
      + [Sobre a configuração de ação personalizada](using/action/about-custom-action-configuration.md)
      + [Limitações de ação personalizada](using/action/custom-action-limitations.md)
      + [Configurar o URL](using/action/url-configuration.md)
      + [Definir os parâmetros da mensagem](using/action/defining-the-message-parameters.md)
+ Uso de segmentos de plataforma {#configuring-segment}
   + [Sobre segmentos de plataforma](using/segment/about-segments.md)
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
   + Atividades {#about-journey-building}
      + Atividades de eventos {#events-activities}
         + [Sobre atividades eventos](using/building-journeys/event-activities.md)
         + [eventos gerais](using/building-journeys/general-events.md)
         + [eventos de reação](using/building-journeys/reaction-events.md)
         + [eventos de qualificação de segmentos](using/building-journeys/segment-qualification-events.md)
      + Atividades de orquestração {#orchestration-activities}
         + [Sobre atividades de orquestração](using/building-journeys/about-orchestration-activities.md)
         + [Atividade de condição](using/building-journeys/condition-activity.md)
         + [Finalizar atividade](using/building-journeys/end-activity.md)
         + [Atividade de espera](using/building-journeys/wait-activity.md)
      + Atividades de ação {#action-activities}
         + [Sobre atividades de ação](using/building-journeys/about-action-activities.md)
         + [Usar ações do Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Usar ações personalizadas](using/building-journeys/using-custom-actions.md)
   + [Testar a jornada](using/building-journeys/testing-the-journey.md)
   + [Publicar a jornada](using/building-journeys/publishing-the-journey.md)
   + Compartilhamento de passos de viagem com Adobe Experience Platform {#sharing-journey-steps}
      + [Visão geral do compartilhamento de etapas de jornada](using/building-journeys/sharing-overview.md)
      + [campos comuns de eventos de passos](using/building-journeys/sharing-common-fields.md)
      + [campos de execução de ação de eventos JourStep](using/building-journeys/sharing-execution-fields.md)
      + [campos de busca de dados dos eventos JourStep](using/building-journeys/sharing-fetch-fields.md)
      + [campos de identidade do evento JourStep](using/building-journeys/sharing-identity-fields.md)
      + [campos de viagem](using/building-journeys/sharing-journey-fields.md)
+ Usar o editor de expressões avançadas {#building-advanced-conditions-journeys}
   + [Sobre o editor de expressões avançadas](using/expression/expressionadvanced.md)
   + Sintaxe {#syntax}
      + [Generalidades](using/expression/generalities.md)
      + [Instrução condicional](using/expression/conditional-instruction.md)
      + [Tipos de dados](using/expression/data-types.md)
      + [Referências de campo](using/expression/field-references.md)
      + [Funções de gerenciamento de coleções](using/expression/collection-management-functions.md)
      + [Operadores](using/expression/operators.md)
      + [Exemplos](using/expression/advanced-editor-use-cases.md)
   + Funções {#main-functions-journey}
      + [Funções principais](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + Agregação {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversão {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Data {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
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
      + Lista {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Matemática {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Cadeia de caracteres {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Criar relatórios{#journey-reports}
   + [Sobre relatórios de jornada](using/reporting/about-journey-reports.md)
   + [Criar relatórios de jornada](using/reporting/creating-your-journey-reports.md)
   + [Métricas e dimensões](using/reporting/metrics-and-dimensions.md)
+ Integração com serviços inteligentes{#use-case-advanced}
   + [Sobre a integração do AI](using/ai-services/ai-services-overview.md)
   + [Alavancando a jornada AI](using/ai-services/leveraging-fatigue-scores.md)
   + [Aproveitando a IA do cliente](using/ai-services/leveraging-customer-ai.md)
+ Casos de uso{#use-cases-journeys}
   + Caso de uso simples{#use-case-simple}
      + [Sobre o caso de uso simples](using/usecase/about-the-simple-use-case.md)
      + [Configurar o evento](using/usecase/configuring-the-event.md)
      + [Configurar a fonte de dados](using/usecase/configuring-the-data-source.md)
      + [Construir a jornada](using/usecase/simple-uc-building-the-journey.md)
   + Caso de uso avançado{#use-case-advanced}
      + [Sobre o caso de uso avançado](using/usecase/about-the-advanced-use-case.md)
      + [Configurar os eventos](using/usecase/configuring-the-events.md)
      + [Configurar as fontes de dados](using/usecase/configuring-the-data-sources.md)
      + [Construir a jornada](using/usecase/building-the-journey.md)
+ Trabalho com APIs{#working-with-apis}
   + [Captando APIs](using/api/capping.md)
+ Recursos alfa {#alpha}
   + [Visão geral dos recursos alfa](using/alpha/alpha-overview.md)
   + [Interface do usuário](using/alpha/alpha-interface.md)
   + [atividade do acionador do segmento](using/alpha/alpha-segment-trigger.md)
   + [eventos baseados em regras](using/alpha/alpha-events.md)

