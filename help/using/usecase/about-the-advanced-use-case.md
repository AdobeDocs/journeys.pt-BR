---
title: Sobre o caso de uso avançado
description: Saiba mais sobre o caso de uso avançado da jornada
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 6%

---


# Sobre o caso de uso avançado{#concept_vzy_ncy_w2b}

## Finalidade {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de beacon perto de todas as áreas estratégicas: saguão, chão, restaurante, ginástica, piscina, etc.

>[!NOTE]
>
>Nesse caso de uso, usamos o Adobe Campaign Standard para enviar mensagens.

Neste caso de uso, veremos como enviar mensagens personalizadas em tempo real aos clientes quando eles se aproximarem de um beacon específico.

Em primeiro lugar, queremos enviar uma mensagem assim que uma pessoa entrar num hotel Marlton. Queremos enviar uma mensagem apenas se a pessoa não tiver recebido qualquer comunicação nossa dentro das últimas 24 horas.

Em seguida, verificamos duas condições:

* Se essa pessoa não for um membro de fidelidade, enviaremos um email para ele ingressar na oferta de afiliação.
* Se essa pessoa já for um membro de fidelidade, verificaremos se ela tem uma reserva de sala:
   * Se ele não fizer isso, enviaremos uma notificação por push com as taxas de sala.
   * Se o fizer, enviaremos-lhe uma notificação por push de boas-vindas. E se ele entrar no restaurante dentro de 6 horas, nós lhe enviamos uma notificação por push com um desconto em uma refeição.

![](../assets/journeyuc2_29.png)

Nesse caso de uso, será necessário criar dois eventos (consulte [](../usecase/configuring-the-events.md)):

* O evento de beacon do lobby que será empurrado para o sistema quando um cliente entrar no hotel.
* O evento de beacon do restaurante que será empurrado quando um cliente entrar no restaurante.

Será necessário configurar uma conexão com duas fontes de dados (consulte [](../usecase/configuring-the-data-sources.md)):

* A fonte de dados integrada do Adobe Experience Platform, para recuperar as informações de nossas duas condições (associação de fidelidade e data do último contato), bem como as informações de personalização da mensagem.
* O sistema de reservas do hotel, para recuperar as informações de status da reserva.

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, criamos três modelos de mensagens transacionais de Adobe Campaign Standard. Estamos usando modelos de mensagens transacionais de evento. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

O Adobe Campaign Standard está configurado para enviar emails e notificações por push.

A ID do Experience Cloud é usada como a chave para identificar o cliente no sistema de reservas do hotel.

Eventos são enviados do telefone celular do cliente quando eles detectam perto de um sinal. Você precisa projetar um aplicativo móvel para enviar eventos do telefone móvel do cliente para o SDK móvel.

O campo membro Fidelidade é um campo personalizado e foi adicionado no XDM para nossa ID de organização específica.
