---
title: 'Sobre Schemas ExperienceEvent para Eventos Journey Orchestration '
description: 'Saiba mais sobre os Schemas ExperienceEvent para Eventos Journey Orchestration '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606

---



# Sobre Schemas ExperienceEvent para Eventos Journey Orchestration

Os eventos Journey Orchestration são Eventos de experiência XDM enviados para a Adobe Experience Platform por meio da assimilação de fluxo contínuo.

Dessa forma, um pré-requisito importante para configurar eventos para o Journey Orchestration é que você está familiarizado com o Modelo de Dados de Experiência (ou XDM) da Plataforma e como compor schemas de Evento de Experiência XDM, bem como como como transmitir dados formatados XDM para a Plataforma.

## Requisitos de Schema para Eventos de orquestração de viagens

A primeira etapa na configuração de um evento para o Journey Orchestration é garantir que você tenha um schema XDM definido para representar o evento, e um conjunto de dados criado para registrar instâncias do evento na Plataforma. Ter um conjunto de dados para seus eventos não é estritamente necessário, mas enviar os eventos para um conjunto de dados específico permitirá manter o histórico de eventos dos usuários para futura referência e análise, portanto, é sempre uma boa ideia. Se você ainda não tiver um schema e um conjunto de dados adequados para o seu evento, ambas as tarefas poderão ser feitas na interface da Web da plataforma.

![](../assets/schema1.png)

Qualquer schema XDM que será usado para eventos do Journey Orchestration deve atender aos seguintes requisitos:

* O schema deve ser da classe XDM ExperienceEvent.

![](../assets/schema2.png)

* O schema deve incluir a combinação Orchestration eventID. A Journey Orchestration usa esse campo para identificar eventos usados em viagens.

![](../assets/schema3.png)

* Declarar um campo de identidade para identificar o assunto do evento. Se nenhuma identidade for especificada, um mapa de identidade poderá ser usado. Isso não é recomendado.

![](../assets/schema4.png)

* Se desejar que esses dados estejam disponíveis para pesquisa mais tarde em uma Jornada, marque o schema e o conjunto de dados para perfil.

![](../assets/schema5.png)

![](../assets/schema6.png)

* Sinta-se à vontade para incluir campos de dados para capturar quaisquer outros dados de contexto que você deseja incluir com o evento, como informações sobre o usuário, o dispositivo a partir do qual o evento foi gerado, o local ou quaisquer outras circunstâncias significativas relacionadas ao evento.

![](../assets/schema7.png)

![](../assets/schema8.png)