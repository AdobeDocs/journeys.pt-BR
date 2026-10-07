---
product: adobe campaign
title: Configuração do evento
description: Saiba como configurar o evento para o caso de uso simples do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 20%
---
# Configuração do evento{#concept_y44_hcy_w2b}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


Em nosso cenário, precisamos receber um evento sempre que uma pessoa caminhar perto de um beacon posicionado ao lado do spa. O **usuário técnico** precisa configurar o evento que o sistema ouvirá em nossa jornada.

Para obter informações adicionais sobre a configuração do evento, consulte [esta página](../event/about-events.md).

1. No menu superior, clique na guia **[!UICONTROL Events]** e clique em **[!UICONTROL Add]** para criar um novo evento.

   ![](../assets/journeyuc1_1.png)

1. Inserimos o nome sem espaços ou caracteres especiais: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Em seguida, selecionamos o schema e definimos a carga útil esperada para esse evento. Selecionamos os campos necessários do modelo normalizado XDM. Precisamos da Experience Cloud ID para identificar a pessoa no banco de dados de Perfil do Cliente em Tempo Real: _endUserIDs > experiência > mcid > id_. Uma ID é gerada automaticamente para esse evento. Esta ID está armazenada no campo **[!UICONTROL eventID]** (_experiência > campanha > orquestração > eventID_). O sistema que envia o evento não deve gerar uma ID, mas usar a disponível na pré-visualização de carga. No nosso caso de uso, essa ID é usada para identificar a localização do beacon. Cada vez que uma pessoa se aproxima do sinal de spa, um evento será enviado contendo essa ID de evento específica. Isso permite que o sistema saiba qual beacon acionou o envio do evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >A lista de campos varia de um esquema para outro. De acordo com a definição do esquema, alguns campos podem ser obrigatórios e pré-selecionados.

1. Precisamos selecionar um namespace. Um namespace é pré-selecionado com base nas propriedades do esquema. Você pode manter o que está pré-selecionado. Para obter mais informações sobre namespaces, consulte [esta página](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Uma chave é pré-selecionada com base nas propriedades do schema e no namespace selecionado. Você pode ficar com ele.

   ![](../assets/journeyuc1_5.png)

1. Clique em **[!UICONTROL Save]**.

1. Clique no ícone **[!UICONTROL View Payload]** para visualizar o conteúdo esperado pelo sistema e compartilhá-lo com a pessoa responsável pelo envio do evento. Essa carga precisará ser configurada no postback do console de administração do Mobile Services.

   ![](../assets/journeyuc1_7.png)

   O evento está pronto para ser usado na jornada. Agora é necessário configurar o aplicativo móvel para que ele possa enviar o conteúdo esperado para o endpoint das APIs de assimilação de streaming. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).
