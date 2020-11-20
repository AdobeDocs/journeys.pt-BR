---
product: adobe campaign
solution: Journey Orchestration
title: Configurar o URL
description: Saiba mais sobre a configuração de URL
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# Configurar o URL {#concept_gbg_1f1_2gb}

Ao configurar uma ação personalizada, é necessário definir os seguintes **[!UICONTROL URL Configuration]** parâmetros:

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >Recomendamos o uso de HTTPS por motivos de segurança. Não permitimos o uso de endereços Adobe que não sejam públicos e o uso de endereços IP.

1. Selecione a chamada **[!UICONTROL Method]**: pode ser **[!UICONTROL POST]** ou **[!UICONTROL PUT]**.
1. Na **[!UICONTROL Headers]** seção, clique em **[!UICONTROL Add a header field]** para definir um novo par de chave/valor. Eles correspondem aos cabeçalhos HTTP da solicitação feita ao serviço externo. Para excluir pares de chaves/valores, posicione o cursor no **[!UICONTROL Headers]** campo e clique no **[!UICONTROL Delete]** ícone.

   **[!UICONTROL Content-Type]** e **[!UICONTROL Charset]** são definidas por padrão e não podem ser excluídas ou substituídas.

   >[!NOTE]
   >
   >Os cabeçalhos são validados de acordo com as seguintes regras [de](https://tools.ietf.org/html/rfc7230#section-3.2.4)análise.
