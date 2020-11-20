---
product: adobe campaign
solution: Journey Orchestration
title: Sobre eventos
description: Saiba como configurar um evento
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 98%

---


# Sobre eventos {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Sobre eventos"
>abstract="Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). É o que o [!DNL Journey Orchestration] escutará nas jornadas para orquestrar as melhores ações futuras."

Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). É o que o [!DNL Journey Orchestration] escutará nas jornadas para orquestrar as melhores ações futuras.

Essa configuração é **obrigatória**, pois o [!DNL Journey Orchestration] foi projetado para acompanhar eventos e sempre ser executado por um **usuário técnico**.

A configuração do evento permite definir as informações que o [!DNL Journey Orchestration] receberá como eventos. Você pode usar vários eventos (em diferentes etapas de uma jornada) e várias jornadas podem usar o mesmo evento.

Se você editar um evento usado em um rascunho ou em uma jornada ao vivo, será possível apenas alterar o nome, a descrição ou adicionar campos de carga útil. Limitamos rigorosamente a edição de rascunho ou jornadas ao vivo para evitar a quebra de jornadas.

## Princípio geral {#section_r1f_xqt_pgb}

Eventos são chamadas POST API. Os eventos são enviados para a Adobe Experience Platform por meio de APIs de assimilação de streaming. O destino do URL de eventos enviados por meio de APIs de mensagens transacionais é chamado de &quot;inlet&quot;. A carga útil de eventos segue a formatação XDM.

O payload contém informações necessárias para que as APIs de assimilação de streaming funcionem (no cabeçalho) e as informações necessárias para que o [!DNL Journey Orchestration] funcione (a ID do evento, parte do corpo do payload útil) e as informações que serão usadas em jornadas (no corpo, por exemplo, o valor total de um carrinho abandonado). Há dois modos para a assimilação de fluxo, autenticados e não autenticados. Para obter detalhes sobre as APIs de assimilação de fluxo, consulte [este link](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/api/getting-started.html).

Após a chegada através das APIs de assimilação de streaming, os eventos fluem para um serviço interno chamado Pipeline e, em seguida, para a Adobe Experience Platform. Se o schema do evento tiver o sinalizador de Serviço de perfil do cliente em tempo real ativado e uma ID de conjunto de dados que também tenha o sinalizador de Perfil do cliente em tempo real, ele fluirá para o Serviço de perfil do cliente em tempo real.

O Pipeline filtra os eventos que têm um payload contendo [!DNL Journey Orchestration] eventIDs (consulte o processo de criação de eventos abaixo) fornecidos pelo [!DNL Journey Orchestration] e contidos no payload do evento. Esses eventos são acompanhados pelo [!DNL Journey Orchestration] e a jornada correspondente é acionada.

## Criar um novo evento {#section_tbk_5qt_pgb}

Estas são as etapas principais para configurar um novo evento:

1. No menu superior, clique na guia **[!UICONTROL Events]**. A lista dos eventos é exibida. Refer to [this page](../about/user-interface.md) for more information on the interface.

   ![](../assets/journey5.png)

1. Clique em **[!UICONTROL Add]** para criar um novo evento. O painel de configuração do evento é aberto no lado direito da tela.

   ![](../assets/journey6.png)

1. Digite um nome para o evento.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição ao evento. Esta etapa é opcional.
1. Defina os campos schema e payload: é aqui que você seleciona as informações do evento (normalmente chamadas de payload) que o [!DNL Journey Orchestration] espera receber. Você poderá então usar essas informações em sua jornada. Consulte [esta página](../event/defining-the-payload-fields.md).
1. O número de jornadas que usam esse evento é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no ícone **[!UICONTROL View journeys]** para exibir a lista de jornadas usando esse evento.
1. Adicione um namespace. Esta etapa é opcional, mas é recomendada, pois a adição de namespace permite que você aproveite as informações armazenadas no Serviço de perfil do cliente em tempo real. Ela define o tipo de chave que o evento tem. Consulte [esta página](../event/selecting-the-namespace.md).
1. Defina a chave: escolha um campo a partir dos campos de carga útil ou defina uma fórmula para identificar a pessoa associada ao evento. Essa chave é configurada automaticamente (mas ainda pode ser editada) se você selecionar um namespace. Na verdade, o [!DNL Journey Orchestration] escolhe a chave que deve corresponder ao namespace (por exemplo, se você selecionar um namespace de email, a chave de email será selecionada). Consulte [esta página](../event/defining-the-event-key.md).
1. Adicione uma condição. Esta etapa é opcional. Ela permite que o sistema processe apenas os eventos que atendem à condição. A condição só pode ter como base as informações contidas no evento. Consulte [esta página](../event/adding-a-condition.md).
1. Clique em **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   Agora o evento está configurado e pronto para ser lançado em uma jornada. Etapas de configuração adicionais são necessárias para receber eventos. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).
