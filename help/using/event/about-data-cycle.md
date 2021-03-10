---
product: adobe campaign
solution: Journey Orchestration
title: Ciclo de dados do evento
description: Saiba mais sobre o ciclo de dados do evento
feature: Jornada
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 78%

---


# Ciclo de dados {#section_r1f_xqt_pgb}

Eventos são chamadas POST API. Os eventos são enviados para a Adobe Experience Platform por meio de APIs de assimilação de streaming. O destino do URL de eventos enviados por meio de APIs de mensagens transacionais é chamado de &quot;inlet&quot;. A carga útil de eventos segue a formatação XDM.

O payload contém informações necessárias para que as APIs de assimilação de streaming funcionem (no cabeçalho) e as informações necessárias para que o [!DNL Journey Orchestration] funcione (a ID do evento, parte do corpo do payload útil) e as informações que serão usadas em jornadas (no corpo, por exemplo, o valor total de um carrinho abandonado). Há dois modos para a assimilação de fluxo, autenticados e não autenticados. Para obter detalhes sobre as APIs de assimilação de fluxo, consulte [este link](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/api/getting-started.html).

Após a chegada através das APIs de assimilação de streaming, os eventos fluem para um serviço interno chamado Pipeline e, em seguida, para a Adobe Experience Platform. Se o schema do evento tiver o sinalizador de Serviço de perfil do cliente em tempo real ativado e uma ID de conjunto de dados que também tenha o sinalizador de Perfil do cliente em tempo real, ele fluirá para o Serviço de perfil do cliente em tempo real.

Para eventos gerados pelo sistema, o Pipeline filtra eventos que têm uma carga útil contendo [!DNL Journey Orchestration] eventIDs (consulte o processo de criação de eventos abaixo) fornecidas por [!DNL Journey Orchestration] e contidas na carga útil do evento. Para eventos com base em regras, o sistema identifica o evento usando a condição eventID. Esses eventos são acompanhados pelo [!DNL Journey Orchestration] e a jornada correspondente é acionada.
