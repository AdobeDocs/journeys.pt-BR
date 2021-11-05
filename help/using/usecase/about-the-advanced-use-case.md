---
product: adobe campaign
title: Sobre o caso de uso avançado
description: Saiba mais sobre o caso de uso avançado do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 5%

---

# Sobre o caso de uso avançado{#concept_vzy_ncy_w2b}

## Propósito {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de beacon perto de todas as áreas estratégicas: saguão, chão, restaurante, ginástica, piscina, etc.

>[!NOTE]
>
>Nesse caso de uso, usamos o Adobe Campaign Standard para enviar mensagens.

Nesse caso de uso, veremos como enviar mensagens personalizadas em tempo real para os clientes quando eles se aproximarem de um beacon específico.

Em primeiro lugar, queremos enviar uma mensagem assim que uma pessoa entrar em um hotel Marlton. Queremos enviar uma mensagem apenas se a pessoa não tiver recebido nenhuma comunicação nossa nas últimas 24 horas.

Em seguida, verificamos duas condições:

* Se essa pessoa não for um membro do programa de fidelidade, enviamos um email para associar-se à oferta de associação de fidelidade.
* Se essa pessoa já for um membro do programa de fidelidade, verificamos se ela tem uma reserva de quarto:
   * Caso contrário, enviamos uma notificação por push com as taxas de sala.
   * Se ele fizer isso, enviamos uma notificação por push de boas-vindas. E se ele entrar no restaurante nas próximas 6 horas, enviamos uma notificação por push com um desconto em uma refeição.

![](../assets/journeyuc2_29.png)

Nesse caso de uso, será necessário criar dois eventos (consulte [esta página](../usecase/configuring-the-events.md)):

* O evento de beacon do lobby que será enviado para o sistema quando um cliente entrar no hotel.
* O evento de beacon do restaurante que será enviado quando um cliente entrar no restaurante.

Será necessário configurar uma conexão com duas fontes de dados (consulte [esta página](../usecase/configuring-the-data-sources.md)):

* A fonte de dados integrada do Adobe Experience Platform, para recuperar as informações de nossas duas condições (associação de fidelidade e data do último contato), bem como as informações de personalização da mensagem.
* O sistema de reservas do hotel, para recuperar as informações de status da reserva.

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, projetamos três templates de mensagens transacionais do Adobe Campaign Standard. Estamos usando templates de mensagens transacionais de evento. Consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=pt-BR).

O Adobe Campaign Standard está configurado para enviar emails e notificações por push.

A ID do Experience Cloud é usada como a chave para identificar o cliente no sistema de reservas do hotel.

Os eventos são enviados do celular do cliente quando foram detectados perto de um beacon. Você precisa criar um aplicativo móvel para enviar eventos do celular do cliente para o SDK móvel.

O campo Loyalty member é um campo personalizado e foi adicionado no XDM para nossa ID de organização específica.
