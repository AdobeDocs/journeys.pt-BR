---
product: adobe campaign
solution: Journey Orchestration
title: Propriedades da jornada
description: Saiba mais sobre as propriedades de viagem
translation-type: tm+mt
source-git-commit: 341138c31676870878099b4f4eecec200a614c69
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 2%

---


# Propriedades da jornada {#journey-properties}

No editor avançado de expressões, você encontrará a categoria **Propriedades da jornada**, abaixo das categorias de evento e fonte de dados. Esta categoria contém campos técnicos relacionados à jornada de um determinado perfil. Esta é a informação obtida pelo sistema a partir de viagens em vida, como a identificação da viagem ou os erros específicos encontrados.

![](../assets/journey-properties.png)

Você encontrará informações, por exemplo, sobre:

* versão de viagem: uid de jornada, uid de versão de jornada, uid de instância, etc.
* erros: busca de dados, execução da ação etc.
* etapa atual, última etapa atual etc.
* perfis descartados

É possível usar esses campos para criar expressões. Durante a execução da jornada, os valores serão recuperados diretamente da jornada.

Estes são alguns exemplos de casos de uso:

* **Registrar perfis** descartados: você pode enviar todos os perfis excluídos de uma mensagem por uma regra de limite para um sistema de terceiros para fins de registro. Para isso, configure um caminho em caso de tempo limite e erro e adicione uma condição para filtrar em um tipo de erro específico, por exemplo: &quot;descarte as pessoas ao limitar a regra&quot;. Em seguida, é possível encaminhar os perfis descartados para um sistema de terceiros por meio de uma ação personalizada.

* **Enviar alertas em caso de erros**: você pode enviar uma notificação para um sistema de terceiros sempre que ocorrer um erro em uma mensagem. Para isso, configure um caminho em caso de erro, adicione uma condição e uma ação personalizada. Você pode enviar uma notificação em um canal Slack, por exemplo, com a descrição do erro encontrado.

* **Refinar erros no relatórios** : em vez de ter apenas um caminho para mensagens em erro, você pode definir uma condição por tipo de erro. Isso permitirá refinar o relatórios e visualização de todos os dados de tipos de erro.

## List of fields {#journey-properties-fields}

| Categoria | Nome do campo | Rótulo | Descrição |
|---|---|---|------------|
| Versão da jornada | jortUID | Identificador de jornada |  |
|  | jortVersionUID | Identificador da versão do diário |  |
|  | JourVersionName | Nome da versão da jornada |  |
|  | pathVersionDescription | Descrição da versão do diário |  |
|  | JourVersion | Versão da jornada |  |
| Instância de Jornada | instanceUID | Identificador de instância de jornada | ID da instância |
|  | externalKey | Chave externa | Identificador individual que desencadeia a viagem |
| Identidade | profileId | Identificador de identidade do perfil | Identificador do perfil na viagem |
|  | namespace | Namespace de identidade do perfil | Namespace do perfil na viagem (exemplo: ECID) |
| Nó atual | currentNodeId | Identificador de nó atual | Identificador da atividade atual (nó) |
|  | currentNodeName | Nome do nó atual | Nome da atividade atual (nó) |
| Nó anterior | previousNodeId | Identificador de nó anterior | Identificador da atividade anterior (nó) |
|  | previousNodeName | Nome do nó anterior | Nome da atividade anterior (nó) |
| Erros | lastNodeUIDInError | Identificador do último nó em erro | Identificador da atividade mais recente (nó) em erro |
|  | lastNodeNameInError | Nome do último nó no erro | Nome da atividade mais recente (nó) no erro |
|  | lastNodeTypeInError | Último tipo de nó em erro | Tipo de erro da atividade mais recente (nó) em erro. Tipos possíveis:<ul><li>Eventos: Eventos, Reações, SQ (exemplo: Qualificação do segmento)</li><li>Controlo de fluxo: End, Condition, Wait</li><li>Ações: Ações ACS, Jump, Ação personalizada</li></ul> |
|  | lastErrorCode | Último código de erro | Erro no código de erro da atividade mais recente (nó). Possíveis erros: <ul><li>Códigos de erro HTTP</li><li>limitado</li><li>timedOut</li><li>error (por exemplo: padrão no caso de um erro inesperado. Não deveria/extremamente raramente)</li></ul> |
|  | lastExecutedActionErrorCode | Código de erro da última ação executada | Código de erro da ação mais recente em erro |
|  | lastDataFetchErrorCode | Código de erro da última busca de dados | Código de erro da busca de dados mais recente de fontes de dados |
| Hora | lastActionExecutionElapsedTime | Tempo decorrido da última execução da ação | Tempo gasto para executar a ação mais recente |
|  | lastDataFetchElapsedTime | Tempo decorrido da última busca de dados | Tempo gasto para executar a busca de dados mais recente a partir de fontes de dados |
