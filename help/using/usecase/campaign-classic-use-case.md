---
product: adobe campaign
solution: Journey Orchestration
title: Envio de uma mensagem usando o Campaign v7/v8
description: Envio de uma mensagem usando o Campaign v7/v8
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 17%
---
# Envio de uma mensagem usando o Campaign v7/v8 {#campaign-classic-use-case}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


Esse caso de uso apresenta todas as etapas necessárias para enviar um email usando a integração com o Adobe Campaign Classic v7 e o Adobe Campaign v8.

Primeiro, criaremos um template de email transacional no Campaign. Em seguida, no Journey Orchestration, criaremos o evento, a ação e projetaremos a jornada.

Para saber mais sobre a integração do Campaign, consulte estas páginas:

* [Criar uma ação de campanha](../action/acc-action.md)
* [Usando a ação em uma jornada](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

A instância do Campaign precisa ser provisionada para essa integração. O recurso de mensagens transacionais precisa ser configurado.

1. Faça logon na instância de controle do Campaign.

1. Em **Administração** > **Plataforma** > **Enumerações**, selecione a enumeração **Tipo de evento** (eventType). Crie um novo tipo de evento (&quot;jornada-evento&quot;, em nosso exemplo). Posteriormente, você terá que usar o nome interno do tipo de evento ao gravar o arquivo JSON.

   ![](../assets/accintegration-uc-1.png)

1. Desconecte e reconecte à instância para que a criação seja efetiva.

1. Em **Centro de Mensagens** > **Modelos de mensagens transacionais**, crie um novo modelo de email com base no tipo de evento criado anteriormente.

   ![](../assets/accintegration-uc-2.png)

1. Projete seu modelo. Neste exemplo, usamos personalização no nome do perfil e no número do pedido. O nome está na fonte de dados do Adobe Experience Platform e o número do pedido é um campo do evento do Journey Orchestration. Use os nomes de campo corretos no Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publique seu template transacional.

   ![](../assets/accintegration-uc-4.png)

1. Agora é necessário gravar a carga JSON correspondente ao modelo.

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
* O endereço de email será uma variável, para que você possa digitar qualquer rótulo.
* No ctx, os campos de personalização também são variáveis.

**Journey Orchestration**

1. Primeiro, é necessário criar um evento. Inclua o campo &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. Em seguida, é necessário criar, no Journey Orchestration, uma ação correspondente ao seu template de Campanha. No menu suspenso **Tipo de ação**, selecione **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Clique no **campo de carga** e cole o JSON criado anteriormente.

   ![](../assets/accintegration-uc-7.png)

1. Para o endereço de email e os dois campos de personalização, altere **Constante** para **Variável**.

   ![](../assets/accintegration-uc-8.png)

1. Agora crie uma nova jornada e comece com o evento criado anteriormente.

   ![](../assets/accintegration-uc-9.png)

1. Adicione a ação e mapeie cada campo para o campo correto no Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Adicione uma atividade **End** e teste sua jornada.

   ![](../assets/accintegration-uc-11.png)

1. Agora você pode publicar sua jornada.
