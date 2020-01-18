---
title: Configuração do evento
description: Saiba como configurar o evento para o caso de uso simples da jornada
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


# Configuração do evento{#concept_y44_hcy_w2b}

Em nosso cenário, precisamos receber um evento toda vez que uma pessoa caminha perto de um farol posicionado ao lado do spa. O usuário **** técnico precisa configurar o evento que o sistema vai ouvir em nossa jornada.

Para obter informações adicionais sobre a configuração do evento, consulte [](../event/about-events.md).

1. No menu superior, clique na **[!UICONTROL Events]**guia e clique em**[!UICONTROL Add]** para criar um novo evento.

   ![](../assets/journeyuc1_1.png)

1. Inserimos o nome sem espaços ou caracteres especiais: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. Em seguida, selecionamos o esquema e definimos a carga esperada para esse evento. Selecionamos os campos necessários no modelo normalizado XDM. Precisamos da Experience Cloud ID para identificar a pessoa no banco de dados de Perfil do cliente em tempo real: _endUserIDs > experience > mcid > id_. Uma ID é gerada automaticamente para esse evento. Essa ID é armazenada no **[!UICONTROL eventID]**campo (_experiência > campanha > orquestração > eventID_). O sistema que envia o evento não deve gerar uma ID; ele deve usar a disponível na visualização da carga. Em nosso caso de uso, essa ID é usada para identificar a localização do beacon. Cada vez que uma pessoa caminha perto do beacon spa, um evento será enviado contendo essa ID de evento específica. Isso permite que o sistema saiba qual sinal disparou o envio do evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >A lista de campos varia de um esquema para outro. De acordo com a definição do esquema, alguns campos podem ser obrigatórios e pré-selecionados.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do esquema. Você pode manter aquele pré-selecionado. Para obter mais informações sobre namespaces, consulte [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Uma tecla é pré-selecionada com base nas propriedades do esquema e no namespace selecionado. Você pode ficar com ele.

   ![](../assets/journeyuc1_5.png)

1. Clique em **[!UICONTROL Save]**.

1. Clique no **[!UICONTROL View Payload]**ícone para visualizar a carga esperada pelo sistema e compartilhá-la com a pessoa responsável pelo envio do evento. Essa carga precisará ser configurada no postback do console de administração do Mobile Services.

   ![](../assets/journeyuc1_7.png)

   O evento está pronto para ser usado em sua jornada. Agora é necessário configurar o aplicativo móvel para que ele possa enviar a carga esperada para o ponto de extremidade das APIs de ingestão de transmissão. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).