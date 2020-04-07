---
title: Selecionar o namespace
description: Saiba como selecionar a namespace
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Selecionar o namespace {#concept_ckb_3qt_52b}

A namespace permite definir o tipo de chave usada para identificar a pessoa associada ao evento. Sua configuração é opcional. É necessário se você quiser recuperar, em suas viagens, informações adicionais provenientes do Perfil [Cliente em tempo](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)real. A definição da namespace não é necessária se você estiver usando apenas dados provenientes de um sistema de terceiros por meio de uma fonte de dados personalizada.

Você pode usar um dos predefinidos ou criar um novo usando o serviço de Namespace de identidade. Consulte esta [página](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html).

Se você selecionar um schema que tenha uma identidade primária, os campos **[!UICONTROL Key]** e **[!UICONTROL Namespace]** serão preenchidos previamente. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar uma namespace e a chave será pré-preenchida (abaixo do **[!UICONTROL Namespace]** campo) usando _identityMap > id_.

Ao selecionar campos, os campos de identidade primários são marcados com tags.

![](../assets/primary-identity.png)


Selecione uma namespace na lista suspensa.

![](../assets/journey17.png)

Apenas uma namespace é permitida por viagem. Se você usar vários eventos na mesma jornada, eles precisam usar a mesma namespace. Consulte [](../building-journeys/journey.md).
