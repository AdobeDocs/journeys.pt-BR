---
title: Configurar os eventos
description: Saiba como configurar os eventos para o caso de uso avançado da jornada
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
source-git-commit: db16f947e8c885167d289484cc2269dcee3bd646
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---


# Configurar os eventos {#concept_sbp_5cy_w2b}

Em nosso cenário, precisamos receber um evento toda vez que uma pessoa entra no hotel Marlton e no restaurante. O usuário **** técnico precisa configurar os dois eventos que queremos que o sistema escute em nossa jornada.

Para obter informações adicionais sobre a configuração do evento, consulte [](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. Inserimos o nome sem espaços ou caracteres especiais: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Em seguida, selecionamos o schema e definimos a carga esperada para esse evento. Selecionamos os campos necessários no modelo normalizado XDM. Precisamos da ID do Experience Cloud para identificar a pessoa no banco de dados do Perfil do cliente em tempo real: &quot;endUserIDs > _experience > mcid > id&quot;.

   Também precisamos do token de registro para enviar mensagens de push: &quot;_experience > campanha > mensagem > perfil > pushNotificationTokens > token&quot;

   Uma ID é gerada automaticamente para este evento. Essa ID é armazenada no **[!UICONTROL eventID]** campo (&quot;_experience > campanha > orquestração > eventID&quot;). O sistema que envia o evento não deve gerar uma ID; ele deve usar a que está disponível na pré-visualização de carga. Em nosso caso de uso, essa ID é usada para identificar a localização do beacon. Cada vez que uma pessoa caminha perto do beacon do lobby, um evento será enviado contendo essa ID de evento específica. O mesmo princípio se aplica aos eventos de beacon do restaurante. Isso permite que o sistema saiba qual sinal disparou o envio do evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >A lista dos campos varia de um schema para outro. De acordo com a definição do schema, alguns campos podem ser obrigatórios e pré-selecionados.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do schema. Você pode manter o que está pré-selecionado. Para obter mais informações sobre namespaces, consulte [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Uma tecla é pré-selecionada com base nas propriedades do schema e na namespace selecionada. Você pode ficar com ele.

   ![](../assets/journeyuc2_4bis.png)

1. Clique em **[!UICONTROL Save]**.

1. Clique no **[!UICONTROL View Payload]** ícone para pré-visualização da carga esperada pelo sistema e compartilhá-la com a pessoa responsável pelo envio do evento.  Essa carga precisará ser configurada no postback do console de administração do Mobile Services.

   ![](../assets/journeyuc2_5.png)

Da mesma forma, crie o evento &quot;RestaurantBeacon&quot;. Seus dois eventos de beacon são criados e agora podem ser usados em nossa jornada. Agora é necessário configurar o aplicativo móvel para que ele possa enviar a carga esperada para o ponto de extremidade das APIs de ingestão de transmissão. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
