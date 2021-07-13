---
product: adobe campaign
title: 'Sobre schemas ExperienceEvent para eventos Journey Orchestration '
description: 'Saiba mais sobre Esquemas ExperienceEvent para Eventos de Journey Orchestration '
feature: Jornadas
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Sobre schemas ExperienceEvent para eventos [!DNL Journey Orchestration]

[!DNL Journey Orchestration] são Eventos de experiência XDM enviados para a Adobe Experience Platform por assimilação de fluxo.

Dessa forma, um pré-requisito importante para configurar eventos para [!DNL Journey Orchestration] é que você está familiarizado com o Experience Data Model (ou XDM) da Adobe Experience Platform e como compor schemas de Evento de experiência XDM, bem como como fazer o stream de dados formatados em XDM para a Adobe Experience Platform.

## Requisitos de esquema para eventos [!DNL Journey Orchestration]

A primeira etapa na configuração de um evento para [!DNL Journey Orchestration] é garantir que você tenha um esquema XDM definido para representar o evento e um conjunto de dados criado para registrar instâncias do evento na Adobe Experience Platform. Ter um conjunto de dados para seus eventos não é estritamente necessário, mas enviar os eventos para um conjunto de dados específico permitirá manter o histórico de eventos dos usuários para referência e análise futuras, portanto, é sempre uma boa ideia. Se você ainda não tiver um esquema e conjunto de dados adequados para o evento, ambas as tarefas podem ser realizadas na interface da Web do Adobe Experience Platform.

![](../assets/schema1.png)

Qualquer esquema XDM que será usado para eventos [!DNL Journey Orchestration] deve atender aos seguintes requisitos:

* O esquema deve ser da classe XDM ExperienceEvent.

   ![](../assets/schema2.png)

* Para eventos gerados pelo sistema, o esquema deve incluir o mixin Orchestration eventID. [!DNL Journey Orchestration] O usa esse campo para identificar eventos usados em jornadas.

   ![](../assets/schema3.png)

* Declarar um campo de identidade para identificar o assunto do evento. Se nenhuma identidade for especificada, um mapa de identidade poderá ser usado. Isso não é recomendado.

   ![](../assets/schema4.png)

* Se desejar que esses dados estejam disponíveis para pesquisa posteriormente em uma Jornada, marque o esquema e o conjunto de dados para o perfil.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* Você pode incluir campos de dados para capturar quaisquer outros dados de contexto que deseja incluir com o evento, como informações sobre o usuário, o dispositivo do qual o evento foi gerado, o local ou quaisquer outras circunstâncias significativas relacionadas ao evento.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)
