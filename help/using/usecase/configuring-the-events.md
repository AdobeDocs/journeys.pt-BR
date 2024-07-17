---
product: adobe campaign
title: Configuração de eventos
description: Saiba como configurar os eventos para o caso de uso avançado do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 7%

---

# Configuração de eventos {#concept_sbp_5cy_w2b}

Em nosso cenário, precisamos receber um evento cada vez que uma pessoa entra no hotel Marlton e no restaurante. O **usuário técnico** precisa configurar os dois eventos que queremos que o sistema escute em nossa jornada.

Para obter informações adicionais sobre a configuração do evento, consulte [esta página](../event/about-events.md).

1. No menu superior, clique na guia **[!UICONTROL Events]** e clique em **[!UICONTROL Add]** para criar um novo evento.

   ![](../assets/journeyuc1_1.png)

1. Inserimos o nome sem espaços ou caracteres especiais: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Em seguida, selecionamos o schema e definimos a carga útil esperada para esse evento. Selecionamos os campos necessários do modelo normalizado XDM. Precisamos da ID de Experience Cloud para identificar a pessoa no banco de dados de Perfil do cliente em tempo real: &quot;endUserIDs > _experience > mcid > id&quot;.

   Também precisamos do token de registro para enviar mensagens por push: &quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   Uma ID é gerada automaticamente para esse evento. Essa ID é armazenada no campo **[!UICONTROL eventID]** (&quot;_experience > campaign > orchestration > eventID&quot;). O sistema que envia o evento não deve gerar uma ID, mas usar a disponível na pré-visualização de carga. No nosso caso de uso, essa ID é usada para identificar a localização do beacon. Cada vez que uma pessoa se aproxima do sinal de entrada, um evento será enviado contendo essa ID de evento específica. O mesmo princípio se aplica aos eventos de sinal do restaurante. Isso permite que o sistema saiba qual beacon acionou o envio do evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >A lista de campos varia de um esquema para outro. De acordo com a definição do esquema, alguns campos podem ser obrigatórios e pré-selecionados.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do schema. Você pode manter o que está pré-selecionado. Para obter mais informações sobre namespaces, consulte [esta página](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Uma chave é pré-selecionada com base nas propriedades do schema e no namespace selecionado. Você pode ficar com ele.

   ![](../assets/journeyuc2_4bis.png)

1. Clique em **[!UICONTROL Save]**.

1. Clique no ícone **[!UICONTROL View Payload]** para visualizar o conteúdo esperado pelo sistema e compartilhá-lo com a pessoa responsável pelo envio do evento.  Essa carga precisará ser configurada no postback do console de administração do Mobile Services.

   ![](../assets/journeyuc2_5.png)

Da mesma forma, crie o evento &quot;RestaurantBeacon&quot;. Seus dois eventos de beacon são criados e agora podem ser usados em nossa jornada. Agora é necessário configurar o aplicativo móvel para que ele possa enviar o conteúdo esperado para o endpoint das APIs de assimilação de streaming. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).
