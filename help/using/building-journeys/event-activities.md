---
product: adobe campaign
solution: Journey Orchestration
title: Sobre atividades de eventos
description: Saiba mais sobre atividades de eventos
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 1%

---


# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [this page](../event/about-events.md)) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre inicie a jornada arrastando e soltando uma atividade de evento. Você também pode clicar duas vezes nela.

![](../assets/journey44.png)

Ao clicar na atividade de evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar o campo **[!UICONTROL Label]** para adicionar um sufixo ao nome do evento que aparecerá sob sua atividade na tela. Isso é útil para identificar os eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Acompanhamento de eventos em um horário específico

Uma atividade de evento posicionada na jornada escuta eventos indefinidamente. Para ouvir um evento somente durante um determinado tempo, é necessário configurar um tempo limite para o evento.

A jornada ouvirá o evento durante o tempo especificado no tempo limite. Se um evento for recebido durante esse período, a pessoa fluirá no caminho do evento. Caso contrário, o cliente fluirá para um caminho de tempo limite ou encerrará sua jornada.

Para configurar um tempo limite para um evento, siga estas etapas:

1. Ative a opção **[!UICONTROL Enable the event timeout]** nas propriedades do evento.

1. Especifique a quantidade de tempo que a jornada aguardará pelo evento.

1. Se desejar enviar os indivíduos para um caminho de tempo limite quando nenhum evento for recebido dentro do tempo limite especificado, habilite a opção **[!UICONTROL Set the timeout path]**. Se essa opção não estiver ativada, a jornada terminará para o indivíduo depois que o tempo limite for atingido.

   ![](../assets/event-timeout.png)

Neste exemplo, a jornada envia um primeiro push de boas-vindas a um cliente. Em seguida, ele envia um push de desconto para refeições somente se o cliente entrar no restaurante no dia seguinte. Portanto, configuramos o evento de restaurante com um tempo limite de 1 dia:

* Se o evento do restaurante for recebido menos de 1 dia após o push de boas-vindas, a atividade de push de desconto para refeições será enviada.
* Se nenhum evento de restaurante for recebido no dia seguinte, a pessoa percorre o caminho de tempo limite.

Observe que, se quiser configurar um tempo limite em vários eventos posicionados após uma atividade **[!UICONTROL Wait]** , será necessário configurar o tempo limite em um desses eventos somente.

O tempo limite será aplicado a todos os eventos posicionados após a atividade **[!UICONTROL Wait]** . Se nenhum evento for recebido após o tempo limite especificado, os indivíduos fluirão para um único caminho de tempo limite ou encerrarão sua jornada.

![](../assets/event-timeout-group.png)
