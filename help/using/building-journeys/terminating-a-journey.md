---
product: adobe campaign
title: Encerrar uma jornada
description: Saiba como finalizar uma jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 2d1b9d6b-0a53-436c-b251-ce77cb931aaa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---

# Encerrar uma jornada


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


As opções **[!UICONTROL Stop]** e **[!UICONTROL Close to new entrances]** permitem encerrar as jornadas **live**. O fechamento de uma jornada envolve **que a chegada de novos clientes à jornada está bloqueada** e que os clientes que já entraram na jornada podem experimentá-la até o fim. Essa é a maneira mais recomendada de colocar um fim em uma jornada, pois oferece a melhor experiência para os clientes. Interromper uma jornada envolve que as pessoas que já entraram em uma jornada sejam todas interrompidas em seu progresso. A jornada está basicamente desligada.

>[!NOTE]
>
>Observe que não é possível retomar uma jornada fechada ou interrompida.
>
>O conceito de término de jornada está descrito nesta [seção](../building-journeys/journey.md#ending_a_journey).

## Fechamento de uma jornada

Você pode fechar uma jornada manualmente para garantir que os clientes que já entraram na jornada possam concluir seu caminho, mas os novos usuários não possam entrar na jornada.

Quando fechada, uma jornada terá o status **[!UICONTROL Closed (no entrance)]**. Após o tempo limite global padrão de 30 dias, a jornada mudará para o status **Concluído**. Consulte esta [seção](../building-journeys/changing-properties.md#entrance).

Uma versão de jornada fechada não pode ser reiniciada ou excluída. Você pode criar uma nova versão ou duplicá-la. Somente as jornadas concluídas podem ser excluídas.

Você pode fechar uma jornada clicando em **[!UICONTROL Close to new entrances]** enquanto passa o mouse sobre uma jornada na lista de jornadas.

![](../assets/do-not-localize/journey-finish-quick-action.png)

Você também pode:

1. Em **[!UICONTROL Home]**, clique na jornada que deseja fechar.
1. No canto superior direito, clique na seta para baixo.

   ![](../assets/finish_drop_down_list.png)

1. Clique em **[!UICONTROL Close to new entrances]**. Uma caixa de diálogo é exibida.
1. Clique em **[!UICONTROL Close to new entrances]** para confirmar.

## Interrupção de uma jornada

Você pode parar uma jornada quando ocorrer uma emergência e todo o processamento precisar ser finalizado imediatamente em uma jornada.

Uma versão do jornada interrompida não pode ser reiniciada.

Quando interrompida, uma jornada terá o status **[!UICONTROL Stopped]**.

Você pode parar uma jornada (por exemplo, se um profissional de marketing perceber que a jornada está direcionada ao público errado ou se uma ação personalizada para entregar mensagens não estiver funcionando corretamente...) clicando em **[!UICONTROL Stop]** enquanto passa o mouse sobre uma jornada na lista de jornadas.

![](../assets/do-not-localize/journey-stop-quick-action.png)

Você também pode:

1. Em **[!UICONTROL Home]**, clique na jornada que deseja parar.
1. No canto superior direito, clique na seta para baixo.

![](../assets/finish_drop_down_list.png)

1. Clique em **[!UICONTROL Stop]**. Uma caixa de diálogo é exibida.
1. Clique em **[!UICONTROL Stop]** para confirmar.
