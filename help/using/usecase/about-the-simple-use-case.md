---
product: adobe campaign
solution: Journey Orchestration
title: Sobre o caso de uso simples
description: Saiba mais sobre o caso de uso simples do jornada
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 14%

---


# Sobre o caso de uso simples{#concept_grh_vby_w2b}

## Finalidade {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de beacon perto de todas as áreas estratégicas: saguão, chão, restaurante, ginástica, piscina, etc.

Nesse caso de uso, veremos como enviar uma mensagem personalizada em tempo real a uma pessoa que caminha ao lado de um beacon posicionado perto do spa.

Queremos enviar uma mensagem somente se a pessoa for mulher. A mensagem deve ser recebida em segundos.

![](../assets/journeyuc1_16.png)

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, projetamos um modelo de mensagens transacionais de email no Adobe Campaign Standard. Estamos usando um template de mensagem transacional de evento. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

O Adobe Campaign Standard está configurado para enviar emails.

Os eventos são enviados do celular do cliente quando são detectados perto de um beacon. Você precisa criar um aplicativo móvel para enviar eventos do celular do cliente para o SDK móvel.