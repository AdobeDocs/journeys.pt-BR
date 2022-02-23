---
product: adobe campaign
title: Atualizações de documentação
description: Saiba mais sobre atualizações da documentação
feature: Journeys
role: User
level: Beginner
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: a5f84d291a5fcb3a0899e9eaabfaf7a7aa12471d
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 96%

---

# Atualizações de documentação

Esta página lista todas as atualizações na documentação do [!DNL Journey Orchestration].
Você também pode consultar as [!DNL Journey Orchestration] [Notas de versão](../release-notes/release-notes.md).

## Fevereiro de 2022 {#feb-2022}

* O [replace](../functions/functionreplace.md#example_2) e [replaceAll](../functions/functionreplaceall.md#example) as páginas de documentação da função foram atualizadas com informações adicionais e exemplos relacionados ao parâmetro target .
* As práticas recomendadas foram adicionadas ao [Operadores](../expression/operators.md#important-notes) página.

## Setembro de 2021

* As seguintes páginas de função foram atualizadas: [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* As seguintes funções foram adicionadas: [filtro](../functions/functionfilter.md), [interseção](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* O tipo de data dateOnly foi adicionado na documentação do editor de expressão. [Leia mais](../expression/data-types.md)

* Foram adicionados detalhes sobre a duração do cache de ação personalizada. [Leia mais](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Foram adicionadas informações sobre as portas padrão de ação personalizada. [Leia mais](../action/url-configuration.md)

* Foram adicionados exemplos usados com frequência para consultar eventos de etapa da jornada no Data Lake. [Leia mais](../building-journeys/query-examples.md)

## Agosto de 2021

* Atualização do procedimento de configuração para ações personalizadas com caminhos dinâmicos de URL e cabeçalhos dinâmicos. [Leia mais](../action/url-configuration.md)
* Adição de uma seção sobre recursos de acessibilidade. [Leia mais](../about/user-interface.md#accessibility)
* Adição de uma seção sobre métodos de avaliação de segmento. [Leia mais](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## Março de 2021 {#march-2021}

* Detalhamos o procedimento completo para criar perfis de teste no Adobe Experience Platform. [Leia mais](../building-journeys/creating-test-profiles.md).

## Janeiro de 2021 {#january-2021}

* Adição de práticas recomendadas ao acionar uma jornada ao mesmo tempo que a criação de um perfil. [Leia mais](../about/limitations.md#journeys-limitation-profile-creation).

## Outubro de 2020 {#october-2020}

* Foram adicionadas informações sobre como configurar um tempo limite para um evento. [Leia mais](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## Setembro de 2020 {#september-2020}

* A seção de descrição da interface foi atualizada para refletir o novo menu **Todos os seletores**. [Leia mais](../about/user-interface.md)
* Adição de uma observação sobre as novas versões das jornadas baseadas em segmentos que não são recorrentes.

## Agosto de 2020 {#august-2020}

* Foram adicionadas informações sobre como classificar e escolher as colunas que serão exibidas na lista de segmentos. [Leia mais](../building-journeys/segment-qualification-events.md)
* Foram adicionadas informações sobre como copiar o nome e a ID de um segmento após sua seleção. [Leia mais](../building-journeys/segment-qualification-events.md)
* As ocorrências da Experience Platform foram harmonizadas entre as diferentes páginas.

## Julho de 2020 {#july-2020}

* Adição de um link para um novo vídeo tutorial sobre os relatórios de eventos da etapa para a Adobe Experience Platform. [Leia mais](../building-journeys/sharing-overview.md)
* A seção de atividades de eventos foi reorganizada em subseções dedicadas a cada tipo de evento. [Leia mais](../building-journeys/event-activities.md)
* Adição de práticas recomendadas para evitar sobrecarga com a qualificação de segmento. [Leia mais](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Adição de uma observação explicativa sobre como uma jornada pode continuar após um erro em uma ação ou condição. [Leia mais](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Adição de uma nova seção sobre os recursos Alfa que são testados entre um conjunto limitado de clientes.
* Adição de uma nova seção sobre a integração com os Serviços inteligentes. [Leia mais](../ai-services/ai-services-overview.md)
* Adição de uma nova seção sobre a criação do perfil de teste. [Leia mais](../building-journeys/testing-the-journey.md)
* Adição de informações sobre como usar o nó **[!UICONTROL SegmentQualification]** em uma condição de jornada ou ação. [Leia mais](../building-journeys/segment-qualification-events.md)
* Adição de uma observação à publicação de mensagens transacionais e eventos do Campaign. Consulte [Trabalhar com Adobe Campaign](../action/working-with-adobe-campaign.md) e [Usar ações do Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Adição de informações sobre as verificações feitas ao testar o URL da instância do Campaign Standard. [Leia mais](../action/working-with-adobe-campaign.md)
* Adição de informações sobre a compatibilidade dos eventos de reação com instâncias do Campaign Standard hospedadas em servidores AWS ou Azure. [Leia mais](../building-journeys/reaction-events.md)
* Adição de uma observação sobre a necessidade de configurar uma regra de limitação ao trabalhar com mensagens transacionais do Campaign Standard. [Leia mais](../action/working-with-adobe-campaign.md)
* Foi adicionada uma observação à geração de eventos reais ao disparar eventos usando o modo de teste. [Leia mais](../building-journeys/testing-the-journey.md#firing_events)

## Junho de 2020 {#june-2020}

* Adição de informações sobre como alterar a duração do cache do token para uma fonte de dados de autenticação personalizada. [Leia mais](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Atualização de capturas de tela e texto para refletir a renomeação do estado da jornada **[!UICONTROL Finished]** que foi alterado para **[!UICONTROL Closed (no entrance)]**.
* Adição de informações sobre como o idioma é definido para a interface. [Leia mais](../about/user-interface.md)
* A lista dos status da jornada de uma pessoa foi movida para a seção [Logs modo de teste](../building-journeys/testing-the-journey.md#viewing_logs).

## Abril de 2020 {#april-2020}

* Adição de uma nova seção sobre a definição do schema do evento da experiência para ajudar os usuários a configurar o primeiro evento. [Leia mais](../event/experience-event-schema.md)
* A home page da documentação do [!DNL Journey Orchestration] foi atualizada com links úteis adicionais. [Leia mais](../../journey-orchestration-home.md)

## Março de 2020 {#march-2020}

* Adição de descrições de parâmetros para _actionExecutionErrors_ e _fetchErrors_ na seção de logs de teste. [Leia mais](../building-journeys/testing-the-journey.md#viewing_logs)
* As limitações das ações personalizadas usadas em uma jornada foram atualizadas. Também é possível modificar o campo **[!UICONTROL URL]** e os parâmetros **[!UICONTROL Authentication]**. [Leia mais](../action/about-custom-action-configuration.md)
* Novas entradas de ajuda contextual foram adicionadas. O painel de carga útil de autenticação personalizada (em ações e fontes de dados) agora inclui um ícone de ajuda que se vincula a esta [seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Agora as jornadas concluídas podem ser interrompidas. [Leia mais](../building-journeys/using-the-journey-designer.md)
* A seção de descrição da interface foi reorganizada. [Leia mais](../about/user-interface.md)
* O acionamento de vários eventos foi adicionado à seção Modo de teste [Leia mais](../building-journeys/testing-the-journey.md#firing_events)
* A seção Modo de teste foi atualizada em relação ao novo parâmetro **[!UICONTROL Wait time in test]**. [Leia mais](../building-journeys/testing-the-journey.md)
* A seção Log de teste foi atualizada com códigos de erro de chamada externos e respostas. [Leia mais](../building-journeys/testing-the-journey.md#viewing_logs)
* O gerenciamento de fuso horário agora está centralizado no painel de propriedades da jornada. Leia mais [aqui](../building-journeys/changing-properties.md#timezone) e [aqui](../building-journeys/timezone-management.md)
* A seção Designer de jornadas foi atualizada para divulgar os aprimoramentos recentes. [Leia mais](../building-journeys/using-the-journey-designer.md)
* A descrição da interface foi atualizada com informações sobre ajuda contextual. [Leia mais](../about/user-interface.md#section_ksq_zr1_ffb)
* Ao navegar pelos **campos XDM**, o nome amigável agora é exibido. As seções relacionadas foram atualizadas. [Leia mais](../about/user-interface.md#friendly-names-display)

## Fevereiro de 2020 {#february-2020}

* A seção de atalho foi atualizada. O atalho **C** do teclado permite criar um novo item em todas as telas de lista. [Leia mais](../about/user-interface.md#section_ksq_zr1_ffb)
* As páginas de visão geral de [fonte de dados](../datasource/about-data-sources.md) e [ação](../action/action.md) foram aprimoradas.

## Janeiro de 2020 {#january-2020}

* Foram adicionadas limitações à busca de [eventos de experiência](../datasource/adobe-experience-platform-data-source.md) e [segmentos](../functions/functioninsegment.md).

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## Dezembro de 2019 {#december-2019}

* Todas as capturas de tela foram atualizadas para divulgar as alterações na interface.
* A seção do modo de teste foi atualizada. [Leia mais](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* Agora, as jornadas interrompidas podem ser excluídas. As páginas de documentação relacionadas foram atualizadas.
* Agora, duas cores são exibidas quando problemas são detectados em uma jornada. Vermelho para erros e laranja para avisos. [Leia mais](../about/troubleshooting.md)
* A seção do editor de expressão avançado foi atualizada. [Leia mais](../expression/expressionadvanced.md).
* As seções [instrução condicional](../expression/conditional-instruction.md) e [gerenciamento de Coleção](../expression/collection-management-functions.md) foram movidas e atualizadas.
* A seção [funções](../expression/functions.md) foi atualizada com novos exemplos.
* A documentação da [função toDateTime](../functions/functiontodatetime.md) foi atualizada para divulgar as alterações na sintaxe do fuso horário.
