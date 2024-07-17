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
source-wordcount: '411'
ht-degree: 3%

---

# Sobre o caso de uso avançado{#concept_vzy_ncy_w2b}

## Finalidade {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de sinal perto de todas as áreas estratégicas: lobby, pisos, restaurante, ginásio, piscina, etc.

>[!NOTE]
>
>Nesse caso de uso, usamos o Adobe Campaign Standard para enviar mensagens.

Nesse caso de uso, veremos como enviar mensagens personalizadas em tempo real para clientes quando eles se aproximarem de um beacon específico.

Primeiro, queremos enviar uma mensagem assim que uma pessoa entrar em um hotel em Marlton. Queremos enviar uma mensagem somente se a pessoa não tiver recebido nenhuma comunicação conosco nas últimas 24 horas.

Em seguida, verificamos duas condições:

* Se essa pessoa não for um membro do programa de fidelidade, enviaremos um email para ela ingressar na oferta de associação de fidelidade.
* Se essa pessoa já for um membro do programa de fidelidade, verificamos se tem uma reserva de quarto:
   * Caso contrário, enviamos a eles uma notificação por push com tarifas de quarto.
   * Se o fizer, enviaremos a eles uma notificação por push de boas-vindas. E se ele entrar no restaurante dentro das próximas 6 horas, enviamos a eles uma notificação por push com desconto em uma refeição.

![](../assets/journeyuc2_29.png)

Neste caso de uso, precisaremos criar dois eventos (consulte [esta página](../usecase/configuring-the-events.md)):

* O evento de sinal de lobby que será encaminhado para o sistema quando um cliente entrar no hotel.
* O evento de beacon do restaurante que será transmitido quando um cliente entrar no restaurante.

Precisaremos configurar uma conexão com duas fontes de dados (consulte [esta página](../usecase/configuring-the-data-sources.md)):

* A fonte de dados integrada do Adobe Experience Platform, para recuperar as informações de nossas duas condições (associação de fidelidade e data do último contato), bem como as informações de personalização da mensagem.
* O sistema de reservas de hotel, para recuperar as informações de status da reserva.

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, projetamos três modelos de mensagens transacionais do Adobe Campaign Standard. Estamos usando modelos de mensagens transacionais de evento. Consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=pt-BR).

O Adobe Campaign Standard está configurado para enviar emails e notificações por push.

A ID do Experience Cloud é usada como a chave para identificar o cliente no sistema de reservas do hotel.

Os eventos são enviados pelo celular dos clientes quando eles detectam perto de um beacon. Você precisa criar um aplicativo para dispositivos móveis para enviar eventos do celular do cliente para o SDK móvel.

O campo Membro de fidelidade é um campo personalizado e foi adicionado no XDM para a ID de organização específica.
