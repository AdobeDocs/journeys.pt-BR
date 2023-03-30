---
product: adobe campaign
title: Limitação da descrição da API
description: Saiba mais sobre a API de limitação.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# Trabalhar com a API de limitação {#work}

A API de limitação ajuda a criar, configurar e monitorar as configurações de limitação.

## Limitação da descrição da API

| Método | Path | Descrição |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obter uma lista das configurações de limite do ponto de extremidade |
| [!DNL POST] | /endpointConfigs | Criar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/implantar | Implantar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Desimplantar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Verifique se uma configuração de limite de ponto de extremidade pode ser implantada ou não |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Atualizar uma configuração de limite de ponto de extremidade |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperar uma configuração de limite de ponto de extremidade |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Excluir uma configuração de limite de ponto de extremidade |

Quando uma configuração é criada ou atualizada, uma verificação é executada automaticamente para garantir a sintaxe e a integridade do payload.
Se ocorrerem alguns problemas, a operação retornará um aviso ou erros para ajudar você a corrigir a configuração.

## Configuração do terminal

Esta é a estrutura básica de uma configuração de ponto de extremidade:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Exemplo:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Aviso e erros

Quando uma **canDeploy** é chamado, o processo valida a configuração e retorna o status de validação identificado por sua ID exclusiva:

```
"ok" or "error"
```

Os possíveis erros são:

* **ERR_ENDPOINTCONFIG_100**: configuração de limitação: url ausente ou inválido
* **ERR_ENDPOINTCONFIG_101**: configuração de limitação: url malformado
* **ERR_ENDPOINTCONFIG_102**: configuração de limitação: url malformado: wildchar no url não permitido em host:port
* **ERR_ENDPOINTCONFIG_103**: configuração de limitação: métodos HTTP ausentes
* **ERR_ENDPOINTCONFIG_104**: configuração de limitação: sem classificação de chamada definida
* **ERR_ENDPOINTCONFIG_107**: configuração de limitação: contagem máxima de chamadas inválida (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuração de limitação: contagem máxima de chamadas inválida (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configuração de limitação: não é possível criar a configuração do ponto de extremidade: carga inválida
* **ERR_ENDPOINTCONFIG_112**: configuração de limitação: não é possível criar a configuração do ponto de extremidade: esperando uma carga JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome de serviço inválido `<!--<given value>-->`: deve ser &#39;dataSource&#39; ou &#39;action&#39;

O possível aviso é:

**ERR_ENDPOINTCONFIG_106**: configuração de limitação: conexões HTTP máximas não definidas: sem limitação por defeito

## Casos de uso

Nesta seção, você encontrará os cinco principais casos de uso que podem ser executados para gerenciar a configuração de limitação no [!DNL Journey Orchestration].

Para ajudá-lo nos testes e configurações, uma coleção do Postman está disponível [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta coleção Postman foi configurada para compartilhar a coleção Variável Postman gerada por __[Integrações do console do Adobe I/O](https://console.adobe.io/integrations) > Experimente > Baixar para Postman__, que gera um arquivo de Ambiente Postman com os valores de integrações selecionados.

Após o download e o upload para o Postman, é necessário adicionar três variáveis: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL do gateway
* `{BASE_PATH}` : ponto de entrada para a API. O valor é &#39;/authoring&#39;
* `{SANDBOX_NAME}` : o cabeçalho **x-sandbox-name** (por exemplo, &quot;prod&quot;) correspondente ao nome da caixa de proteção onde as operações da API ocorrerão. Consulte a [visão geral das sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) para obter mais informações.

Na seção a seguir, você encontrará a lista ordenada Rest API calls para executar o caso de uso.

Caso de uso n°1: **Criação e implantação de uma nova configuração de limitação**

1. listar
1. criar
1. pode implantar
1. implantar

Caso de uso n°2: **Atualizar e implantar uma configuração de limitação ainda não implantada**

1. listar
1. get
1. atualizar
1. pode implantar
1. implantar

Caso de uso n° 3: **Desimplantar e excluir uma configuração de limite implantada**

1. listar
1. cancelar implantação
1. excluir

Caso de uso n°4: **Exclua uma configuração de limite implantada.**

Em apenas uma chamada de API, é possível desimplantar e excluir a configuração com o uso do parâmetro forceDelete.
1. listar
1. excluir, com o parâmetro forceDelete

Caso de uso n°5: **Atualizar uma configuração de limitação já implantada**

1. listar
1. get
1. atualizar
1. cancelar implantação
1. pode implantar
1. implantar
