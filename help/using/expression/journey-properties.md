---
product: adobe campaign
solution: Journey Orchestration
title: Propriedades da viagem
description: Saiba mais sobre as propriedades de viagem
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Propriedades da viagem {#journey-properties}

No editor avançado de expressões, você encontrará a categoria Propriedades **da** jornada, abaixo do evento e das categorias da fonte de dados. Esta categoria contém campos técnicos relacionados à jornada de um determinado perfil. Esta é a informação obtida pelo sistema a partir de viagens em vida, como a identificação da viagem ou os erros específicos encontrados.

![](../assets/journey-properties.png)

Você encontrará informações, por exemplo, sobre:

* versão de viagem: uid de jornada, uid de versão de jornada, uid de instância, etc.
* erros: busca de dados, execução da ação etc.
* etapa atual, última etapa atual etc.
* perfis descartados

É possível usar esses campos para criar expressões. Durante a execução da jornada, os valores serão recuperados diretamente da jornada.

Estes são alguns exemplos de casos de uso:

* **Registrar perfis** descartados: você pode enviar todos os perfis excluídos de uma mensagem por uma regra de limite para um sistema de terceiros para fins de registro. Para isso, configure um caminho em caso de tempo limite e erro e adicione uma condição para filtrar em um tipo de erro específico, por exemplo: &quot;descarte as pessoas ao limitar a regra&quot;. Em seguida, é possível encaminhar os perfis descartados para um sistema de terceiros por meio de uma ação personalizada.

* **Alertas de push enviados em caso de erros**: você pode enviar uma notificação para um sistema de terceiros sempre que ocorrer um erro em uma mensagem. Para isso, configure um caminho em caso de erro, adicione uma condição e uma ação personalizada. Você pode enviar uma notificação em um canal Slack, por exemplo, com a descrição do erro encontrado.

* **Refinar erros no relatórios** : em vez de ter apenas um caminho para mensagens em erro, você pode definir uma condição por tipo de erro. Isso permitirá refinar o relatórios e visualização de todos os dados de tipos de erro.

## List of fields {#journey-properties-fields}

|Categoria|Nome do campo|Rótulo|Descrição|
|-|-|-|—
|Versão da jornada|ID da jornada|Identificador da jornada| |
| |Identificação da Versão de Viagem|ID de Id de Versão de Viagem| |
| |JourneyVersionName|Nome da Versão da Jornada| |
| |descrição de JourneyVersion|Descrição de versão de jornada| |
| |JourneyVersion|Versão da jornada| |
|Instância de jornada|instanceUID|Identificador de instância de jornada|ID da instância|
| |externalKey|Chave externa|Identificador individual que aciona a viagem|
|Identidade|profileId|Identificador de identidade do Perfil|Identificador do perfil na jornada|
| |namespace|Namespace de identificação do Perfil|Namespace do perfil na jornada (por exemplo: ECID)|
|Nó atual|currentNodeId|Identificador de nó atual|Identificador da atividade atual (nó)|
| |currentNodeName|Nome do nó atual|Nome da atividade atual (nó)|
|Nó anterior|previousNodeId|Identificador de nó anterior|Identificador da atividade anterior (nó)|
| |previousNodeName|Nome do nó anterior|Nome da atividade anterior (nó)|
|Erros|lastNodeUIDInErro|Identificador do último nó em Erro|Identificador da última atividade (nó) em erro|
| |lastNodeNameInError|Last Node Name in Error|Name of the latest atividade (node) in error|
| |lastNodeTypeInError|Last Node Type in Error|Tipo de erro da mais recente atividade (nó) com erro. Tipos possíveis:<ul><li>Eventos: Eventos, Reações, SQ (exemplo: Qualificação do segmento)</li><li>Controlo de fluxo: End, Condition, Wait</li><li>Ações: Ações ACS, Jump, Ação personalizada</li></ul>|
| |lastErrorCode|Last Error Code|Error code of the latest atividade (node) in error (Código do último erro). Possíveis erros: <ul><li>Códigos de erro HTTP</li><li>limitado</li><li>timedOut</li><li>error (por exemplo: padrão no caso de um erro inesperado. Não deveria/extremamente raramente)</li></ul>|
| |lastExecutedActionErrorCode|Código de erro da última ação executada|Código de erro da última ação em erro |
| |lastDataFetchErrorCode|Código de Erro da Última Busca de Dados|Código de erro da busca de dados mais recente a partir de fontes de dados|
|Time|lastActionExecutionElapsedTime|Tempo decorrido da última execução da ação|Tempo gasto para executar a ação mais recente|
| |lastDataFetchElapsedTime|Tempo decorrido da última busca de dados|Tempo gasto para executar a busca de dados mais recente a partir de fontes de dados|
