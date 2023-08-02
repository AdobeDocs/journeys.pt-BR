---
product: adobe campaign
title: Descrição da API de limite
description: Saiba mais sobre a API de limite.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 29%

---


# Trabalhar com a API de limite {#work}

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
>A variável **maxHttpConnections** é opcional. Ela permite restringir o número de conexões que o Journey Optimizer abrirá com o sistema externo.
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

Quando um **canDeploy** for chamado, o processo validará a configuração e retornará o status de validação identificado por seu identificador exclusivo:

```
"ok" or "error"
```

Os possíveis erros são:

* **ERR_ENDPOINTCONFIG_100**: configuração de limite: url ausente ou inválido
* **ERR_ENDPOINTCONFIG_101**: configuração de limite: url malformado
* **ERR_ENDPOINTCONFIG_102**: configuração de limitação: url malformado: curinga no url não permitido em host:port
* **ERR_ENDPOINTCONFIG_103**: configuração de limite: métodos HTTP ausentes
* **ERR_ENDPOINTCONFIG_104**: configuração de limite: nenhuma classificação de chamada definida
* **ERR_ENDPOINTCONFIG_107**: configuração de limitação: contagem máxima de chamadas inválida (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuração de limite: contagem máxima de chamadas inválida (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configuração de limite: não é possível criar a configuração do endpoint: carga inválida
* **ERR_ENDPOINTCONFIG_112**: configuração de limitação: não é possível criar a configuração de endpoint: espera de uma carga JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome de serviço inválido `<!--<given value>-->`: deve ser &quot;dataSource&quot; ou &quot;action&quot;

O aviso potencial é:

**ERR_ENDPOINTCONFIG_106**: configuração de limitação: máximo de conexões HTTP não definidas: sem limitação por padrão

## Casos de uso

Nesta seção, você encontrará os cinco principais casos de uso que podem ser executados para gerenciar a configuração de limite no [!DNL Journey Orchestration].

Para ajudá-lo nos testes e configurações, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta coleção do Postman foi estabelecida como um complemento da coleção variável do Postman gerada pela opção __[Integrações do console do Adobe I/O](https://console.adobe.io/integrations) > Experimente > Baixar para o Postman__, que gera um arquivo de ambiente do Postman com os valores das integrações selecionadas.

Após o download e o upload para o Postman, é necessário adicionar três variáveis: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : URL de gateway do [!DNL Journey Orchestration]
* `{BASE_PATH}` : ponto de entrada da API. O valor é “/authoring”
* `{SANDBOX_NAME}` : o cabeçalho **x-sandbox-name** (por exemplo, “prod”) correspondente ao nome da sandbox na qual as operações da API ocorrerão. Consulte a [visão geral das sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) para obter mais informações.

Na seção a seguir, você encontrará a lista ordenada de chamadas API REST para executar o caso de uso.

Caso de utilização n.º 1: **Criação e implantação de uma nova configuração de limite**

1. list
1. create
1. candeploy
1. deploy

Caso de uso n.º 2: **Atualizar e implantar uma configuração de limite ainda não implantada**

1. list
1. get
1. update
1. candeploy
1. deploy

Caso de utilização n.º 3: **Desimplantar e excluir uma configuração de limite implantada**

1. list
1. undeploy
1. delete

Caso de uso n.º 4: **Excluir uma configuração de limite implantada.**

Em apenas uma chamada de API, é possível desimplantar e excluir a configuração com o uso do parâmetro forceDelete.
1. list
1. delete, com o parâmetro forceDelete

Caso de utilização n.º 5: **Atualizar uma configuração de limite já implantada**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
