---
product: adobe campaign
solution: Journey Orchestration
title: Aproveitar pontuações de fadiga
description: Saiba como aproveitar as pontuações de fadiga no jornada
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---


# Envio de uma mensagem usando Campaign Classic {#campaign-classic-use-case}

Esse caso de uso apresenta todas as etapas necessárias para enviar um email usando a integração do Adobe Campaign Classic.

Primeiro, criaremos um template de email transacional no Campaign Classic. Em seguida, no Journey Orchestration, criaremos o evento, a ação e projetaremos a jornada.

Para saber mais sobre a integração do Campaign Classic, consulte estas páginas:

* [Criação de uma Campaign Classic action](../action/acc-action.md)
* [Usar a ação em uma jornada](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign Classic**

Sua instância do Campaign Classic precisa ser provisionada para essa integração. O recurso Mensagens transacionais precisa ser configurado.

1. Faça logon na instância de controle do Campaign Classic.

1. Em **Administration** > **Platform** > **Enumerations**, selecione a enumeração **Event type** (eventType). Crie um novo tipo de evento (&quot;jornada-evento&quot;, no nosso exemplo). Você precisará usar o nome interno do tipo de evento ao gravar o arquivo JSON posteriormente.

   ![](../assets/accintegration-uc-1.png)

1. Desconecte e reconecte à instância para que a criação seja efetiva.

1. Em **Message Center** > **Transactional message templates**, crie um novo template de email com base no tipo de evento criado anteriormente.

   ![](../assets/accintegration-uc-2.png)

1. Projete seu modelo. Neste exemplo, usamos personalização no nome do perfil e no número do pedido. O primeiro nome está na fonte de dados do Adobe Experience Platform e o número do pedido é um campo do evento do Journey Orchestration. Certifique-se de usar os nomes de campo corretos no Campaign Classic.

   ![](../assets/accintegration-uc-3.png)

1. Publique seu template transacional.

   ![](../assets/accintegration-uc-4.png)

1. Agora, é necessário gravar a carga JSON correspondente ao modelo.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* Para o canal, é necessário digitar &quot;email&quot;.
* Para eventType, use o nome interno do tipo de evento criado anteriormente.
* O endereço de email será uma variável, portanto, você pode digitar qualquer rótulo.
* Em ctx, os campos de personalização também são variáveis.

**Journey Orchestration**

1. Primeiro, você precisa criar um evento . Certifique-se de incluir o campo &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. Em seguida, é necessário criar, no Journey Orchestration, uma ação correspondente ao seu template Campaign Classic. Na lista suspensa **Action type**, selecione **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Clique no campo **Carga** e cole o JSON criado anteriormente.

   ![](../assets/accintegration-uc-7.png)

1. Para o endereço de email e os dois campos de personalização, altere **Constant** para **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Agora crie uma nova jornada e comece com o evento criado anteriormente.

   ![](../assets/accintegration-uc-9.png)

1. Adicione a ação e mapeie cada campo para o campo correto no Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Adicione uma atividade **End** e teste sua jornada.

   ![](../assets/accintegration-uc-11.png)

1. Agora você pode publicar sua jornada.
