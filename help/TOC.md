---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# Ajuda da Orquestração de Jornadas {#using}

+ [Documentação do produto](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [Notas de versão](using/release-notes/release-notes.md)
   + [Atualizações da documentação](using/release-notes/documentation-updates.md)
+ Começando com a Journey Orchestration {#starting-with-journeys}
   + [Sobre a Orquestração de Jornadas](using/about/about-journey-orchestration.md)
   + [Introdução](using/about/get-started.md)
   + [Interface do usuário](using/about/user-interface.md)
   + [Gerenciamento de acesso](using/about/access-management.md)
   + [Solução de problemas](using/about/troubleshooting.md)
+ Configuração de um evento {#events-journeys}
   + [Sobre eventos](using/event/about-events.md)
   + [Definição dos campos de carga](using/event/defining-the-payload-fields.md)
   + [Selecionar o namespace](using/event/selecting-the-namespace.md)
   + [Definição da chave de evento](using/event/defining-the-event-key.md)
   + [Adicionar uma condição](using/event/adding-a-condition.md)
   + [Visualização da carga](using/event/previewing-the-payload.md)
   + [Etapas adicionais para enviar eventos](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configuração de uma fonte de dados {#data-source-journeys}
   + [Sobre fontes de dados](using/datasource/about-data-sources.md)
   + [Grupos de campos](using/datasource/field-groups.md)
   + [Fonte de dados do Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Fontes de dados externas](using/datasource/external-data-sources.md)
+ Configurar uma ação {#action-journeys}
   + [Sobre ações](using/action/action.md)
   + [Trabalhar com o Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Uso de um sistema de terceiros {#action-third-party}
      + [Sobre a configuração de ação personalizada](using/action/about-custom-action-configuration.md)
      + [Limitações de ação personalizada](using/action/custom-action-limitations.md)
      + [Configuração do URL](using/action/url-configuration.md)
      + [Definição dos parâmetros da mensagem](using/action/defining-the-message-parameters.md)
+ Construção de uma jornada {#building-journeys}
   + Sobre construção de viagens {#about-journey-building}
      + [Criação de uma jornada](using/building-journeys/journey.md)
      + [Uso do designer de jornada](using/building-journeys/using-the-journey-designer.md)
      + [Alterar propriedades](using/building-journeys/changing-properties.md)
      + [Versões de viagem](using/building-journeys/journey-versions.md)
      + [Terminando uma viagem](using/building-journeys/terminating-a-journey.md)
      + [Gerenciamento de fuso horário](using/building-journeys/timezone-management.md)
   + Atividades {#about-journey-building}
      + [Atividades de eventos](using/building-journeys/event-activities.md)
      + Atividades de orquestração {#orchestration-activities}
         + [Sobre atividades de orquestração](using/building-journeys/about-orchestration-activities.md)
         + [Atividade de condição](using/building-journeys/condition-activity.md)
         + [Finalizar atividade](using/building-journeys/end-activity.md)
         + [Atividade de espera](using/building-journeys/wait-activity.md)
      + Atividades de ação {#action-activities}
         + [Sobre atividades de ação](using/building-journeys/about-action-activities.md)
         + [Uso de ações do Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Uso de ações personalizadas](using/building-journeys/using-custom-actions.md)
   + [Teste da viagem](using/building-journeys/testing-the-journey.md)
   + [Publicar a jornada](using/building-journeys/publishing-the-journey.md)
+ Uso do editor de expressões avançadas {#building-advanced-conditions-journeys}
   + [Sobre o editor de expressões avançadas](using/expression/expressionadvanced.md)
   + Sintaxe {#syntax}
      + [Generalidades](using/expression/generalities.md)
      + [Instrução condicional](using/expression/conditional-instruction.md)
      + [Tipos de dados](using/expression/data-types.md)
      + [Referências de campo](using/expression/field-references.md)
      + [Funções de gerenciamento de coleções](using/expression/collection-management-functions.md)
      + [Operadores](using/expression/operators.md)
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
         + [differentCount](using/functions/functiondistinctcount.md)
         + [differentCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [soma](using/functions/functionsum.md)
      + Conversão {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Data {#date}
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [nosÚltimos Anos](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [nos Próximos Anos](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + List {#list}
         + [distinto](using/functions/functiondistinct.md)
         + [differentWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [espécie](using/functions/functionsort.md)
      + Matemática {#math}
         + [aleatório](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Cadeia de caracteres {#string}
         + [concat](using/functions/functionconcat.md)
         + [contém](using/functions/functioncontain.md)
         + [containsWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [sameWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [comprimento](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [SAA](using/functions/functionsubstr.md)
         + [aparo](using/functions/functiontrim.md)
         + [parte superior](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Criação de relatórios{#journey-reports}
   + [Sobre relatórios de jornada](using/reporting/about-journey-reports.md)
   + [Criação de relatórios de jornada](using/reporting/creating-your-journey-reports.md)
   + [Métricas e dimensões](using/reporting/metrics-and-dimensions.md)
+ Casos de uso{#use-cases-journeys}
   + Caso de uso simples{#use-case-simple}
      + [Sobre o caso de uso simples](using/usecase/about-the-simple-use-case.md)
      + [Configuração do evento](using/usecase/configuring-the-event.md)
      + [Configuração da fonte de dados](using/usecase/configuring-the-data-source.md)
      + [Construção da viagem](using/usecase/simple-uc-building-the-journey.md)
   + Caso de uso avançado{#use-case-advanced}
      + [Sobre o caso de uso avançado](using/usecase/about-the-advanced-use-case.md)
      + [Configuração dos eventos](using/usecase/configuring-the-events.md)
      + [Configuração das fontes de dados](using/usecase/configuring-the-data-sources.md)
      + [Construção da viagem](using/usecase/building-the-journey.md)
   + [Alavancando pontuações de fadiga](using/usecase/leveraging-fatigue-scores.md)

