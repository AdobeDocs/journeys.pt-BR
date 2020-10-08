---
title: Configurar o URL
description: Saiba mais sobre a configuração de URL
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
