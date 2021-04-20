---
product: adobe campaign
solution: Journey Orchestration
title: Construir a jornada
description: 'Saiba como criar a jornada de casos de uso avançado '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 91%

---


# Construir a jornada {#concept_owm_kdy_w2b}

Agora o **usuário empresarial** pode criar a jornada. Nossa jornada incluirá as seguintes atividades:

* duas atividades **[!UICONTROL Event]**: “LobbyBeacon” e “RestaurantBeacon”
* duas atividades **[!UICONTROL Condition]**
* três atividades **[!UICONTROL Push]** e uma atividade **[!UICONTROL Email]** (usando o Adobe Campaign Standard)
* uma atividade **[!UICONTROL Wait]**
* quatro atividades **[!UICONTROL End]**

>[!NOTE]
>
>As atividades **[!UICONTROL Push]** e **[!UICONTROL Email]** só estarão disponíveis na paleta se você tiver o Adobe Campaign Standard.

Para obter informações adicionais sobre como criar uma jornada, consulte [esta página](../building-journeys/journey.md).

## Primeiros passos{#section_ntb_ws1_ffb}

1. No menu superior, clique na guia **[!UICONTROL Home]** e **[!UICONTROL Create]** para criar uma nova jornada.

   ![](../assets/journey31.png)

1. Edite as propriedades da jornada no painel de configuração exibido no lado direito. Adicione um nome e defina a duração de um mês, de 1º a 31 de dezembro.

   ![](../assets/journeyuc2_12.png)

1. Inicie a criação da jornada arrastando e soltando o evento “LobbyBeacon” da paleta para a tela. Você também pode dar um duplo clique no evento da paleta para adicioná-lo à tela.

   ![](../assets/journeyuc2_13.png)

