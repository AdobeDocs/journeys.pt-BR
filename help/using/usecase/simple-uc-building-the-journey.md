---
title: Construir a jornada
description: Saiba como criar uma viagem de caso de uso simples
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 43%

---


# Construir a jornada{#concept_eyw_mcy_w2b}

Agora o **usuário empresarial** pode criar a jornada. Nossa jornada incluirá apenas um caminho com as seguintes atividades:

* o &quot;SpaBeacon&quot; **[!UICONTROL Event]**: quando uma pessoa caminha perto do spa beacon, o sistema receberá um evento e a viagem será start para essa pessoa.
* uma **[!UICONTROL Condition]** atividade para verificar se a pessoa é uma mulher
* uma **[!UICONTROL Email]** atividade (usando o Adobe Campaign Standard)
* uma atividade **[!UICONTROL End]**

>[!NOTE]
>
>As atividades **[!UICONTROL Push]** e **[!UICONTROL Email]** só estarão disponíveis na paleta se você tiver o Adobe Campaign Standard.

Para obter informações adicionais sobre como criar uma jornada, consulte [](../building-journeys/journey.md).

1. No menu superior, clique na guia **[!UICONTROL Home]** e **[!UICONTROL Create]** para criar uma nova jornada.

   ![](../assets/journey31.png)

1. Edite as propriedades da jornada no painel de configuração exibido no lado direito. Nós o chamamos de &quot;Viagem Spa&quot; e a definimos para durar um mês, do 1º ao 31º de dezembro.

   ![](../assets/journeyuc1_8.png)

1. Start desenhando sua jornada arrastando e soltando o evento &quot;SpaBeacon&quot; da paleta para a tela. Você também pode dar um duplo clique no evento da paleta para adicioná-lo à tela.

   ![](../assets/journeyuc1_9.png)

1. Agora vamos adicionar uma condição para verificar se a pessoa é uma mulher. Arraste e solte uma atividade de condição na sua jornada.

   ![](../assets/journeyuc1_10.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e clique no campo **[!UICONTROL Expression]**. Você também pode definir um rótulo de condição que aparecerá na seta sobre a tela.

   ![](../assets/journeyuc1_11.png)

1. Usando o editor de expressões simples, procure o campo de gênero (_pessoa > gênero_) e solte-o à direita para criar a seguinte condição: &quot;O gênero é igual a &quot;Mulher&quot;.

   ![](../assets/journeyuc1_12.png)

1. Solte uma **[!UICONTROL Email]** atividade e selecione seu modelo de mensagem transacional de &quot;Desconto do Spa&quot;. Este modelo foi projetado usando o Adobe Campaign. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Click inside the **[!UICONTROL Email]** field and select the email address from the data source.

   ![](../assets/journeyuc1_14.png)

1. Da mesma forma, defina os campos de personalização de nome e sobrenome da fonte de dados.

   ![](../assets/journeyuc1_15.png)

1. Solte uma **[!UICONTROL End]** atividade.

   ![](../assets/journeyuc1_17.png)

1. Clique na opção de **[!UICONTROL Test]** alternar e teste sua jornada usando perfis de teste. Se houver algum erro, desative o modo de teste, modifique sua jornada e teste novamente. Para obter mais informações sobre o modo de teste, consulte [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Quando o teste for conclusivo, você pode publicar sua jornada pelo menu suspenso no canto superior direito.

   ![](../assets/journeyuc1_18.png)

Na próxima vez que uma mulher caminhar perto do beacon spa, ela receberá imediatamente um e-mail personalizado com &quot;desconto spa&quot;.
