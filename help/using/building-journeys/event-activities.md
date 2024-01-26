---
product: adobe campaign
title: Sobre atividades de eventos
description: Saiba mais sobre atividades de eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: fca24f7dd0f9170fa209474f270a4c0fb4080c03
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [esta página](../event/about-events.md)) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre inicie a jornada arrastando e soltando uma atividade de evento. Você também pode clicar duas vezes nela.

![](../assets/journey44.png)

Ao clicar na atividade de evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar a variável **[!UICONTROL Label]** para adicionar um sufixo ao nome do evento que aparecerá em sua atividade na tela. Isso é útil para identificar seus eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Acompanhamento de eventos durante um período específico {#listening}

Uma atividade de evento posicionada na jornada escuta eventos indefinidamente. Para acompanhar um evento somente durante um determinado tempo, você deve configurar um tempo limite para o evento.

A jornada ouvirá o evento durante o tempo especificado no tempo limite. Se um evento for recebido durante esse período, a pessoa fluirá no caminho do evento. Caso contrário, o cliente fluirá para o caminho de tempo limite, se estiver definido, ou continuará essa jornada. Se nenhum caminho de tempo limite for definido, a configuração de tempo limite atuará como uma atividade de espera, fazendo com que o perfil aguarde um período, que pode ser interrompido se um evento ocorrer antes do fim dessa espera. Se desejar que os perfis sejam excluídos dessa jornada após o tempo limite, será necessário definir um caminho de tempo limite.

Para configurar um tempo limite para um evento, siga estas etapas:

1. Ativar o **[!UICONTROL Enable the event timeout]** nas propriedades do evento.

1. Especifique por quanto tempo a jornada aguardará pelo evento.

1. Se desejar enviar as pessoas físicas para um caminho de tempo limite quando nenhum evento for recebido dentro do tempo limite especificado, habilite o **[!UICONTROL Set the timeout path]** opção. Se essa opção não estiver ativada, a jornada continuará para o indivíduo assim que o tempo limite for atingido.

   ![](../assets/event-timeout.png)

Neste exemplo, a jornada envia um primeiro push de boas-vindas para um cliente. Em seguida, ele envia um push de desconto para refeição somente se o cliente entrar no restaurante no dia seguinte. Portanto, configuramos o evento do restaurante com um tempo limite de 1 dia:

* Se o evento do restaurante for recebido menos de 1 dia após o push de boas-vindas, a atividade de push de desconto para refeições será enviada.
* Se nenhum evento de restaurante for recebido no dia seguinte, a pessoa fluirá pelo caminho de tempo limite.

Observe que se quiser configurar um tempo limite em vários eventos posicionados após um **[!UICONTROL Wait]** atividade, é necessário configurar o tempo limite em apenas um desses eventos.

O tempo limite será aplicado a todos os eventos posicionados após o **[!UICONTROL Wait]** atividade. Se nenhum evento for recebido antes do tempo limite especificado, as pessoas físicas fluirão para um único caminho de tempo limite ou continuarão essa jornada pela ramificação que sai da atividade onde essas configurações de tempo limite foram definidas.

![](../assets/event-timeout-group.png)
