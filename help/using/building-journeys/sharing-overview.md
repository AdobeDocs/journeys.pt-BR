---
product: adobe campaign
title: Visão geral do compartilhamento de etapas da jornada
description: Visão geral do compartilhamento de etapas da jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 5%

---

# Visão geral do compartilhamento de etapas da jornada{#sharing-overview}

[!DNL Journey Orchestration] O envia automaticamente os dados de desempenho do jornada para a Adobe Experience Platform, para que possa ser combinado com outros dados para fins de análise.

>[!NOTE]
>
>Esse recurso é ativado por padrão em todas as instâncias para eventos de etapas do jornada. Não é possível modificar ou atualizar os esquemas e conjuntos de dados que foram criados durante o provisionamento para eventos de etapa. Por padrão, esses esquemas e conjuntos de dados estão no modo somente leitura.

Por exemplo, você configurou uma jornada que envia vários emails. Esse recurso permite combinar [!DNL Journey Orchestration] dados com dados de evento downstream como quantas conversões ocorreram, quanto envolvimento aconteceu no site ou quantas transações ocorreram na loja. As informações de jornada podem ser combinadas com dados no Adobe Experience Platform, de outras propriedades digitais ou de propriedades offline, para fornecer uma visão mais abrangente do desempenho.

[!DNL Journey Orchestration] O cria automaticamente os esquemas e fluxos necessários em conjuntos de dados para a Adobe Experience Platform para cada etapa que um indivíduo faz em uma jornada. Um evento de etapa corresponde a um indivíduo que se move de um nó para outro em uma jornada. Por exemplo, em uma jornada que tem um evento, uma condição e uma ação, três eventos de etapa são enviados para a Adobe Experience Platform.

A lista de campos XDM que são passados é abrangente. Alguns contêm códigos gerados pelo sistema e outros têm nomes amigáveis legíveis. Os exemplos incluem o rótulo da atividade de jornada ou o status da etapa: quantas vezes uma ação atingiu o tempo limite ou terminou com erro.

>[!CAUTION]
>
>Os conjuntos de dados não podem ser ativados para o serviço de perfil em tempo real. Certifique-se de que a variável **[!UICONTROL Profile]** está desligado.

O Jornada envia dados conforme ocorre, de forma contínua. Você pode consultar esses dados usando o Serviço de query. Você pode se conectar ao Customer Journey Analytics ou a outras ferramentas de BI para exibir dados relacionados a essas etapas.

Os seguintes esquemas são criados:

* Esquema do Evento de etapa de Jornada para [!DNL Journey Orchestration] - Evento de etapa de Jornada vinculado a um Metadado de Jornada.
* Jornada esquema com Campos de Jornada para [!DNL Journey Orchestration] - Jornada metadados para descrever Jornadas.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Os seguintes conjuntos de dados são transmitidos:

* Jornada de eventos em etapas
* Jornadas

![](../assets/sharing3.png)

As listas de campos XDM passados para a Adobe Experience Platform são detalhadas aqui:

* [Lista de campos de evento de etapa](../building-journeys/sharing-field-list.md)
* [Campos de evento de etapa herdado](../building-journeys/sharing-legacy-fields.md)

Para obter mais informações sobre os eventos das etapas relatados para o Adobe Experience Platform, assista a isso [vídeo tutorial](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## Integração com o Customer Jornada Analytics{#integration-cja}

Os eventos Journey Orchestration step podem ser vinculados a outros conjuntos de dados em [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR). Este é o fluxo de trabalho geral:

* O Customer Journey Analytics assimila o conjunto de dados &quot;Evento de etapa de Jornada&quot;.
* O **profileID** no &quot;Jornada Step Event schema for Journey Orchestration&quot; associado é definido como um campo Identity . No Customer Journey Analytics, é possível vincular esse conjunto de dados a qualquer outro conjunto de dados que tenha o mesmo valor do identificador baseado em pessoas.
* Se quiser usar esse conjunto de dados no Customer Journey Analytics, para análise de jornada entre canais, consulte [documentação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
