---
product: adobe campaign
solution: Journey Orchestration
title: 'Sobre Schemas ExperienceEvent para Eventos Journey Orchestration '
description: 'Saiba mais sobre os Schemas ExperienceEvent para Eventos Journey Orchestration '
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---



# Sobre Schemas ExperienceEvent para Eventos [!DNL Journey Orchestration]

[!DNL Journey Orchestration] Os eventos são Eventos de experiência XDM enviados para a Adobe Experience Platform por meio da ingestão de fluxo contínuo.

Dessa forma, um pré-requisito importante para configurar eventos para [!DNL Journey Orchestration] é que você está familiarizado com o Experience Data Model (ou XDM) da Adobe Experience Platform e com como compor schemas do Evento de experiência XDM, bem como como como fazer o stream de dados formatados XDM para a Adobe Experience Platform.

## Requisitos de schema para Eventos [!DNL Journey Orchestration]

A primeira etapa para configurar um evento para [!DNL Journey Orchestration] é garantir que você tenha um schema XDM definido para representar o evento e um conjunto de dados criado para registrar instâncias do evento no Adobe Experience Platform. Ter um conjunto de dados para seus eventos não é estritamente necessário, mas enviar os eventos para um conjunto de dados específico permitirá manter o histórico de eventos dos usuários para futura referência e análise, portanto, é sempre uma boa ideia. Se você ainda não tiver um schema e um conjunto de dados adequados para o seu evento, ambas as tarefas poderão ser feitas na interface da Web da Adobe Experience Platform.

![](../assets/schema1.png)

Qualquer schema XDM que será usado para eventos [!DNL Journey Orchestration] deve atender aos seguintes requisitos:

* O schema deve ser da classe XDM ExperienceEvent.

   ![](../assets/schema2.png)

* Para eventos gerados pelo sistema, o schema deve incluir a combinação Orchestration eventID. [!DNL Journey Orchestration] usa esse campo para identificar eventos usados em viagens.

   ![](../assets/schema3.png)

* Declarar um campo de identidade para identificar o assunto do evento. Se nenhuma identidade for especificada, um mapa de identidade poderá ser usado. Isso não é recomendado.

   ![](../assets/schema4.png)

* Se desejar que esses dados estejam disponíveis para pesquisa mais tarde em uma Jornada, marque o schema e o conjunto de dados para perfil.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* Sinta-se à vontade para incluir campos de dados para capturar quaisquer outros dados de contexto que você deseja incluir com o evento, como informações sobre o usuário, o dispositivo a partir do qual o evento foi gerado, o local ou quaisquer outras circunstâncias significativas relacionadas ao evento.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)