---
title: Métricas e dimensões
description: Saiba mais sobre as dimensões e métricas disponíveis para o Journey Orchestration
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Métricas e dimensões {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Os dados de entrega só serão preenchidos se você tiver o Adobe Campaign Standard.

Você pode encontrar aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.

A tabela abaixo apresenta a lista de dimensões usadas nos relatórios de jornada e suas definições.

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensões da viagem {#MBE_table_wk4_bnj_w2b}

A tabela abaixo fornece a lista de dimensões usadas nos relatórios de jornada, suas definições e fórmulas.

| Dimensões | Definição |
|--- |--- |
| **Ação** | Lista de todas as ações (nome da **ação - etiqueta** de ação) usadas em viagens, por exemplo, Push - Confirmação de check-out, Email - Fidelidade de recompensas. |
| **Fonte de dados** | Lista das fontes de dados (nome **da fonte de** dados) usadas para enriquecer dados em uma jornada, por exemplo, plataforma de experiência, sistema de reserva. |
| **[!UICONTROL Event]** | Lista de todos os eventos (nome do **evento - rótulo** do evento) usados em viagens, por exemplo, evento Geometrixx - Check-out do Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (nome **do grupo de** campos) utilizados para enriquecer dados em viagens, por exemplo, grupo de campos de perfil, sistema de reservas Geometrixx. |
| **Jornada** | Lista de todas as viagens (nome **da** viagem) em modo de teste e viver, por exemplo, abandono do carrinho, notificação de reserva de hotel. |
| **Versão da jornada** | Lista de todas as versões publicadas de uma viagem (nome da **viagem + número** da versão), por exemplo, abandono do carrinho v1, notificação de reserva do hotel v2. |
| **Orquestração** | Lista de todas as atividades de orquestração (**Condição, Final, Espera**) definidas e usadas em viagens. |

## Dimensões de entrega {#delivery-dimensions}

A tabela abaixo apresenta a lista de dimensões de entrega usadas em relatórios de jornada, suas definições e fórmulas.

| Dimensão | Definição |
|--- |--- |
| **Navegador** | Navegador no qual a mensagem foi aberta ou clicada. |
| **Nome da entrega** | Rótulo e ID da entrega. |
| **Dispositivo** | Dispositivo a partir do qual a notificação por email/SMS/push foi aberta/visualizada/clicada. |
| **Tipo de mensagem** | Canal usado para a entrega, como email, SMS, notificação por push ou no aplicativo. |
| **Nome do aplicativo móvel** | Nome do aplicativo móvel |
| **Plataforma** | Plataforma do dispositivo a partir do qual a mensagem foi aberta/visualizada/clicada. |
| **[!UICONTROL Push platform]** | Plataforma do dispositivo a partir do qual a notificação por push foi aberta, como iOS ou Android. |
| **Domínio do destinatário** | Domínio usado para abrir o email. |
| **URL de rastreamento** | URL clicado pelo usuário na mensagem. |
| **Rastrear categoria de URL** | Categoria atribuída ao URL de rastreamento. |
| **Rastreamento do rótulo do URL** | Rótulo fornecido ao URL, como página espelhada, entre em contato conosco ou abra. |
| **Variante** | Variante do email no caso de teste A/B. |


## Métricas de jornada {#MBE_p_p22_c4j_w2b}

A tabela abaixo fornece a lista de métricas usadas em relatórios de jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |---|
| **Concluído** | O número total de indivíduos que terminaram normalmente a viagem. |
| **Taxa de conclusão** | O número total de indivíduos que terminaram normalmente a viagem em comparação ao número total de indivíduos que entraram na viagem. |
| **Atual** | O número total de indivíduos que estão atualmente na viagem, isto é, quantas pessoas entraram menos pessoas que saíram, erros e o tempo limite. |
| **Taxa atual** | O número total de indivíduos que atualmente se encontram na viagem em comparação com o número de indivíduos que entraram na viagem. |
| **Digitado** | Número total de eventos que ocorreram para iniciar uma entrada individual na jornada. |
| **Erro** | O número total de erros que ocorreram durante uma viagem, mas que não impediram o sucesso da viagem. |
| **Erro em ação** | Número total de erros que ocorreram para ações. |
| **Erro no enriquecimento** | O número total de erros que ocorreram para um enriquecimento de dados ao chamar uma fonte de dados/grupo de campos. |
| **Erro no evento** | Número total de erros que ocorreram para eventos. |
| **Taxa de Erro** | O número total de erros que ocorreram durante uma viagem em comparação com o número total de ocorrências na viagem. |
| **Ação executada** | O número total de ações executadas para uma jornada. |
| **Enriquecimento executado** | O número total de aprimoramentos executados ao chamar uma fonte de dados para obter grupos de campos específicos. |
| **Evento executado** | O número total de ações executadas para uma jornada. |
| **Orquestração executada** | O número total de objetos de orquestração (fim, espera, condição) executados para uma jornada. |
| **Failed** | Número total de viagens que não foram executadas com êxito. |
| **Taxa de falha** | O número total de viagens que não foram executadas com êxito em comparação com o número de viagens em curso. |

## Métricas de entrega {#delivery-metrics}

A tabela abaixo fornece a lista de métricas usadas em relatórios de jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |--- |
| **Lista negra** | Número de destinatários que declararam um email como spam ou lixo eletrônico. |
| **Taxa da lista negra** | O número total de mensagens marcadas como proibidas em comparação às mensagens enviadas. |
| **Rejeições + erros** | Total de erros acumulados durante a entrega e o processamento automático de retorno em relação ao número total de mensagens enviadas. |
| **Rejeição + taxa de erro** | O número total de mensagens que retornaram em comparação com as mensagens enviadas. |
| **Clique em** | Número de vezes que um conteúdo foi clicado em uma entrega. |
| **Taxa de cliques** | O número total de cliques em uma entrega em comparação ao número de mensagens entregues. |
| **Entregue** | Número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas. |
| **Taxa entregue** | O número total de mensagens entregues com êxito em comparação com as mensagens enviadas. |
| **Erro** | O número total de erros que ocorreram durante uma viagem, mas que não impediram o sucesso da viagem. |
| **Rejeição forçada** | O número total de erros permanentes, como um endereço de email incorreto. |
| **Taxa de rejeição em disco** | Número total de entregas que falharam devido a erros permanentes em comparação com as mensagens enviadas. |
| **Página de espelhamento** | Número de destinatários que clicaram no link da página espelhada. |
| **Taxa de páginas espelhadas** | O número total de cliques no link da página espelhada em comparação ao total de mensagens entregues. |
| **Abertura** | Número de vezes que uma mensagem foi aberta em uma entrega. |
| **Taxa Aberta** | O número total de mensagens abertas em comparação ao número de mensagens entregues. |
| **Quarentena** | Número de mensagens que retornou e resultaram na quarentena do endereço. |
| **Taxa de quarentena** | O número total de quarentena em comparação às mensagens enviadas. |
| **Rejeitada** | Número de mensagens classificadas como spam pelos servidores SMTP. |
| **Taxa de rejeição** | O número total de mensagens marcadas como rejeitadas em comparação com as mensagens enviadas. |
| **Processado/enviado** | O número total de envios para a entrega. |
| **Rejeição suave** | Número total de erros temporários, como uma caixa de entrada completa. |
| **Taxa de rejeição suave** | Número total de entregas que falharam devido a motivo temporário em comparação com as mensagens enviadas. |
| **Cliques únicos** | Número de destinatários que clicaram em um conteúdo em uma entrega. |
| **Aberturas exclusivas** | Número de destinatários que abriram a entrega. |
| **Inscrito** | Número de cliques no link unsubscription. |
| **Taxa de cancelamento de inscrição** | Número total de cancelamentos de assinaturas por destinatário em comparação às mensagens entregues. |
