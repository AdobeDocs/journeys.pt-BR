---
title: Sobre eventos
description: Saiba como configurar um evento
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 76%

---


# Sobre eventos {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Sobre eventos"
>abstract="Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

Essa configuração é **obrigatória**[!DNL Journey Orchestration], pois o foi projetado para acompanhar eventos, sempre executada por um **usuário técnico**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. Você pode usar vários eventos (em diferentes etapas de uma jornada) e várias jornadas podem usar o mesmo evento.

Se você editar um evento usado em um rascunho ou em uma jornada ao vivo, será possível apenas alterar o nome, a descrição ou adicionar campos de carga útil. Limitamos rigorosamente a edição de rascunho ou jornadas ao vivo para evitar a quebra de jornadas.

## Princípio geral {#section_r1f_xqt_pgb}

Eventos são chamadas POST API. Os eventos são enviados para a plataforma de dados da Adobe Experience Cloud por meio de APIs de assimilação de fluxo. O destino do URL de eventos enviados por meio de APIs de mensagens transacionais é chamado de &quot;inlet&quot;. A carga útil de eventos segue a formatação XDM.

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). Há dois modos para a assimilação de fluxo, autenticados e não autenticados. Para obter detalhes sobre as APIs de assimilação de fluxo, consulte [este link](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/api/getting-started.html).

Após chegar através das APIs de assimilação de fluxo contínuo, os eventos fluem para um serviço interno chamado Pipeline e, em seguida, para a Plataforma de dados. Se o schema do evento tiver o sinalizador de Serviço de perfil do cliente em tempo real ativado e uma ID de conjunto de dados que também tenha o sinalizador de Perfil do cliente em tempo real, ele fluirá para o Serviço de perfil do cliente em tempo real.

The Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.

## Criar um novo evento {#section_tbk_5qt_pgb}

Estas são as etapas principais para configurar um novo evento:

1. No menu superior, clique na guia **[!UICONTROL Events]**. A lista dos eventos é exibida. Consulte [](../about/user-interface.md) para obter mais informações sobre a interface.

   ![](../assets/journey5.png)

1. Clique em **[!UICONTROL Add]** para criar um novo evento. O painel de configuração do evento é aberto no lado direito da tela.

   ![](../assets/journey6.png)

1. Digite um nome para o evento.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição ao evento. Esta etapa é opcional.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. Você poderá então usar essas informações em sua jornada. Consulte [](../event/defining-the-payload-fields.md).
1. O número de jornadas que usam esse evento é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no ícone **[!UICONTROL View journeys]** para exibir a lista de jornadas usando esse evento.
1. Adicione um namespace. Esta etapa é opcional, mas é recomendada, pois a adição de namespace permite que você aproveite as informações armazenadas no Serviço de perfil do cliente em tempo real. Ela define o tipo de chave que o evento tem. Consulte [](../event/selecting-the-namespace.md).
1. Defina a chave: escolha um campo a partir dos campos de carga útil ou defina uma fórmula para identificar a pessoa associada ao evento. Essa chave é configurada automaticamente (mas ainda pode ser editada) se você selecionar um namespace. Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). Consulte [](../event/defining-the-event-key.md).
1. Adicione uma condição. Esta etapa é opcional. Ela permite que o sistema processe apenas os eventos que atendem à condição. A condição só pode ter como base as informações contidas no evento. Consulte [](../event/adding-a-condition.md).
1. Clique em **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   Agora o evento está configurado e pronto para ser lançado em uma jornada. Etapas de configuração adicionais são necessárias para receber eventos. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
