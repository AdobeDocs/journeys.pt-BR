---
product: adobe campaign
solution: Journey Orchestration
title: Visão geral do compartilhamento de etapas da jornada
description: Visão geral do compartilhamento de etapas da jornada
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# Visão geral do compartilhamento de etapas da jornada{#sharing-overview}

[!DNL Journey Orchestration] envia automaticamente os dados de desempenho da jornada para a Adobe Experience Platform para que possam ser combinados com outros dados para fins de análise.

>[!NOTE]
>
>Este recurso não é ativado por padrão em todas as instâncias recém-implantadas. A ativação é mediante solicitação.

Por exemplo, você configurou uma jornada que envia vários emails. Esse recurso permite combinar [!DNL Journey Orchestration] dados com dados de evento downstream, como quantas conversões ocorreram, quanto envolvimento aconteceu no site ou quantas transações ocorreram na loja. As informações de viagem podem ser combinadas com dados no Adobe Experience Platform, de outras propriedades digitais ou de propriedades offline, para proporcionar uma visualização mais abrangente de desempenho.

[!DNL Journey Orchestration] cria automaticamente os schemas e fluxos necessários em conjuntos de dados para a Adobe Experience Platform para cada etapa que um indivíduo faz em uma jornada. Um evento Step corresponde a um indivíduo que se move de um nó para outro em uma jornada. Por exemplo, em uma jornada que tenha um evento, uma condição e uma ação, eventos de três etapas são enviados para a Adobe Experience Platform.

A lista de campos XDM que são passados é abrangente. Alguns contêm códigos gerados pelo sistema e outros têm nomes amigáveis e legíveis. Os exemplos incluem o rótulo da atividade de viagem ou o status da etapa: quantas vezes uma ação atingiu o tempo limite ou terminou com erro.

>[!CAUTION]
>
>Os conjuntos de dados não podem ser ativados para o serviço de perfil em tempo real. Certifique-se de que a **[!UICONTROL Profile]** alternância está desligada.

As viagens enviam os dados como ocorrem, de forma contínua. É possível query desses dados usando o Serviço de Query. Você pode se conectar ao Customer Journey Analytics ou a outras ferramentas BI para visualização de dados relacionados a essas etapas.

Os seguintes schemas são criados:

* Schema de Perfil da Etapa de Jornada para [!DNL Journey Orchestration] - Eventos de experiência para as etapas realizadas em uma Jornada junto com um Mapa de identidade a ser usado para mapear para um participante individual da jornada.
* Schema de Evento de Etapa de Jornada para [!DNL Journey Orchestration] - evento de etapa de jornada vinculado a um Metadados de Jornada.
* Schema de jornada com campos de jornada para [!DNL Journey Orchestration] - Metadados de jornada para descrever Jornadas.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Os seguintes conjuntos de dados são enviados:

* Schema de Perfil da Etapa de Jornada para Evento [!DNL Journey Orchestration]
* Eventos de Etapa de Jornada
* Jornadas

![](../assets/sharing3.png)

As listas dos campos XDM passados para a Adobe Experience Platform estão detalhadas aqui:

* [campos comuns de eventos journeySteps](../building-journeys/sharing-common-fields.md)
* [campos de execução de ação de eventos journeyStep](../building-journeys/sharing-execution-fields.md)
* [campos de busca de dados de eventos journeyStep](../building-journeys/sharing-fetch-fields.md)
* [campos de identidade do evento journeyStep](../building-journeys/sharing-identity-fields.md)
* [campos de jornada](../building-journeys/sharing-journey-fields.md)

Para obter mais informações sobre o relatórios de eventos de etapa para o Adobe Experience Platform, assista a este vídeo [de](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)tutorial.
