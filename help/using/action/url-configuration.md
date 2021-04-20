---
product: adobe campaign
solution: Journey Orchestration
title: Configurar o URL
description: Saiba mais sobre a configuração do URL
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 9%

---


# Configurar o URL {#concept_gbg_1f1_2gb}

Ao configurar uma ação personalizada, você precisa definir os seguintes parâmetros **[!UICONTROL URL Configuration]**:

![](../assets/journeyurlconfiguration.png)

1. Adicione o **[!UICONTROL URL]** do serviço externo.

   >[!NOTE]
   >
   >Recomendamos o uso de HTTPS por motivos de segurança. Não permitimos o uso de endereços Adobe que não são públicos e o uso de endereços IP.

1. Selecione a chamada **[!UICONTROL Method]**: pode ser **[!UICONTROL POST]** ou **[!UICONTROL PUT]**.
1. Na seção **[!UICONTROL Headers]**, clique em **[!UICONTROL Add a header field]** para definir um novo par de chave/valor. Eles correspondem aos cabeçalhos HTTP da solicitação feita para o serviço externo. Para excluir pares de chave/valor, coloque o cursor no campo **[!UICONTROL Headers]** e clique no ícone **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** e  **[!UICONTROL Charset]** são definidas por padrão e não podem ser excluídas ou substituídas.

   >[!NOTE]
   >
   >Os cabeçalhos são validados de acordo com as seguintes [regras de análise](https://tools.ietf.org/html/rfc7230#section-3.2.4).