1. Agora vamos adicionar uma condição para verificar se a pessoa não foi contatada nas últimas 24 horas e se é um membro de fidelidade. Arraste e solte uma atividade de condição na sua jornada.

   ![](../assets/journeyuc2_14.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e clique no campo **[!UICONTROL Expression]**. Você também pode definir um rótulo de condição que aparecerá na seta sobre a tela. Em nosso exemplo, substituímos “Condição 1” por “Membro de fidelidade”.

   ![](../assets/journeyuc2_15.png)

1. Clique em **[!UICONTROL Advanced mode]** e defina a seguinte condição com base nos campos “data e hora” e “directMarketing.send.value” provenientes da fonte de dados da Adobe Experience Platform. A sintaxe da expressão é:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. Clique no botão **[!UICONTROL Add a path]** e crie um segundo caminho para clientes que não foram contatados nas últimas 24 horas e que não são membros do programa de fidelidade. Nomeie o caminho “Não é membro do programa de fidelidade”. A sintaxe da expressão é:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >Na segunda parte da expressão, o “Perfil” é opcional.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do schema. Você pode manter o que está pré-selecionado. Para obter mais informações sobre namespaces, consulte [esta página](../event/selecting-the-namespace.md).

No nosso caso, só queremos reagir a essas duas condições, então não marcamos a caixa **[!UICONTROL Show path for other cases than the one(s) above]**.

Dois caminhos são criados após sua condição:

* _Clientes que não tenham sido contatados nas últimas 24 horas e que sejam membros do programa de fidelidade._
* _Clientes que não tenham sido contatados nas últimas 24 horas e que sejam membros do programa de fidelidade._

![](../assets/journeyuc2_16.png)

## Primeiro caminho: o cliente é um membro do programa de fidelidade {#section_otb_ws1_ffb}

1. No primeiro caminho, vamos adicionar uma condição para verificar se ele tem uma reserva. Arraste e solte uma atividade de condição na sua jornada.

   ![](../assets/journeyuc2_17.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e defina a condição com base nas informações de status da reserva recuperadas do sistema de reservas:

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. Quando um campo de uma fonte de dados externa é selecionado, a parte direita da tela exibe a lista de parâmetros que foram definidos ao configurar a fonte de dados externa (consulte [this page](../usecase/configuring-the-data-sources.md)). Clique no nome do parâmetro e defina o valor da chave do sistema de reservas, a Experience Cloud ID, em nosso exemplo:

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. Como também queremos reagir a clientes que não têm uma reserva, precisamos marcar a caixa **[!UICONTROL Show path for other cases than the one(s) above]**.

   ![](../assets/journeyuc2_20.png)

   Dois caminhos são criados:

   * _Clientes que reservaram um quarto_
   * _Clientes que não reservaram um quarto._

   ![](../assets/journeyuc2_21.png)

1. No primeiro caminho (quarto reservado), solte uma atividade **[!UICONTROL Push]**, selecione seu aplicativo móvel e seu modelo de “Boas-vindas”.

   ![](../assets/journeyuc2_22.png)

1. Defina os campos **[!UICONTROL Target]** exigidos pelo sistema para enviar o push.

   * **[!UICONTROL Push platform]**: selecione a plataforma: **[!UICONTROL Apple Push Notification Server]** (Apple) ou **[!UICONTROL Firebase Cloud Messaging]** (Android).
   * **[!UICONTROL Registration token]**: adicione a seguinte expressão (com base no evento configurado) usando o modo avançado:

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ```

1. Defina os campos de personalização de notificação por push. Em nosso exemplo: nome e sobrenome.

1. Adicione um evento “RestaurantBeacon”.

   ![](../assets/journeyuc2_23.png)

1. Adicione uma nova atividade **[!UICONTROL Push]**, selecione o modelo “Desconto de refeição” e defina os campos **[!UICONTROL Address]** e **[!UICONTROL Personalization]**. Adicione uma atividade **[!UICONTROL End]**. 

   ![](../assets/journeyuc2_24.png)

1. Queremos enviar uma notificação por push de desconto para refeições somente se a pessoa entrar no restaurante nas próximas 6 horas após o push de boas-vindas. Para isso, precisamos usar uma atividade de espera. Coloque o cursor na atividade de push de boas-vindas e clique no símbolo “+”. No novo caminho, adicione uma atividade de espera e defina uma duração de 6 horas. A primeira atividade elegível será escolhida. Se o evento do restaurante for recebido menos de 6 horas após o push de boas-vindas, a atividade de push será enviada. Se nenhum evento de restaurante for recebido dentro das próximas 6 horas, a espera será escolhida. Coloque uma atividade **[!UICONTROL End]** após a atividade de espera.

   ![](../assets/journeyuc2_31.png)

1. No segundo caminho após a condição de reserva (nenhum quarto reservado), adicione uma atividade **[!UICONTROL Push]** e selecione o modelo “Tarifas de quartos”. Adicione uma atividade **[!UICONTROL End]**. 

   ![](../assets/journeyuc2_25.png)

## Segundo caminho: o cliente não é um membro do programa de fidelidade{#section_ptb_ws1_ffb}

1. No segundo caminho após a primeira condição (o cliente não é um membro do programa de fidelidade), adicione uma atividade **[!UICONTROL Email]** e selecione seu modelo de “categoria de fidelidade”.

   ![](../assets/journeyuc2_26.png)

1. No campo **[!UICONTROL Address]**, selecione o endereço de email da fonte de dados.

   ![](../assets/journeyuc2_27.png)

1. Defina os campos de personalização de nome e sobrenome a partir da fonte de dados.

   ![](../assets/journeyuc2_28.png)

1. Adicione uma atividade **[!UICONTROL End]**. 

Clique no botão de alternância **[!UICONTROL Test]** e teste sua jornada. Se houver algum erro, desative o modo de teste, modifique sua jornada e teste novamente. Para obter mais informações sobre o modo de teste, consulte [esta página](../building-journeys/testing-the-journey.md).

![](../assets/journeyuc2_32bis.png)

Quando o teste for conclusivo, você pode publicar sua jornada pelo menu suspenso no canto superior direito.

![](../assets/journeyuc2_32.png)
