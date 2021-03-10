---
product: adobe campaign
solution: Journey Orchestration
title: Selecionar namespace
description: Saiba como selecionar o namespace
feature: Jornada
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 13%

---


# Selecionar namespace {#concept_ckb_3qt_52b}

O namespace permite definir o tipo de chave usada para identificar a pessoa associada ao evento. Sua configuração é opcional. É necessário se você quiser recuperar, em suas jornadas, informações adicionais provenientes do [Real-time Customer Profile](https://docs.adobe.com/content/help/pt-BR/experience-platform/profile/home.html). A definição do namespace não é necessária se você estiver usando apenas dados provenientes de um sistema de terceiros por meio de uma fonte de dados personalizada.

Você pode usar um dos predefinidos ou criar um novo usando o serviço Namespace de identidade. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/experience-platform/identity/home.html).

Se você selecionar um esquema que tenha uma identidade primária, os campos **[!UICONTROL Key]** e **[!UICONTROL Namespace]** serão pré-preenchidos. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar um namespace e a chave será pré-preenchida (abaixo do campo **[!UICONTROL Namespace]**) usando _identityMap > id_.

Ao selecionar campos, os campos de identidade primários são marcados.

![](../assets/primary-identity.png)


Selecione um namespace na lista suspensa.

![](../assets/journey17.png)

Somente um namespace é permitido por jornada. Se você usar vários eventos na mesma jornada, eles precisarão usar o mesmo namespace. Consulte [esta página](../building-journeys/journey.md).
