---
product: adobe campaign
title: Descrição da API de limite
description: Saiba mais sobre a API de limite.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 27%

---


# Trabalhar com a API de limite {#work}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


A API de limite ajuda a criar, configurar e monitorar as configurações de limite.

## Descrição da API de limite

| Método | Caminho | Descrição |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obter uma lista das configurações de limite de endpoint |
| [!DNL POST] | /endpointConfigs | Criar uma configuração de limite de endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Implantar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Desimplantar uma configuração de limite de endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Verificar se uma configuração de limite de ponto de extremidade pode ser implantada ou não |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Atualizar uma configuração de limite de ponto de extremidade |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperar uma configuração de limite de ponto de extremidade |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Excluir uma configuração de limite de ponto de extremidade |

Quando uma configuração é criada ou atualizada, uma verificação é executada automaticamente para garantir a sintaxe e a integridade do payload.
Se ocorrerem alguns problemas, a operação retornará um aviso ou erros para ajudá-lo a corrigir a configuração.

## Configuração do endpoint

Esta é a estrutura básica de uma configuração de endpoint:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>O parâmetro **maxHttpConnections** é opcional. Ela permite restringir o número de conexões que o Journey Optimizer abrirá com o sistema externo.
>
>O valor máximo que pode ser definido é 400. Se nada for especificado, o sistema poderá abrir até vários milhares de conexões, dependendo do dimensionamento dinâmico do sistema.

### Exemplo:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Aviso e erros

Quando um método **canDeploy** é chamado, o processo valida a configuração e retorna o status de validação identificado por sua Identificação Exclusiva:

```
"ok" or "error"
```

Os possíveis erros são:

* **ERR_ENDPOINTCONFIG_100**: configuração de limitação: url ausente ou inválida
* **ERR_ENDPOINTCONFIG_101**: configuração de limitação: url malformada
* **ERR_ENDPOINTCONFIG_102**: configuração de limitação: url malformada: caractere curinga em url não permitido em host:port
* **ERR_ENDPOINTCONFIG_103**: configuração de limitação: métodos HTTP ausentes
* **ERR_ENDPOINTCONFIG_104**: configuração de limitação: nenhuma classificação de chamada definida
* **ERR_ENDPOINTCONFIG_107**: configuração de limitação: contagem máxima inválida de chamadas (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuração de limitação: contagem máxima de chamadas inválida (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configuração de limitação: não é possível criar a configuração de ponto de extremidade: carga inválida
* **ERR_ENDPOINTCONFIG_112**: configuração de limitação: não é possível criar a configuração de ponto de extremidade: esperando uma carga JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome de serviço inválido `<!--<given value>-->`: deve ser &#39;dataSource&#39; ou &#39;action&#39;

O aviso potencial é:

**ERR_ENDPOINTCONFIG_106**: configuração de limitação: máximo de conexões HTTP não definidas: sem limitação por padrão

## Casos de uso

Nesta seção, você encontrará os cinco principais casos de uso que podem ser executados para gerenciar sua configuração de limitação no [!DNL Journey Orchestration].

Para ajudá-lo nos testes e configurações, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta coleção do Postman foi estabelecida como um complemento da coleção variável do Postman gerada pela opção __[Integrações do console do Adobe I/O](https://console.adobe.io/integrations) > Experimente > Baixar para o Postman__, que gera um arquivo de ambiente do Postman com os valores das integrações selecionadas.

Após o download e o upload para o Postman, é necessário adicionar três variáveis: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : URL de gateway do [!DNL Journey Orchestration]
* `{BASE_PATH}` : ponto de entrada da API. O valor é “/authoring”
* `{SANDBOX_NAME}` : o cabeçalho **x-sandbox-name** (por exemplo, “prod”) correspondente ao nome da sandbox na qual as operações da API ocorrerão. Consulte a [visão geral das sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) para obter mais informações.

Na seção a seguir, você encontrará a lista ordenada de chamadas API REST para executar o caso de uso.

Caso de uso nº 1: **Criação e implantação de uma nova configuração de limite**

1. list
1. create
1. candeploy
1. deploy

Caso de uso nº 2: **Atualizar e implantar uma configuração de limitação ainda não implantada**

1. list
1. get
1. update
1. candeploy
1. deploy

Caso de uso nº 3: **Desimplantar e excluir uma configuração de limite implantada**

1. list
1. undeploy
1. delete

Caso de uso nº 4: **Excluir uma configuração de limite implantada.**

Em apenas uma chamada de API, é possível desimplantar e excluir a configuração com o uso do parâmetro forceDelete.
1. list
1. delete, com o parâmetro forceDelete

Caso de uso n°5: **Atualizar uma configuração de limitação já implantada**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
