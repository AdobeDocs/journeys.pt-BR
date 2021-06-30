---
product: adobe campaign
title: Sobre dados do Adobe Analytics
description: Saiba como aproveitar os dados do Adobe Analytics
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Como aproveitar os dados do Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Esta seção se aplica somente a eventos com base em regras e clientes que precisam usar dados do Adobe Analytics.

Você pode aproveitar todos os dados de evento comportamental do Adobe Analytics que já estão sendo capturados e transmitidos na plataforma para acionar jornadas e automatizar experiências para seus clientes.

Para que isso funcione, é necessário ativar, no Adobe Experience Platform, o conjunto de relatórios que deseja aproveitar:

1. No Adobe Experience Platform, selecione **[!UICONTROL Sources]** e **[!UICONTROL Add data]** na seção Adobe Analytics. A lista de conjuntos de relatórios disponíveis do Adobe Analytics é exibida.

1. Escolha o conjunto de relatórios que deseja habilitar, clique em **[!UICONTROL Next]** e clique em **[!UICONTROL Finish]**.

1. Compartilhe a ID de dados de origem com o ponto de contato do programa Alfa.

Isso ativa o conector de origem do Analytics para esse conjunto de relatórios. Sempre que os dados entram, eles são transformados em um evento de Experiência e enviados para o Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obter mais informações sobre o conector de origem do Adobe Analytics, consulte a [documentação](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) e [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
