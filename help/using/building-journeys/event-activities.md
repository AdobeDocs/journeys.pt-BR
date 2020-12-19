---
product: adobe campaign
solution: Journey Orchestration
title: Sobre atividades de eventos
description: Saiba mais sobre atividades de eventos
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [this page](../event/about-events.md)) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre start sua jornada arrastando e soltando uma atividade evento. Você também pode clicar duplo nele.

![](../assets/journey44.png)

Quando você clica na atividade do evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar o campo **[!UICONTROL Label]** para adicionar um sufixo ao nome do evento que aparecerá sob sua atividade na tela. Isso é útil para identificar seus eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Acompanhamento de eventos durante um horário específico

Uma atividade evento posicionada na viagem escuta eventos indefinidamente. Para ouvir um evento somente durante um determinado tempo, é necessário configurar um tempo limite para o evento.

A viagem ouvirá o evento durante o tempo especificado no tempo limite. Se um evento for recebido durante esse período, ele fluirá no caminho do evento. Caso contrário, o cliente fluirá para um caminho de tempo limite ou encerrará sua jornada.

Para configurar um tempo limite para um evento, siga estas etapas:

1. Ative a opção **[!UICONTROL Enable the event timeout]** nas propriedades do evento.

1. Especifique a quantidade de tempo que a jornada aguardará pelo evento.

1. Se desejar enviar os indivíduos para um caminho de tempo limite quando nenhum evento for recebido dentro do tempo limite especificado, ative a opção **[!UICONTROL Set the timeout path]**. Se essa opção não estiver ativada, a jornada terminará para o indivíduo depois que o tempo limite for atingido.

   ![](../assets/event-timeout.png)

Neste exemplo, a jornada envia um primeiro empurrão bem-vindo a um cliente. Em seguida, ele envia um desconto de refeição somente se o cliente entrar no restaurante no dia seguinte. Portanto, configuramos o evento do restaurante com um tempo limite de 1 dia:

* Se o evento do restaurante for recebido menos de 1 dia após o push de boas-vindas, a atividade de push de desconto para refeições será enviada.
* Se nenhum evento de restaurante for recebido no dia seguinte, a pessoa percorre o tempo limite.

Observe que se você quiser configurar um tempo limite em vários eventos posicionados após uma atividade **[!UICONTROL Wait]**, é necessário configurar o tempo limite em apenas um desses eventos.

O tempo limite será aplicado a todos os eventos posicionados após a atividade **[!UICONTROL Wait]**. Se nenhum evento for recebido após o tempo limite especificado, os indivíduos irão fluir para um único caminho de tempo limite ou terminarão sua jornada.

![](../assets/event-timeout-group.png)
