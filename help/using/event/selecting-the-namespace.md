---
product: adobe campaign
title: Selecionar o namespace
description: Saiba como selecionar o namespace
feature: Jornadas
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 6%

---

# Selecionar o namespace {#concept_ckb_3qt_52b}

O namespace permite definir o tipo de chave usada para identificar a pessoa associada ao evento. Sua configuração é opcional. É necessário se você quiser recuperar, em suas jornadas, informações adicionais provenientes do [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html). A definição do namespace não é necessária se você estiver usando apenas dados provenientes de um sistema de terceiros por meio de uma fonte de dados personalizada.

Você pode usar um dos predefinidos ou criar um novo usando o serviço Namespace de identidade. Consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html).

Se você selecionar um esquema que tenha uma identidade primária, os campos **[!UICONTROL Key]** e **[!UICONTROL Namespace]** serão pré-preenchidos. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar um namespace e a chave será pré-preenchida (abaixo do campo **[!UICONTROL Namespace]**) usando _identityMap > id_.

Ao selecionar campos, os campos de identidade primários são marcados.

![](../assets/primary-identity.png)


Selecione um namespace na lista suspensa.

![](../assets/journey17.png)

Somente um namespace é permitido por jornada. Se você usar vários eventos na mesma jornada, eles precisarão usar o mesmo namespace. Consulte [esta página](../building-journeys/journey.md).
