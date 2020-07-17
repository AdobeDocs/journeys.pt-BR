---
title: Métricas e dimensões
description: Saiba mais sobre dimensões e métricas disponíveis para o Journey Orchestration
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 2%

---


# Métricas e dimensões {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Os dados do Delivery só serão preenchidos se você tiver Adobe Campaign Standard.

Você pode encontrar aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.

A tabela abaixo apresenta a lista das dimensões usadas nos relatórios de jornada e suas definições.

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensões da viagem {#MBE_table_wk4_bnj_w2b}

A tabela abaixo apresenta a lista das dimensões usadas nos relatórios de jornada, suas definições e fórmulas.

| Dimensões | Definição |
|--- |--- |
| **Ação** | Lista de cada ação (nome da **ação - etiqueta** de ação) usada em viagens, por exemplo, Push - Confirmação de check-out, Email - Fidelidade de recompensas. |
| **Fonte de dados** | Lista de fontes de dados (nome **da fonte de** dados) usada para enriquecer dados em uma jornada, por exemplo, plataforma Adobe Experience, sistema de reserva. |
| **[!UICONTROL Event]** | Lista de todos os eventos (nome do **evento - etiqueta** do evento) utilizados em viagens, por exemplo, evento Geometrixx - Verificação Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (nome **do grupo de** campos) utilizados para enriquecer dados em viagens, por exemplo, grupo de campos do Perfil, sistema de reservas Geometrixx. |
| **Jornada** | Lista de cada viagem (nome **da** viagem) no modo de teste e viver, por exemplo, abandono do carrinho, notificação de reserva do hotel. |
| **Versão da jornada** | Lista de cada versão publicada de uma viagem (nome da **viagem + número** da versão), por exemplo, abandono do carrinho v1, notificação de reserva do hotel v2. |
| **Orquestração** | Lista de cada atividade de orquestração (**Condição, Final, Espera**) definida e usada em viagens. |

## Dimensões do Delivery {#delivery-dimensions}

A tabela abaixo apresenta a lista das dimensões do delivery usadas nos relatórios de jornada, suas definições e fórmulas.

| Dimensão | Definição |
|--- |--- |
| **Navegador** | Navegador no qual a mensagem foi aberta ou clicada. |
| **Nome do Delivery** | Rótulo e ID do delivery. |
| **Dispositivo** | Dispositivo a partir do qual a notificação por email/SMS/push foi aberta/visualizada/clicada. |
| **Tipo de mensagem** | Canal usado para o delivery, como email, SMS, notificação por push ou no aplicativo. |
| **Nome do aplicativo móvel** | Nome do aplicativo móvel |
| **Platform** | Platform do dispositivo a partir do qual a mensagem foi aberta/visualizada/clicada. |
| **[!UICONTROL Push platform]** | Platform do dispositivo a partir do qual a notificação por push foi aberta, como iOS ou Android. |
| **domínio do Recipient** | Domínio usado para abrir o email. |
| **URL de rastreamento** | URL clicado pelo usuário na mensagem. |
| **Rastreamento da categoria de URL** | Categoria atribuída ao URL de rastreamento. |
| **Rastreamento do rótulo do URL** | Rótulo fornecido ao URL, como mirror page, entre em contato conosco ou abra. |
| **Variante** | Variante do email no caso de teste A/B. |


## Métricas de jornada {#MBE_p_p22_c4j_w2b}

A tabela abaixo fornece a lista de métricas usadas em relatórios de jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |---|
| **Concluído** | O número total de indivíduos que terminaram normalmente a viagem. |
| **Taxa de conclusão** | O número total de indivíduos que terminaram a jornada normalmente em comparação ao número total de indivíduos que entraram na jornada. |
| **Atual** | O número total de indivíduos que estão atualmente na viagem, isto é, quantas pessoas entraram menos pessoas que saíram, erros e o tempo limite. |
| **Taxa atual** | O número total de indivíduos que atualmente se encontram na viagem em comparação com o número de indivíduos que entraram na viagem. |
| **Digitado** | O número total de eventos que ocorreram para start de uma entrada individual na viagem. |
| **Erro** | O número total de erros que ocorreram durante uma viagem, mas que não impediram o sucesso da viagem. |
| **Erro em ação** | Número total de erros que ocorreram para ações. |
| **Erro no Enriquecimento** | O número total de erros que ocorreram em um enriquecimento de dados ao chamar uma fonte de dados/grupo de campos. |
| **Erro no Evento** | Número total de erros que ocorreram para eventos. |
| **Taxa de Erro** | O número total de erros que ocorreram durante uma viagem em comparação com o número total de ocorrências na viagem. |
| **Ação executada** | O número total de ações executadas para uma jornada. |
| **Enriquecimento executado** | O número total de enriquecimentos executados ao chamar uma fonte de dados para obter grupos de campos específicos. |
| **Evento executado** | O número total de ações executadas para uma jornada. |
| **Orquestração executada** | O número total de objetos de orquestração (fim, espera, condição) executados para uma jornada. |
| **Failed** | O número total de viagens que não foram executadas com êxito. |
| **Taxa de falha** | O número total de viagens que não foram executadas com êxito em comparação com o número de viagens em curso. |

## Métricas de Delivery {#delivery-metrics}

A tabela abaixo fornece a lista de métricas usadas em relatórios de jornada, suas definições e fórmulas.

| Métrica | Definição |
|--- |--- |
| **Na lista de bloqueios** | Número de recipient que declararam um email como spam ou lixo eletrônico. |
| **taxa de Lista de bloqueios** | O número total de mensagens na lista de bloqueios em comparação às mensagens enviadas. |
| **Rejeições + erros** | Total de erros acumulados durante o processamento de retorno automático e delivery em relação ao número total de mensagens enviadas. |
| **Rejeição + taxa de erro** | O número total de mensagens que retornaram em comparação com as mensagens enviadas. |
| **Clique em** | Número de vezes que um conteúdo foi clicado em um delivery. |
| **Taxa de cliques** | O número total de cliques em um delivery em comparação ao número de mensagens entregues. |
| **Entregue** | Número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas. |
| **Taxa entregue** | O número total de mensagens entregues com êxito em comparação com as mensagens enviadas. |
| **Erro** | O número total de erros que ocorreram durante uma viagem, mas que não impediram o sucesso da viagem. |
| **Rejeição forçada** | O número total de erros permanentes, como um endereço de email incorreto. |
| **Taxa de rejeição em disco** | O número total de delivery que falharam devido a erros permanentes em comparação com as mensagens enviadas. |
| **Mirror page** | Número de recipient que clicaram no link do mirror page. |
| **taxa de Mirror page** | O número total de cliques no link do mirror page em comparação ao total de mensagens entregues. |
| **Abertura** | Número de vezes que uma mensagem foi aberta em um delivery. |
| **Taxa Aberta** | O número total de mensagens abertas em comparação ao número de mensagens entregues. |
| **Quarentena** | Número de mensagens que retornou e resultaram na quarentena do endereço. |
| **Taxa de Quarentena** | O número total de quarentenas em relação às mensagens enviadas. |
| **Rejeitada** | Número de mensagens classificadas como spam pelos servidores SMTP. |
| **taxa Rejeitada** | O número total de mensagens marcadas como rejeitadas em comparação com as mensagens enviadas. |
| **Processado/enviado** | Número total de envios para o delivery. |
| **Rejeição suave** | O número total de erros temporários, como uma caixa de entrada completa. |
| **Taxa de rejeição suave** | O número total de delivery que falharam devido ao motivo temporário em comparação com as mensagens enviadas. |
| **Cliques únicos** | Número de recipient que clicaram em um conteúdo em um delivery. |
| **Aberturas exclusivas** | Número de recipient que abriram o delivery. |
| **Inscrito** | Número de cliques no link unsubscription. |
| **Taxa de cancelamento de inscrição** | O número total de unsubscription por recipient em comparação às mensagens entregues. |
