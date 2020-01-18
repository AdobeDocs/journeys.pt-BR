---
title: Definição dos campos de carga
description: Saiba mais sobre como definir os campos de carga
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


# Definição dos campos de carga {#concept_yrw_3qt_52b}

A definição da carga permite escolher as informações que o sistema espera receber do evento em sua jornada e a chave para identificar qual pessoa está associada ao evento. A carga é baseada na definição do campo XDM da Experience Cloud. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Selecione um esquema XDM na lista e clique no **[!UICONTROL Payload]**campo ou no**[!UICONTROL Edit]** ícone.

   ![](../assets/journey8.png)

   Todos os campos definidos no esquema são exibidos. A lista de campos varia de um esquema para outro. Você pode pesquisar por um campo específico ou usar os filtros para exibir todos os nós e campos ou apenas os campos selecionados. De acordo com a definição do esquema, alguns campos podem ser obrigatórios e pré-selecionados. Não é possível desmarcá-los.

   >[!NOTE]
   >
   >Certifique-se de ter adicionado a mistura &quot;orquestração&quot; ao esquema XDM. Isso garantirá que seu esquema contenha todas as informações necessárias para trabalhar com o Journey Orchestration.

   ![](../assets/journey9.png)

1. Selecione os campos que você espera receber do evento. Estes são os campos que o usuário do negócio vai aproveitar na jornada. Eles também devem incluir a chave que será usada para identificar a pessoa associada ao evento (consulte [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >O **[!UICONTROL eventID]**campo é adicionado automaticamente na lista de campos selecionados para que o Journey Orchestration possa identificar o evento. O sistema que envia o evento não deve gerar uma ID; ele deve usar a disponível na visualização da carga. Consulte[](../event/previewing-the-payload.md).

1. Quando terminar de selecionar os campos necessários, clique **[!UICONTROL Save]**ou pressione**[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   O número de campos selecionados é exibido no **[!UICONTROL Payload]**campo.

   ![](../assets/journey12.png)
