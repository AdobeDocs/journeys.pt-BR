---
product: adobe campaign
title: Propriedades da jornada
description: Saiba mais sobre as propriedades do jornada
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 6%

---

# Jornada atributos de propriedades {#journey-properties}

No editor de expressão avançado, você encontrará a variável **Propriedades da Jornada** , abaixo das categorias evento e fonte de dados. Esta categoria contém campos técnicos relacionados à jornada de um determinado perfil. Essas são as informações recuperadas pelo sistema a partir das jornadas ativas, como a ID da jornada ou os erros específicos encontrados.

>[!NOTE]
>
>Os atributos de propriedades da jornada também estão disponíveis no editor de expressões simples. Consulte esta [seção](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

Você encontrará informações, por exemplo, sobre:

* Versão do jornada: Uid do jornada, uid da versão do jornada, uid da instância etc.
* erros: busca de dados, execução de ação etc.
* etapa atual, última etapa atual etc.
* perfis descartados

Você pode usar esses campos para criar expressões. Durante a execução da jornada, os valores serão recuperados diretamente da jornada.

Veja alguns exemplos de casos de uso:

* **Registrar perfis descartados**: é possível enviar todos os perfis excluídos de uma mensagem por uma regra de limitação para um sistema de terceiros para fins de registro. Para isso, configure um caminho em caso de tempo limite e erro e adicione uma condição para filtrar em um tipo de erro específico, por exemplo: &quot;descartar as pessoas ao limitar a regra&quot;. Em seguida, é possível enviar os perfis descartados para um sistema de terceiros por meio de uma ação personalizada.

* **Enviar alertas em caso de erros**: você pode enviar uma notificação para um sistema de terceiros sempre que ocorrer um erro em uma mensagem. Para isso, configure um caminho em caso de erro, adicione uma condição e uma ação personalizada. Você pode enviar uma notificação em um canal de Slack, por exemplo, com a descrição do erro encontrado.

* **Refinar erros nos relatórios** : em vez de ter apenas um caminho para mensagens com erro, você pode definir uma condição por tipo de erro. Isso permitirá refinar os relatórios e exibir todos os dados de tipos de erro.

## List of fields {#journey-properties-fields}

| Categoria | Nome do campo | Rótulo | Descrição |
|---|---|---|------------|
| Versão do Jornada | journeyUID | Identificador de jornada |  |
|  | journeyVersionUID | Identificador de versão do Jornada |  |
|  | journeyVersionName | Nome da versão do Jornada |  |
|  | journeyVersionDescription | Descrição da versão do Jornada |  |
|  | journeyVersion | Versão do Jornada |  |
| Instância do Jornada | instanceUID | Identificador de Instância do Jornada | ID da instância |
|  | externalKey | Chave externa | Identificador individual que aciona a jornada |
|  | organizationId | Identificador da organização | Organização da marca |
|  | sandboxName | Nome da sandbox | Nome da sandbox |
| Identidade | profileId | Identificador de identidade do perfil | Identificador do perfil na jornada |
|  | namespace | Namespace de identidade do perfil | Namespace do perfil na jornada (exemplo: ECID) |
| Nó atual | currentNodeId | Identificador de nó atual | Identificador da atividade atual (nó) |
|  | currentNodeName | Nome do nó atual | Nome da atividade atual (nó) |
| Nó anterior | previousNodeId | Identificador de nó anterior | Identificador da atividade anterior (nó) |
|  | previousNodeName | Nome do nó anterior | Nome da atividade anterior (nó) |
| Erros | lastNodeUIDInError | Último identificador de nó no erro | Identificador da atividade mais recente (nó) com erro |
|  | lastNodeNameInError | Nome do último nó no erro | Nome da atividade mais recente (nó) com erro |
|  | lastNodeTypeInError | Último tipo de nó no erro | Tipo de erro da atividade mais recente (nó) com erro. Tipos possíveis:<ul><li>Eventos: Eventos, Reações, SQ (exemplo: Qualificação do segmento)</li><li>Controle de fluxo: End, Condition, Wait</li><li>Ações: Ações ACS, Jump, Custom Action</li></ul> |
|  | lastErrorCode | Último código de erro | Erro no código de erro da atividade mais recente (nó). Possíveis erros: <ul><li>Códigos de erro HTTP</li><li>limitado</li><li>timedOut</li><li>erro (exemplo: padrão no caso de um erro inesperado. Não deveria/extremamente raramente acontecer)</li></ul> |
|  | lastExecutedActionErrorCode | Código de erro da última ação executada | Código de erro da ação mais recente com erro |
|  | lastDataFetchErrorCode | Código de erro da última busca de dados | Código de erro da busca de dados mais recente a partir de fontes de dados |
| Hora | lastActionExecutionElapsedTime | Tempo decorrido da execução da última ação | Tempo gasto para executar a ação mais recente |
|  | lastDataFetchElapsedTime | Tempo decorrido da última busca de dados | Tempo gasto para executar a busca de dados mais recente a partir de fontes de dados |
