---
product: adobe campaign
solution: Journey Orchestration
title: Definir campos de carga
description: Saiba mais sobre como definir os campos de carga
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 6%

---


# Definir campos de carga {#concept_yrw_3qt_52b}

A definição de carga permite escolher as informações que o sistema espera receber do evento em sua jornada e a chave para identificar qual pessoa está associada ao evento. A carga é baseada na definição do campo Experience Cloud XDM. Para obter mais informações sobre XDM, consulte [esta página](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html).

1. Selecione um esquema XDM na lista e clique no campo **[!UICONTROL Payload]** ou no ícone **[!UICONTROL Edit]**.

   ![](../assets/journey8.png)

   Todos os campos definidos no schema são exibidos. A lista de campos varia de um schema para outro. Você pode pesquisar um campo específico ou usar os filtros para exibir todos os nós e campos ou somente os campos selecionados. De acordo com a definição do schema, alguns campos podem ser obrigatórios e pré-selecionados. Não é possível desmarcá-los. Todos os campos obrigatórios para o evento ser recebido corretamente pelo Journey Orchestration são selecionados por padrão.

   >[!NOTE]
   >
   >Certifique-se de ter adicionado o mixin &quot;orquestration&quot; ao esquema XDM. Isso garantirá que o esquema contenha todas as informações necessárias para funcionar com [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Selecione os campos que você espera receber do evento. Esses são os campos que o usuário empresarial aproveitará na jornada. Eles também devem incluir a chave que será usada para identificar a pessoa associada ao evento (consulte [esta página](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Para eventos gerados pelo sistema, o campo **[!UICONTROL eventID]** é adicionado automaticamente na lista de campos selecionados para que [!DNL Journey Orchestration] possa identificar o evento. O sistema que envia o evento não deve gerar uma ID, mas deve usar a disponível na pré-visualização de carga. Consulte [esta página](../event/previewing-the-payload.md).

1. Quando terminar de selecionar os campos necessários, clique em **[!UICONTROL Save]** ou pressione **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   O número de campos selecionados aparece no campo **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
