---
product: adobe campaign
solution: Journey Orchestration
title: Sobre dados da Adobe Analytics
description: Saiba como aproveitar os dados da Adobe Analytics
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# Como aproveitar os dados da Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Esta seção se aplica somente a eventos baseados em regras e clientes que precisam usar dados da Adobe Analytics.

Você pode aproveitar todos os dados de evento comportamental da Adobe Analytics que já está capturando e fazendo streaming na plataforma para acionar viagens e automatizar experiências para seus clientes.

Para que isso funcione, é necessário ativar, no Adobe Experience Platform, o conjunto de relatórios que você deseja aproveitar:

1. No Adobe Experience Platform, selecione **[!UICONTROL Sources]** e **[!UICONTROL Add data]** na seção Adobe Analytics. A lista de conjuntos de relatórios Adobe Analytics disponíveis é exibida.

1. Escolha o conjunto de relatórios que deseja ativar, clique em **[!UICONTROL Next]** e em **[!UICONTROL Finish]**.

1. Compartilhe a ID de dados de origem com o ponto de contato do programa alfa.

Isso habilita o conector de origem do Analytics para esse conjunto de relatórios. Sempre que os dados entram, eles são transformados em um evento da Experiência e enviados para o Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obter mais informações sobre o conector de origem Adobe Analytics, consulte a [documentação](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) e [tutorial](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
