---
title: Visão geral do compartilhamento de etapas de jornada
description: Visão geral do compartilhamento de etapas de jornada
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
source-git-commit: b8cfc9de56e879d8812cf3871067252937454e1d
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Visão geral do compartilhamento de etapas de jornada{#sharing-overview}

[!DNL Journey Orchestration] envia automaticamente os dados de desempenho da viagem para o Adobe Experience Platform para que possam ser combinados com outros dados para fins de análise.

Por exemplo, você configurou uma jornada que envia vários emails. Esse recurso permite combinar [!DNL Journey Orchestration] dados com dados de evento downstream, como quantas conversões ocorreram, quanto envolvimento aconteceu no site ou quantas transações ocorreram na loja. As informações de viagem podem ser combinadas com dados no Adobe Experience Platform, de outras propriedades digitais ou de propriedades offline, para oferecer uma visualização mais abrangente de desempenho.

[!DNL Journey Orchestration] cria automaticamente os schemas e fluxos necessários em conjuntos de dados para o Adobe Experience Platform para cada etapa que um indivíduo faz em uma jornada. Um evento Step corresponde a um indivíduo que se move de um nó para outro em uma jornada. Por exemplo, em uma jornada que tem um evento, uma condição e uma ação, eventos de três etapas são enviados para o Adobe Experience Platform.

A lista de campos XDM que são passados é abrangente. Alguns contêm códigos gerados pelo sistema e outros têm nomes amigáveis e legíveis. Os exemplos incluem o rótulo da atividade de viagem ou o status da etapa: quantas vezes uma ação atingiu o tempo limite ou terminou com erro.

>[!CAUTION]
>
>Os conjuntos de dados não podem ser ativados para o serviço de perfil em tempo real. Certifique-se de que a **[!UICONTROL Profile]** alternância está desativada

As viagens enviam os dados como ocorrem, de forma contínua. É possível query desses dados usando o Serviço de Query. Você pode se conectar ao Customer Journey Analytics ou a outras ferramentas BI para visualização de dados relacionados a essas etapas.

Os seguintes schemas são criados:

* schema de Perfil da Etapa de Jornada para [!DNL Journey Orchestration] - Eventos de experiência para as etapas realizadas em uma Jornada junto com um Mapa de identidade a ser usado para mapear para um participante individual da jornada.
* schema de Evento de Etapa de Jornada para [!DNL Journey Orchestration] - evento de etapa de jornada vinculado a um Metadados de Jornada.
* schema de jornada com campos de jornada para [!DNL Journey Orchestration] - Metadados de jornada para descrever Jornadas.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Os seguintes conjuntos de dados são enviados:

* schema de Perfil da Etapa de Jornada para Evento [!DNL Journey Orchestration]
* Eventos de Etapa de Jornada
* Jornadas

![](../assets/sharing3.png)

As listas dos campos XDM passados para o Adobe Experience Platform são detalhadas aqui:

* [campos comuns de eventos de passos](../building-journeys/sharing-common-fields.md)
* [campos de execução de ação de eventos JourStep](../building-journeys/sharing-execution-fields.md)
* [campos de busca de dados dos eventos JourStep](../building-journeys/sharing-fetch-fields.md)
* [campos de identidade do evento JourStep](../building-journeys/sharing-identity-fields.md)
* [campos de viagem](../building-journeys/sharing-journey-fields.md)

Para obter mais informações sobre eventos de etapa relatórios a Adobe Experience Platform, assista a este vídeo [de](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)tutorial.
