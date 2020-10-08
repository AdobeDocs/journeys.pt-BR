---
title: Sobre o caso de uso simples
description: Saiba mais sobre o caso de uso simples da jornada
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
source-wordcount: '175'
ht-degree: 14%

---


# Sobre o caso de uso simples{#concept_grh_vby_w2b}

## Finalidade {#purpose}

Vejamos o exemplo de uma marca de hotel chamada Marlton. Em seus hotéis, eles posicionaram dispositivos de beacon perto de todas as áreas estratégicas: saguão, chão, restaurante, ginástica, piscina, etc.

Neste caso de uso, veremos como enviar uma mensagem personalizada em tempo real para uma pessoa que caminha ao lado de um beacon posicionado perto do spa.

Queremos enviar uma mensagem apenas se a pessoa for mulher. A mensagem deve ser recebida em segundos.

![](../assets/journeyuc1_16.png)

## Pré-requisitos {#prerequisites}

Para nosso caso de uso, criamos um modelo de mensagens transacionais por email no Adobe Campaign Standard. Estamos usando um modelo de mensagens transacionais de evento. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

A Adobe Campaign Standard está configurada para enviar emails.

Os eventos são enviados do celular do cliente quando são detectados perto de um sinal. Você precisa projetar um aplicativo móvel para enviar eventos do telefone móvel do cliente para o SDK móvel.