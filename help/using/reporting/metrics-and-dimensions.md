---
product: adobe campaign
solution: Journey Orchestration
title: Métricas e dimensões
description: Saiba mais sobre as dimensões e métricas disponíveis para o Journey Orchestration
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 2%

---


# Métricas e dimensões {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Os dados do delivery só serão preenchidos se você tiver o Adobe Campaign Standard.

Você pode encontrar aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.

A tabela abaixo fornece a lista de dimensões usadas nos relatórios de jornada e suas definições.

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Jornada dimensões {#MBE_table_wk4_bnj_w2b}

A tabela abaixo fornece a lista de dimensões usadas nos relatórios de jornada, suas definições e fórmulas.

| Dimension | Definição |
|--- |--- |
| **Ação** | Lista de todas as ações (**action name - action label**) usadas em jornadas, por exemplo, Push - Check out confirmation, Email - Rewards fidelity. |
| **Fonte de dados** | Lista de fontes de dados (**data source name**) usadas para enriquecer dados em uma jornada, por exemplo, Adobe Experience Platform, Sistema de reserva. |
| **[!UICONTROL Event]** | Lista de cada evento (**event name - event label**) usado em jornadas, por exemplo, Geometrixx event - Geometrixx check-out. |
| **Grupo de campos** | Lista de grupos de campos (**field group name**) usados para enriquecer dados em jornadas, por exemplo, Grupo de campos de perfil, sistema de reserva de Geometrixx. |
| **Jornada** | Lista de cada jornada (**jornada name**) no modo de teste e ao vivo, por exemplo, abandono de carrinho, notificação de reserva de hotel. |
| **Versão do Jornada** | Lista de todas as versões publicadas de uma jornada (**jornada name + número da versão**), por exemplo, Abandono de carrinho v1, Notificação de reserva de hotel v2. |
| **Orquestração** | Lista de todas as atividades de orquestração (**Condição, Fim, Wait**) definidas e usadas no jornada. |

## Dimensões de delivery {#delivery-dimensions}

A tabela abaixo fornece a lista de dimensões de delivery usadas nos relatórios de jornada, suas definições e fórmulas.

| Dimensão | Definição |
|--- |--- |
| **Navegador** | Navegador do qual a mensagem foi aberta ou clicada. |
| **Nome do delivery** | Rótulo e ID do delivery. |
| **Dispositivo** | Dispositivo do qual a notificação por email/SMS/push foi aberta/exibida/clicada. |
| **Tipo de mensagem** | Canal usado para o delivery, como email, SMS, notificação por push ou No aplicativo. |
| **Nome do aplicativo móvel** | Nome do aplicativo móvel |
| **Plataforma** | Plataforma do dispositivo a partir do qual a mensagem foi aberta/visualizada/clicada. |
| **[!UICONTROL Push platform]** | Plataforma do dispositivo do qual a notificação por push foi aberta, como iOS ou Android. |
| **Domínio do destinatário** | Domínio usado para abrir o email. |
| **URL de rastreamento** | URL que foi clicado pelo usuário na mensagem. |
| **Categoria de URL de rastreamento** | Categoria atribuída ao URL de rastreamento. |
| **Rótulo do URL de rastreamento** | Rótulo fornecido para o URL, como mirror page, entre em contato conosco ou abra. |
| **Variante** | Variante do email no caso de teste A/B. |

## Jornada métricas {#MBE_p_p22_c4j_w2b}

A tabela abaixo fornece a lista de métricas usadas em relatórios de jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |---|
| **Concluído** | Número total de indivíduos que terminaram normalmente a jornada. |
| **Taxa de conclusão** | Número total de indivíduos que terminaram normalmente a jornada em comparação ao número total de indivíduos que entraram na jornada. |
| **Atual** | Número total de indivíduos atualmente na jornada, ou seja, quantas pessoas entraram menos pessoas que saíram, erros e tempo limite. |
| **Taxa atual** | Número total de indivíduos que estão atualmente na jornada em comparação ao número de indivíduos que entraram na jornada. |
| **Digitado** | Número total de eventos que ocorreram para iniciar uma entrada individual na jornada. |
| **Erro** | Número total de erros que ocorreram durante uma jornada, mas que não impediram o sucesso da jornada. |
| **Erro na ação** | Número total de erros que ocorreram para ações. |
| **Erro no enriquecimento** | Número total de erros que ocorreram para um enriquecimento de dados ao chamar uma fonte de dados/grupo de campos. |
| **Erro no Evento** | Número total de erros que ocorreram para eventos. |
| **Taxa de Erro** | Número total de erros que ocorreram durante uma jornada em comparação ao número total de ocorrências na jornada. |
| **Ação executada** | Número total de ações executadas para uma jornada. |
| **Enriquecimento executado** | Número total de enriquecimentos executados chamando uma fonte de dados para obter grupos de campos específicos. |
| **Evento executado** | Número total de ações executadas para uma jornada. |
| **Orquestração executada** | Número total de objetos de orquestração (fim, espera, condição) executados para uma jornada. |
| **Failed** | Número total de jornadas que não foram executadas com êxito. |
| **Taxa de falha** | Número total de jornadas que não foram executadas com êxito em comparação ao número de jornadas de execução. |

## Métricas de delivery {#delivery-metrics}

A tabela abaixo fornece a lista de métricas usadas no jornada
relatórios, suas definições e fórmulas.

| Métrica | Definição |
|--- |--- |
| **Ao lista de bloqueios** | Número de recipients que declararam um email como spam ou lixo eletrônico. |
| **Taxa de lista de bloqueios** | Número total de mensagens em lista de bloqueios em comparação às mensagens enviadas. |
| **Rejeições + erros** | Total de erros acumulados durante o delivery e o processamento automático de retorno em relação ao número total de mensagens enviadas. |
| **Rejeição + taxa de erro** | Número total de mensagens que retornaram em comparação às mensagens enviadas. |
| **Clique em** | Número de vezes que um conteúdo foi clicado em um delivery. |
| **Índice de click-through** | Número total de cliques em um delivery em comparação ao número de mensagens entregues. |
| **Entregue** | Número de mensagens enviadas com êxito em relação ao número total de mensagens enviadas. |
| **Taxa de delivery** | Número total de mensagens entregues com êxito em comparação às mensagens enviadas. |
| **Erro** | Número total de erros que ocorreram durante uma jornada, mas que não impediram o sucesso da jornada. |
| **Rejeição permanente** | Número total de erros permanentes, como um endereço de email incorreto. |
| **Taxa de rejeição permanente** | Número total de deliveries que falharam devido a erros permanentes em comparação a mensagens enviadas. |
| **Mirror page** | Número de recipients que clicaram no link da mirror page. |
| **Taxa de mirror page** | Número total de cliques no link da mirror page em comparação ao total de mensagens entregues. |
| **Abertura** | Número de vezes que uma mensagem foi aberta em um delivery. |
| **Taxa de abertura** | Número total de mensagens abertas em comparação ao número de mensagens entregues. |
| **Quarentena** | Número de mensagens que retornaram e resultaram na quarentena do endereço. |
| **Taxa de Quarentena** | Número total de quarentenas em comparação às mensagens enviadas. |
| **Rejeitada** | Número de mensagens classificadas como spam pelos servidores SMTP. |
| **Taxa rejeitada** | Número total de mensagens marcadas como rejeitadas em comparação às mensagens enviadas. |
| **Processado/enviado** | Número total de envios para o delivery. |
| **Rejeição suave** | Número total de erros temporários, como uma caixa de entrada completa. |
| **Taxa de rejeição suave** | Número total de deliveries que falharam devido a motivos temporários em comparação a mensagens enviadas. |
| **Cliques únicos** | Número de recipients que clicaram em um conteúdo em um delivery. |
| **Aberturas exclusivas** | Número de recipients que abriram o delivery. |
| **Inscrições canceladas** | Número de cliques no link unsubscription. |
| **Taxa de cancelamento de inscrição** | Número total de unsubscriptions por recipient em comparação às mensagens entregues. |
