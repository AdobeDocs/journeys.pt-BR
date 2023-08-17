---
product: adobe campaign
title: Métricas e dimensões
description: Saiba mais sobre dimensões e métricas disponíveis para o Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 6%

---

# Métricas e dimensões {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Os dados de delivery só serão preenchidos se você tiver o Adobe Campaign Standard.

Aqui você pode encontrar a lista de todos os componentes disponíveis nos Relatórios dinâmicos, bem como suas definições.

A tabela abaixo fornece a lista de dimensões usadas nos relatórios do jornada e suas definições.

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Jornada dimensões {#MBE_table_wk4_bnj_w2b}

A tabela abaixo fornece a lista de dimensões usadas nos relatórios do jornada, suas definições e fórmulas.

| Dimensões | Definição |
|--- |--- |
| **Ação** | Lista de todas as ações (**nome da ação - rótulo da ação**) usado em jornadas, por exemplo, push - confirmação de check-out, email - fidelidade de recompensas. |
| **Fonte de dados** | Lista de fontes de dados (**nome da fonte de dados**) usado para enriquecer dados em uma jornada, por exemplo, Adobe Experience Platform, Sistema de reserva. |
| **[!UICONTROL Event]** | Lista de todos os eventos (**nome do evento - rótulo do evento**) usado no jornada, por exemplo, Geometrixx event - Geometrixx check-out. |
| **Grupo de campos** | Lista de grupos de campos (**nome do grupo de campos**) usado para enriquecer dados no jornada, por exemplo: grupo de campos de perfil, sistema de reservas do Geometrixx. |
| **Jornada** | Lista de cada jornada (**Nome da jornada**) no modo de teste e ao vivo, por exemplo, abandono do carrinho, notificação de reserva do hotel. |
| **Versão do Jornada** | Lista de cada versão publicada de uma jornada (**Nome da jornada + número da versão**) por exemplo: Abandono do carrinho v1, Notificação de reserva de hotel v2. |
| **Orquestração** | Lista de cada atividade de orquestração (**Condição, Fim, Espera**) definido e usado em jornadas. |

## Dimensões de entrega {#delivery-dimensions}

A tabela abaixo fornece a lista de dimensões de entrega usadas nos relatórios do jornada, suas definições e fórmulas.

| Dimensão | Definição |
|--- |--- |
| **Navegador** | Navegador no qual a mensagem foi aberta ou clicada. |
| **Nome da entrega** | Etiqueta e ID da entrega. |
| **Dispositivo** | Dispositivo no qual o email/SMS/notificação por push foi aberto/exibido/clicado. |
| **Tipo de mensagem** | Canal usado para a entrega, como email, SMS, notificação por push ou no aplicativo. |
| **Nome do aplicativo móvel** | Nome do aplicativo móvel |
| **Plataforma** | Plataforma do dispositivo do qual a mensagem foi aberta/exibida/clicada. |
| **[!UICONTROL Push platform]** | Plataforma do dispositivo do qual a notificação por push foi aberta, como iOS ou Android. |
| **Domínio do destinatário** | Domínio usado para abrir o email. |
| **URL de rastreamento** | URL no qual o usuário clicou a partir da mensagem. |
| **Categoria de URL de rastreamento** | Categoria atribuída ao URL de rastreamento. |
| **Rótulo do URL de rastreamento** | Rótulo fornecido ao URL, como mirror page, entre em contato conosco ou abra. |
| **Variante** | Variante do email em caso de teste A/B. |

## Jornada métricas {#MBE_p_p22_c4j_w2b}

A tabela abaixo fornece a lista de métricas usadas nos relatórios do jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |---|
| **Concluído** | Número total de indivíduos que encerraram normalmente a jornada. |
| **Taxa de conclusão** | Número total de indivíduos que encerraram normalmente a jornada em comparação ao número total de indivíduos que entraram na jornada. |
| **Atual** | Número total de indivíduos atualmente na jornada, ou seja, quantas pessoas entraram menos as pessoas que saíram, erros e tempo limite atingido. |
| **Taxa atual** | Número total de indivíduos atualmente na jornada em comparação ao número de indivíduos que entraram na jornada. |
| **Inserido** | Número total de eventos que ocorreram para iniciar uma entrada individual na jornada. |
| **Erro** | Número total de erros que ocorreram durante uma jornada, mas que não impediram que a jornada fosse bem-sucedida. |
| **Erro na ação** | Número total de erros que ocorreram para ações. |
| **Erro no enriquecimento** | Número total de erros que ocorreram para um enriquecimento de dados ao chamar uma fonte de dados/grupo de campos. |
| **Erro no evento** | Número total de erros que ocorreram para eventos. |
| **Taxa de erros** | Número total de erros que ocorreram durante uma jornada em comparação ao número total de ocorrências na jornada. |
| **Ação executada** | Número total de ações executadas para uma jornada. |
| **Enriquecimento executado** | Número total de enriquecimentos executados ao chamar uma fonte de dados para obter grupos de campos específicos. |
| **Evento Executado** | Número total de ações executadas para uma jornada. |
| **Orquestração executada** | Número total de objetos de orquestração (fim, espera, condição) executados para uma jornada. |
| **Falha** | Número total de jornadas que não foram executadas com êxito. |
| **Taxa de falhas** | Número total de jornadas que não foram executadas com êxito em comparação ao número de jornadas executadas. |

## Métricas de entrega {#delivery-metrics}

A tabela abaixo fornece a lista de métricas usadas nos relatórios do jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |--- |
| **Na lista de bloqueios** | Número de destinatários que declararam um email como spam ou lixo eletrônico. |
| **Taxa de Lista de bloqueios** | Número total de mensagens na inclui na lista de bloqueios comparadas às mensagens enviadas. |
| **Devoluções + erros** | Total de erros acumulados durante o processamento de entrega e retorno automático em relação ao número total de mensagens enviadas. |
| **Rejeição + taxa de erro** | Número total de mensagens que foram rejeitadas em comparação às mensagens enviadas. |
| **Clique em** | Número de vezes que um conteúdo foi clicado em um delivery. |
| **Taxa de cliques** | Número total de cliques em um delivery em comparação ao número de mensagens entregues. |
| **Entregues** | Número de mensagens enviadas com êxito em relação ao número total de mensagens enviadas. |
| **Taxa de entregas** | Número total de mensagens entregues com êxito em comparação às mensagens enviadas. |
| **Erro** | Número total de erros que ocorreram durante uma jornada, mas que não impediram que a jornada fosse bem-sucedida. |
| **Rejeição permanente** | Número total de erros permanentes, como um endereço de email incorreto. |
| **Taxa de rejeição permanente** | Número total de entregas que falharam devido a erros permanentes em comparação às mensagens enviadas. |
| **Mirror page** | Número de destinatários que clicaram no link da mirror page. |
| **Taxa de mirror pages** | Número total de cliques no link da mirror page em comparação ao total de mensagens entregues. |
| **Abrir** | Número de vezes que uma mensagem foi aberta em um delivery. |
| **Taxa de abertura** | Número total de mensagens abertas em comparação ao número de mensagens entregues. |
| **Quarentena** | Número de mensagens que foram rejeitadas e resultaram na quarentena do endereço. |
| **Taxa de quarentena** | Número total de quarentenas em comparação às mensagens enviadas. |
| **Rejeitado** | Número de mensagens classificadas como spam pelos servidores SMTP. |
| **Taxa de rejeições** | Número total de mensagens marcadas como rejeitadas em comparação às mensagens enviadas. |
| **Processado/enviado** | Número total de envios para a entrega. |
| **Rejeição leve** | Número total de erros temporários, como uma caixa de entrada cheia. |
| **Taxa de rejeição temporária** | Número total de entregas que falharam por motivo temporário em comparação às mensagens enviadas. |
| **Cliques únicos** | Número de recipients que clicaram em um conteúdo em um delivery. |
| **Aberturas únicas** | Número de destinatários que abriram o delivery. |
| **Inscrições canceladas** | Número de cliques no link unsubscription. |
| **Taxa de cancelamento de inscrição** | Número total de cancelamentos de subscrições por recipient em comparação às mensagens entregues. |
