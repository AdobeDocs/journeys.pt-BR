---
product: adobe campaign
solution: Journey Orchestration
title: Definir a chave de evento
description: Saiba como definir a chave do evento
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%

---


# Definir a chave de evento {#concept_ond_hqt_52b}

A chave é o campo ou combinação de campos que faz parte dos dados de carga do evento e permitirá que o sistema identifique a pessoa associada ao evento. A chave pode ser, por exemplo, a Experience Cloud ID, uma CRM ID ou um endereço de email.

Se você planeja aproveitar os dados armazenados no banco de dados do Perfil do cliente em tempo real, é necessário selecionar, como chave do evento, as informações que você definiu como identidade do perfil no Serviço [de Perfil do cliente em tempo](https://docs.adobe.com/content/help/pt-BR/experience-platform/profile/home.html)real.

Isso permitirá que o sistema realize a reconciliação entre o evento e o perfil do indivíduo. Se você selecionar um schema que tenha uma identidade primária, os campos **[!UICONTROL Key]** e **[!UICONTROL Namespace]** serão preenchidos previamente. Se não houver identidade definida, selecionamos _identityMap > id_ como a chave primária. Em seguida, é necessário selecionar uma namespace e a chave será pré-preenchida (abaixo do **[!UICONTROL Namespace]** campo) usando _identityMap > id_.

Ao selecionar campos, os campos de identidade primários são marcados com tags.

![](../assets/primary-identity.png)

Se precisar usar uma chave diferente, como uma ID CRM ou um endereço de email, é necessário adicioná-la manualmente:

1. Clique dentro do **[!UICONTROL Key]** campo ou no ícone de lápis.

   ![](../assets/journey16.png)

1. Selecione o campo escolhido como a chave na lista dos campos de carga. Você também pode alternar para o editor de expressões avançado para criar chaves mais complexas (por exemplo, uma concatenação de dois campos dos eventos). Veja abaixo, nesta seção.

   ![](../assets/journey20.png)

Quando o evento for recebido, o valor da chave permitirá que o sistema identifique a pessoa associada ao evento. Associada a uma namespace (consulte [esta página](../event/selecting-the-namespace.md)), a chave pode ser usada para executar query no Adobe Experience Platform. Consulte [esta página](../building-journeys/about-orchestration-activities.md).
A chave também é usada para verificar se uma pessoa está em uma jornada. Na verdade, uma pessoa não pode estar em dois lugares diferentes na mesma viagem. Como resultado, o sistema não permite que a mesma chave, por exemplo a chave CRMID=3224, esteja em diferentes locais na mesma viagem.

Você também tem acesso às funções de expressão avançadas (**[!UICONTROL Advanced mode]**) se quiser realizar manipulações adicionais. Essas funções permitem manipular os valores usados para realizar query específicos, como formatos alterados, realizar concatenações de campo, levando em conta apenas uma parte de um campo (por exemplo, os 10 primeiros caracteres). Consulte [esta página](../expression/expressionadvanced.md).
