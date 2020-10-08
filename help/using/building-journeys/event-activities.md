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
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---


# Sobre atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [](../event/about-events.md)) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre start sua jornada arrastando e soltando uma atividade evento. Você também pode clicar duplo nele.

![](../assets/journey44.png)

Quando você clica na atividade do evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar o **[!UICONTROL Label]** campo para adicionar um sufixo ao nome do evento que aparecerá sob sua atividade na tela. Isso é útil para identificar seus eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Uso avançado: eventos com espera em paralelo{#section_vxv_h25_pgb}

**Como você pode ouvir um evento apenas durante um determinado tempo?**

Uma atividade evento posicionada na viagem escuta eventos indefinidamente. Para ouvir um evento somente durante um determinado tempo, é necessário adicionar uma atividade de espera paralela ao caminho do evento. A viagem ouvirá o evento durante o tempo especificado na atividade de espera. Se um evento for recebido durante esse período, ele fluirá no caminho do evento. Caso contrário, o cliente fluirá para o caminho de espera.

Por exemplo, você enviou um primeiro push de boas-vindas para um cliente e deseja enviar um push de desconto de refeição somente se o cliente entrar no restaurante dentro das próximas 6 horas. Para fazer isso, você criará um segundo caminho (paralelo ao evento do restaurante um) com uma atividade de espera de 6 horas. Se o evento do restaurante for recebido menos de 6 horas após o push de boas-vindas, a atividade de push de desconto para refeições será enviada. Se nenhum evento de restaurante for recebido dentro das próximas 6 horas, a pessoa percorre o caminho de espera.

![](../assets/journeyuc2_31.png)
