---
title: Sobre atividades de eventos
description: Saiba mais sobre atividades de eventos
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 65ff1003fdfec087e4e2030dd81df8dab6229495
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 1%

---


# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [](../event/about-events.md)) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre start sua jornada arrastando e soltando uma atividade evento. Você também pode clicar duplo nele.

![](../assets/journey44.png)

Quando você clica na atividade do evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar o **[!UICONTROL Label]** campo para adicionar um sufixo ao nome do evento que aparecerá sob sua atividade na tela. Isso é útil para identificar seus eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Acompanhamento de eventos durante um horário específico

Uma atividade evento posicionada na viagem escuta eventos indefinidamente. Para ouvir um evento somente durante um determinado tempo, é necessário configurar um tempo limite para o evento.

A viagem ouvirá o evento durante o tempo especificado no tempo limite. Se um evento for recebido durante esse período, ele fluirá no caminho do evento. Caso contrário, o cliente fluirá para um caminho de tempo limite ou encerrará sua jornada.

Para configurar um tempo limite para um evento, siga estas etapas:

1. Ative a **[!UICONTROL Enable the event timeout]** opção nas propriedades do evento.

1. Especifique a quantidade de tempo que a jornada aguardará pelo evento.

1. Se desejar enviar os indivíduos para um caminho de tempo limite quando nenhum evento for recebido dentro do tempo limite especificado, ative a **[!UICONTROL Set the timeout path]** opção. Se essa opção não estiver ativada, a jornada terminará para o indivíduo depois que o tempo limite for atingido.

   ![](../assets/event-timeout.png)

Neste exemplo, a jornada envia um primeiro empurrão bem-vindo a um cliente. Em seguida, ele envia um desconto de refeição somente se o cliente entrar no restaurante no dia seguinte. Portanto, configuramos o evento do restaurante com um tempo limite de 1 dia:

* Se o evento do restaurante for recebido menos de 1 dia após o push de boas-vindas, a atividade de push de desconto para refeições será enviada.
* Se nenhum evento de restaurante for recebido no dia seguinte, a pessoa percorre o tempo limite.

Observe que se você quiser configurar um tempo limite em vários eventos posicionados após uma **[!UICONTROL Wait]** atividade, é necessário configurar o tempo limite em apenas um desses eventos.

O tempo limite será aplicado a todos os eventos posicionados após a **[!UICONTROL Wait]** atividade. Se nenhum evento for recebido após o tempo limite especificado, os indivíduos irão fluir para um único caminho de tempo limite ou terminarão sua jornada.

![](../assets/event-timeout-group.png)
