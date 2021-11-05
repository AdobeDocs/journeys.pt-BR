---
product: adobe campaign
title: Sobre atividades de eventos
description: Saiba mais sobre atividades de eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 5b09ed456b6a9645dbb7897481317d3904e29d31
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [esta página](../event/about-events.md)) são exibidas na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre inicie a jornada arrastando e soltando uma atividade de evento. Você também pode clicar duas vezes nela.

![](../assets/journey44.png)

Ao clicar na atividade de evento na tela, o painel de configuração da atividade é exibido. By default, when you use the same event several times, an incremented number is added to the event name in the canvas. Além disso, você pode usar o **[!UICONTROL Label]** para adicionar um sufixo ao nome do evento que aparecerá sob a atividade na tela. Isso é útil para identificar os eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Acompanhamento de eventos em um horário específico

An event activity positioned in the journey listens to events indefinitely. Para ouvir um evento somente durante um determinado tempo, é necessário configurar um tempo limite para o evento.

A jornada ouvirá o evento durante o tempo especificado no tempo limite. If an event is received during that period, the person will flow in the event path. If not, the customer will either flow into a timeout path, or end their journey.

Para configurar um tempo limite para um evento, siga estas etapas:

1. Activate the **[!UICONTROL Enable the event timeout]** option from the event properties.

1. Especifique a quantidade de tempo que a jornada aguardará pelo evento.

1. If you want to send the individuals into a timeout path when no event is received within the specified timeout, enable the **[!UICONTROL Set the timeout path]** option. Se essa opção não estiver ativada, a jornada terminará para o indivíduo depois que o tempo limite for atingido.

   ![](../assets/event-timeout.png)

In this example, the journey sends a first welcome push to a customer. Em seguida, ele envia um push de desconto para refeições somente se o cliente entrar no restaurante no dia seguinte. Portanto, configuramos o evento de restaurante com um tempo limite de 1 dia:

* Se o evento do restaurante for recebido menos de 1 dia após o push de boas-vindas, a atividade de push de desconto para refeições será enviada.
* If no restaurant event is received within the next day, the person flows through the timeout path.

Observe que se você quiser configurar um tempo limite em vários eventos posicionados após uma **[!UICONTROL Wait]** , é necessário configurar o tempo limite em um desses eventos somente.

O tempo limite será aplicado a todos os eventos posicionados após a **[!UICONTROL Wait]** atividade . If no event is received before the specified timeout, the individuals will flow into one single timeout path or will end their journey.

![](../assets/event-timeout-group.png)
