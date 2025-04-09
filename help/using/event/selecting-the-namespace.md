---
product: adobe campaign
title: Selecionar o namespace
description: Saiba como selecionar o namespace
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 6%

---

# Selecionar o namespace {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


O namespace permite definir o tipo de chave usada para identificar a pessoa associada ao evento. Sua configuração é opcional. Isso é necessário se você quiser recuperar, em suas jornadas, informações adicionais provenientes do [Perfil de cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR). A definição do namespace não é necessária se você estiver usando apenas dados provenientes de um sistema de terceiros por meio de uma fonte de dados personalizada.

Você pode usar um dos predefinidos ou criar um novo usando o serviço de namespace de identidade. Consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR).

Se você selecionar um esquema que tenha uma identidade primária, os campos **[!UICONTROL Key]** e **[!UICONTROL Namespace]** serão preenchidos previamente. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar um namespace e a chave será preenchida previamente (abaixo do campo **[!UICONTROL Namespace]**) usando _identityMap > id_.

Ao selecionar campos, os campos de identidade principais são marcados.

![](../assets/primary-identity.png)


Selecione um namespace na lista suspensa.

![](../assets/journey17.png)

Somente um namespace é permitido por jornada. Se você usar vários eventos na mesma jornada, eles precisarão usar o mesmo namespace. Consulte [esta página](../building-journeys/journey.md).
