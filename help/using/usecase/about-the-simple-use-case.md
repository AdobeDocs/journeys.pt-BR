---
product: adobe campaign
title: Sobre o caso de uso simples
description: Saiba mais sobre o caso de uso simples do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 13%

---

# Sobre o caso de uso simples{#concept_grh_vby_w2b}

## Propósito {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de beacon perto de todas as áreas estratégicas: saguão, chão, restaurante, ginástica, piscina, etc.

Nesse caso de uso, veremos como enviar uma mensagem personalizada em tempo real a uma pessoa que caminha ao lado de um beacon posicionado perto do spa.

Queremos enviar uma mensagem somente se a pessoa for mulher. A mensagem deve ser recebida em segundos.

![](../assets/journeyuc1_16.png)

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, projetamos um modelo de mensagens transacionais de email no Adobe Campaign Standard. Estamos usando um template de mensagem transacional de evento. Consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=pt-BR).

O Adobe Campaign Standard está configurado para enviar emails.

Os eventos são enviados do celular do cliente quando são detectados perto de um beacon. Você precisa criar um aplicativo móvel para enviar eventos do celular do cliente para o SDK móvel.
