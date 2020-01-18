---
title: Definição da chave de evento
description: Saiba como definir a chave do evento
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Definição da chave de evento {#concept_ond_hqt_52b}

A chave é o campo ou combinação de campos que faz parte dos dados de carga do evento e permitirá que o sistema identifique a pessoa associada ao evento. A chave pode ser, por exemplo, a Experience Cloud ID, uma CRM ID ou um endereço de email.

Se você planeja aproveitar os dados armazenados no banco de dados de Perfil do cliente em tempo real, é necessário selecionar, como chave do evento, as informações que você definiu como identidade do perfil no Serviço [de perfil do cliente em tempo](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)real.

Isso permitirá que o sistema realize a reconciliação entre o evento e o perfil do indivíduo. Se você selecionar um esquema que tenha uma identidade primária, os campos **[!UICONTROL Key]**e**[!UICONTROL Namespace]** serão preenchidos previamente. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar um namespace e a chave será pré-preenchida (abaixo do **[!UICONTROL Namespace]**campo) usando _identityMap > id_.

Se precisar usar uma chave diferente, como uma ID CRM ou um endereço de email, é necessário adicioná-la manualmente:

1. Clique dentro do **[!UICONTROL Key]**campo ou no ícone de lápis.

   ![](../assets/journey16.png)

1. Selecione o campo escolhido como a chave na lista de campos de carga. Você também pode alternar para o editor de expressões avançadas para criar chaves mais complexas (por exemplo, uma concatenação de dois campos dos eventos). Veja abaixo, nesta seção.

   ![](../assets/journey20.png)

Quando o evento for recebido, o valor da chave permitirá que o sistema identifique a pessoa associada ao evento. Associada a um namespace (consulte [](../event/selecting-the-namespace.md)), a chave pode ser usada para realizar consultas na plataforma Adobe Experience. Consulte [](../building-journeys/about-orchestration-activities.md).
A chave também é usada para verificar se uma pessoa está em uma jornada. Na verdade, uma pessoa não pode estar em dois lugares diferentes na mesma viagem. Como resultado, o sistema não permite que a mesma chave, por exemplo a chave CRMID=3224, esteja em diferentes locais na mesma viagem.

Você também tem acesso às funções de expressão avançada (**[!UICONTROL Advanced mode]**) se quiser realizar manipulações adicionais. Essas funções permitem manipular os valores usados para realizar consultas específicas, como formatos em alteração, realizar concatenações de campo, levando em conta apenas uma parte de um campo (por exemplo, os 10 primeiros caracteres). Consulte[](../expression/expressionadvanced.md).
