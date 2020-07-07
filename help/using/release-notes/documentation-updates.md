---
title: Atualizações da documentação
description: Saiba mais sobre atualizações da documentação
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
source-git-commit: 18364d6e93b48e065b21bbaddee33e7ba4d9274d
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 59%

---


# Atualizações da documentação

Esta página lista todas as atualizações de documentação do [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## Julho de 2020 {#july-2020}

* Adicionada uma nova seção sobre os recursos Alfa que são testados entre um conjunto limitado de clientes. [Leia mais](../alpha/alpha-overview.md)
* Adicionada uma nova seção sobre a integração com os Serviços inteligentes. [Leia mais](../ai-services/ai-services-overview.md)
* Adicionada uma nova seção sobre a criação do perfil de teste. [Leia mais](../building-journeys/testing-the-journey.md#create-test-profile)
* Foram adicionadas informações sobre como usar o nó **SegmentQualification** em uma condição de jornada ou ação. [Leia mais](../building-journeys/event-activities.md#segment-qualification)
* Uma observação foi adicionada à publicação de mensagens transacionais e eventos. Consulte [Trabalhar com Adobe Campaign](../action/working-with-adobe-campaign.md) e [Usar ações](../building-journeys/using-adobe-campaign-actions.md)Adobe Campaign.
* Foram adicionadas informações sobre as verificações realizadas ao testar o URL da instância do Campaign Standard. [Leia mais](../action/working-with-adobe-campaign.md)
* Foram adicionadas informações sobre a compatibilidade de evento de reação com instâncias Campaign Standard hospedadas em servidores AWS ou Azure. [Leia mais](../building-journeys/event-activities.md#section_dhx_gss_dgb)
* Foi adicionada uma observação sobre a necessidade de configurar uma regra de limite ao trabalhar com mensagens transacionais de Campaign Standard. [Leia mais](../action/working-with-adobe-campaign.md)
* Uma observação foi adicionada à geração de eventos reais ao disparar eventos usando o modo de teste. [Leia mais](../building-journeys/testing-the-journey.md#firing_events)

## Junho de 2020 {#june-2020}

* Foram adicionadas informações sobre como alterar a duração do cache do token para uma fonte de dados de autenticação personalizada. [Leia mais](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Capturas de tela e texto atualizados para refletir a renomeação do estado de viagem **Concluído** que foi alterado para **Fechado (sem entrada)**.
* Foram adicionadas informações sobre como o idioma é definido para a interface. [Leia mais](../about/user-interface.md)
* A lista dos status da jornada de um indivíduo foi movida para a seção [Testar logs](../building-journeys/testing-the-journey.md#viewing_logs) do modo.

## Abril de 2020 {#april-2020}

* Adicionada uma nova seção sobre a definição do schema do evento da experiência para ajudar os usuários a configurar seu primeiro evento. [Leia mais](../event/experience-event-schema.md)
* O home page da documentação foi atualizado com links úteis adicionais. [!DNL Journey Orchestration] [Leia mais](../../journey-orchestration-home.md)

## Março de 2020 {#march-2020}

* Adição de descrições de parâmetros para _actionExecutionErrors_ e _fetchErrors_ na seção de logs de teste. [Leia mais](../building-journeys/testing-the-journey.md#viewing_logs)
* As limitações das ações personalizadas usadas em uma jornada foram atualizadas. Também é possível modificar o campo **URL** e os parâmetros de **Autenticação**. [Leia mais](../action/about-custom-action-configuration.md)
* Novas entradas de ajuda contextual foram adicionadas. O painel de carga útil de autenticação personalizada (em ações e fontes de dados) agora inclui um ícone de ajuda que se vincula a esta [seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* As viagens fechadas podem agora ser interrompidas. [Leia mais](../building-journeys/using-the-journey-designer.md)
* A seção de descrição da interface foi reorganizada. [Leia mais](../about/user-interface.md)
* O acionamento de vários eventos foi adicionado à seção Modo de teste [Leia mais](../building-journeys/testing-the-journey.md#firing_events)
* A seção Modo de teste foi atualizada com relação ao novo parâmetro **Tempo de espera em teste**. [Leia mais](../building-journeys/testing-the-journey.md)
* A seção Log de teste foi atualizada com códigos de erro de chamada externos e respostas. [Leia mais](../building-journeys/testing-the-journey.md#viewing_logs)
* O gerenciamento de fuso horário agora está centralizado no painel de propriedades da jornada. Leia mais [aqui](../building-journeys/changing-properties.md#timezone) e [aqui](../building-journeys/timezone-management.md)
* A seção Designer de jornadas foi atualizada para divulgar os aprimoramentos recentes. [Leia mais](../building-journeys/using-the-journey-designer.md)
* A descrição da interface foi atualizada com informações sobre ajuda contextual. [Leia mais](../about/user-interface.md#section_ksq_zr1_ffb)
* Ao navegar pelos **campos XDM**, o nome amigável agora é exibido. As seções relacionadas foram atualizadas. [Leia mais](../about/user-interface.md#friendly-names-display)

## Fevereiro de 2020 {#february-2020}

* A seção de atalho foi atualizada. O atalho **C** do teclado permite criar um novo item em todas as telas de lista. [Leia mais](../about/user-interface.md#section_ksq_zr1_ffb)
* As páginas de visão geral da fonte [de](../datasource/about-data-sources.md) dados e da [ação](../action/action.md) foram aprimoradas.

## Janeiro de 2020 {#january-2020}

* Foram adicionadas limitações à busca de [eventos de experiência](../datasource/adobe-experience-platform-data-source.md) e [segmentos](../functions/functioninsegment.md).
* A [documentação getBestSendTime](../functions/functiongetbestsendtime.md) foi atualizada.

## Dezembro de 2019 {#december-2019}

* Todas as capturas de tela foram atualizadas para divulgar as alterações na interface.
* A seção do modo de teste foi atualizada. [Leia mais](../building-journeys/testing-the-journey.md)
* Foi adicionado um aviso nas seções de [otimização de tempo de envio de email](../building-journeys/wait-activity.md) e [pontuações de fadiga preditiva](../ai-services/leveraging-fatigue-scores.md). Esses recursos só estão disponíveis para clientes que usam o recurso Data Service do Adobe Campaign Standard .
* Agora, as jornadas interrompidas podem ser excluídas. As páginas de documentação relacionadas foram atualizadas.
* Agora, duas cores são exibidas quando problemas são detectados em uma jornada. Vermelho para erros e laranja para avisos. [Leia mais](../about/troubleshooting.md)
* A seção avançada do editor de expressões foi atualizada. [Leia mais](../expression/expressionadvanced.md).
* As seções [instrução condicional](../expression/conditional-instruction.md) e [gerenciamento de Coleção](../expression/collection-management-functions.md) foram movidas e atualizadas.
* A seção [funções](../expression/functions.md) foi atualizada com novos exemplos.
* A documentação da [função toDateTime](../functions/functiontodatetime.md) foi atualizada para divulgar as alterações na sintaxe do fuso horário.
