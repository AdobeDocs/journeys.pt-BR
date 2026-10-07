---
product: adobe campaign
title: Ciclo de dados do evento
description: Saiba mais sobre o ciclo de dados do evento
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 79%
---
# Ciclo de dados {#section_r1f_xqt_pgb}

Eventos são chamadas POST API. Os eventos são enviados para a Adobe Experience Platform por meio de APIs de ingestão de transmissão. O destino do URL de eventos enviados por meio de APIs de mensagens transacionais é chamado de entrada. A carga útil de eventos segue a formatação XDM.

O payload contém informações necessárias para que as APIs de ingestão de transmissão funcionem (no cabeçalho) e as informações necessárias para que o [!DNL Journey Orchestration] funcione (a ID do evento, parte do corpo do payload útil) e as informações que serão usadas em jornadas (no corpo, por exemplo, o valor total de um carrinho abandonado). Há dois modos para a ingestão de transmissão, autenticados e não autenticados. Para obter detalhes sobre as APIs de ingestão de transmissão, consulte [este link](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=pt-BR).

Após a chegada através das APIs de ingestão de transmissão, os eventos fluem para um serviço interno chamado Pipeline e, em seguida, para a Adobe Experience Platform. Se o esquema do evento tiver o sinalizador de Serviço de perfil do cliente em tempo real habilitado e uma ID de conjunto de dados que também tenha o sinalizador de Perfil do cliente em tempo real, ele fluirá para o Serviço de perfil do cliente em tempo real.

Para eventos gerados pelo sistema, o Pipeline filtra os eventos que têm uma carga contendo [!DNL Journey Orchestration] eventIDs (consulte o processo de criação de eventos abaixo) fornecidos por [!DNL Journey Orchestration] e contidos na carga do evento. Para eventos baseados em regras, o sistema identifica o evento usando a condição eventID. Esses eventos são acompanhados pelo [!DNL Journey Orchestration] e a jornada correspondente é acionada.
