---
product: adobe campaign
title: Sobre dados do Adobe Analytics
description: Saiba como aproveitar os dados do Adobe Analytics
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Aproveitamento dos dados do Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Essa seção se aplica somente a eventos com base em regras e clientes que precisam usar dados do Adobe Analytics.

Você pode aproveitar todos os dados de evento comportamental do Adobe Analytics que já estão sendo capturados e transmitidos na plataforma para acionar jornadas e automatizar experiências para seus clientes.

Para que isso funcione, é necessário ativar no Adobe Experience Platform o conjunto de relatórios que você deseja usar:

1. No Adobe Experience Platform, selecione **[!UICONTROL Sources]** e depois **[!UICONTROL Add data]** na seção Adobe Analytics. A lista de conjuntos de relatórios do Adobe Analytics disponíveis é exibida.

1. Escolha o conjunto de relatórios que deseja habilitar, clique em **[!UICONTROL Next]** e em **[!UICONTROL Finish]**.

1. Compartilhe a ID de dados de origem com o ponto de contato do programa Alpha.

Isso ativa o conector de origem do Analytics para esse conjunto de relatórios. Sempre que os dados entram, são transformados em um evento de experiência e enviados para o Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obter mais informações sobre o conector de origem do Adobe Analytics, consulte a [documentação](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) e o [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
