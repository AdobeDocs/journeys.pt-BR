---
product: adobe campaign
solution: Journey Orchestration
title: Configurar o evento
description: Saiba como configurar o evento para o caso de uso simples da jornada
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---


# Configurar o evento{#concept_y44_hcy_w2b}

Em nosso cenário, precisamos receber um evento toda vez que uma pessoa caminha perto de um farol posicionado ao lado do spa. O usuário **** técnico precisa configurar o evento que o sistema vai ouvir em nossa jornada.

For additional information on event configuration, refer to [this page](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. Inserimos o nome sem espaços ou caracteres especiais: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Em seguida, selecionamos o schema e definimos a carga esperada para esse evento. Selecionamos os campos necessários no modelo normalizado XDM. Precisamos da ID do Experience Cloud para identificar a pessoa no banco de dados do Perfil do cliente em tempo real: _endUserIDs > experience > mcid > id_. Uma ID é gerada automaticamente para este evento. Essa ID é armazenada no **[!UICONTROL eventID]** campo (_experiência > campanha > orquestração > eventID_). O sistema que envia o evento não deve gerar uma ID; ele deve usar a que está disponível na pré-visualização de carga. Em nosso caso de uso, essa ID é usada para identificar a localização do beacon. Cada vez que uma pessoa caminha perto do beacon spa, um evento será enviado contendo essa ID de evento específica. Isso permite que o sistema saiba qual sinal disparou o envio do evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >A lista dos campos varia de um schema para outro. De acordo com a definição do schema, alguns campos podem ser obrigatórios e pré-selecionados.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do schema. Você pode manter o que está pré-selecionado. For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Uma tecla é pré-selecionada com base nas propriedades do schema e na namespace selecionada. Você pode ficar com ele.

   ![](../assets/journeyuc1_5.png)

1. Clique em **[!UICONTROL Save]**.

1. Clique no **[!UICONTROL View Payload]** ícone para pré-visualização da carga esperada pelo sistema e compartilhá-la com a pessoa responsável pelo envio do evento. Essa carga precisará ser configurada no postback do console de administração do Mobile Services.

   ![](../assets/journeyuc1_7.png)

   O evento está pronto para ser usado em sua jornada. Agora é necessário configurar o aplicativo móvel para que ele possa enviar a carga esperada para o ponto de extremidade das APIs de ingestão de transmissão. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).