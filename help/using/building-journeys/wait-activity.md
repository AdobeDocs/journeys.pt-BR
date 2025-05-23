---
product: adobe campaign
title: Atividade Aguardar
description: Saiba mais sobre a atividade de espera
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 8%

---

# Atividade Aguardar{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._



Se quiser aguardar antes de executar a próxima atividade no caminho, você pode usar uma atividade **[!UICONTROL Wait]**. Ela permite definir o momento em que a próxima atividade será executada. Três opções estão disponíveis:

* [Duração](#duration)
* [Personalizado](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## Sobre a atividade Wait{#about_wait}

Esta é a forma como as esperas são priorizadas quando você usa várias esperas em paralelo. Se eles tiverem a mesma configuração de tempo e uma condição diferente, mas sobreposta, a espera posicionada acima será a priorizada. Por exemplo, a condição da primeira espera é &quot;ser uma mulher&quot; e a condição da segunda espera em paralelo é &quot;ser uma VIP&quot;. A primeira atividade de espera será priorizada.

Observe também que se duas esperas diferentes estiverem em paralelo, a que ocorrer primeiro será priorizada, independentemente da sua posição vertical. Por exemplo, se uma espera de 1 hora estiver acima e uma espera de 30 minutos estiver abaixo, após 30 minutos, a espera de 30 minutos será processada.

>[!NOTE]
>
>A duração máxima de espera é de 30 dias.
>
>No modo de teste, o parâmetro **[!UICONTROL Wait time in test]** permite definir o tempo que cada atividade de espera durará. O tempo padrão é de 10 segundos. Isso garantirá que você obtenha os resultados do teste rapidamente. Ver [esta página](../building-journeys/testing-the-journey.md)

## Espera de duração{#duration}

Selecione a duração da espera antes da execução da próxima atividade.

![](../assets/journey55.png)

## Espera personalizada{#custom}

Essa opção permite definir uma data personalizada, por exemplo, 12 de julho de 2020 às 17h, usando uma expressão avançada com base em um campo proveniente de um evento ou de uma fonte de dados. Isso não permite definir uma duração personalizada, por exemplo, 7 dias. A expressão no editor de expressão deve fornecer um formato dateTimeOnly. Consulte [esta página](../expression/expressionadvanced.md). Para obter mais informações sobre o formato dateTimeOnly, consulte [esta página](../expression/data-types.md).

>[!NOTE]
>
>Você pode usar uma expressão dateTimeOnly ou usar uma função para converter em dateTimeOnly. Por exemplo: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), o campo no evento é do formulário 2016-08-12T09:46:06Z.
>
>O **fuso horário** é esperado nas propriedades da jornada. Como resultado, não é possível, hoje, a partir da interface apontar diretamente para um carimbo de data e hora ISO-8601 completo misturando deslocamento de tempo e fuso horário como 2016-08-12T09:46:06.982-05. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
