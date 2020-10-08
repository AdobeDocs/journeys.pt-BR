---
title: Descrição da API de limitação
description: Saiba mais sobre a API Capping.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 2%

---


# Trabalhar com a API de limite

## Introdução

[!DNL Journey Orchestration]As APIs do são compatíveis com 5000 eventos/segundos, mas alguns sistemas externos ou APIs não podem ter uma saída equivalente. É por isso que [!DNL Journey Orchestration] vem com um recurso dedicado chamado Capping API para monitorar e limitar a taxa que impomos aos sistemas externos.

Durante uma configuração de fonte de dados, você definirá uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas viagens ou para uma definição de ação, você configurará a conexão de um sistema de terceiros para enviar mensagens ou chamadas de API. Cada vez que uma chamada de API é executada pelo Journey, a API de limite é consultada, a chamada é enviada pelo mecanismo da API. Se houver um limite definido, a chamada será rejeitada e o sistema externo não será sobrecarregado.

Para saber mais sobre a ação ou a configuração da fonte de dados, consulte [Sobre ações](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) ou [Sobre fontes de dados](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Recursos

>[!NOTE]
>
>A API de [!DNL Journey Orchestration] Capping é descrita em um arquivo Swagger disponível [aqui](https://adobedocs.github.io/JourneyAPI/docs/).

Para usar essa API com sua [!DNL Journey Orchestration] instância, é necessário usar o Console de E/S da Adobe. Você pode start seguindo esta [Introdução ao Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) do desenvolvedor do Adobe e, em seguida, usar as seções desta página.

Para testar e preparar sua integração, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autenticação

### Configuração do acesso à API

[!DNL Journey Orchestration] O acesso à API é configurado pelas etapas abaixo. Cada uma dessas etapas está detalhada na documentação [de E/S do](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!CAUTION]
>
>Para gerenciar certificados na E/S do Adobe, verifique se você tem direitos de administrador <b>do</b> sistema na organização ou em uma conta [de](https://helpx.adobe.com/enterprise/using/manage-developers.html) desenvolvedor no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração com o[!DNL Journey Orchestration]Serviço** na E/S do Adobe e configure-a. O acesso ao perfil do produto é necessário para o e para o Adobe Experience Platform. [!DNL Journey Orchestration] Suas credenciais serão geradas (chave da API, segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias ao Adobe para verificar sua identidade e conceder acesso à API. Esta etapa está detalhada nesta [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um Token de acesso** por uma solicitação de POST ou pela interface do Developer Console. Esse Token de acesso deverá ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão segura de I/O Adobe de serviço a serviço, cada solicitação a um serviço de Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZAÇÃO>**: Esta é a ID pessoal da ORGANIZAÇÃO, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias:

   * &lt;ORGANIZAÇÃO> : sua instância de produção

   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la na E/S do Adobe ao criar uma nova integração, na lista de licenças (consulte a documentação <a href="https://www.adobe.io/authentication.html">de E/S do</a>Adobe).

* **&lt;ACCESS_TOKEN>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JWT por uma solicitação de POST.

* **&lt;API_KEY>**: sua chave de API pessoal. Ele é fornecido em E/S de Adobe após a criação de uma nova integração ao [!DNL Journey Orchestration] Serviço.



## Descrição da API de limitação

A API Capping ajuda a criar, configurar e monitorar suas configurações de capping.

| Método | Caminho | Descrição |
|---|---|---|
| [!DNL POST] | lista/endpointConfigs | Obtenha uma lista das configurações de limite de ponto final |
| [!DNL POST] | /endpointConfigs | Criar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/deplos | Implantar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeplos | Desimplantar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Verifique se uma configuração de limite de ponto de extremidade pode ser implantada ou não |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Atualizar uma configuração de limite de ponto de extremidade |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperar uma configuração de limite de ponto de extremidade |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Excluir uma configuração de limite de enpoint |

Quando uma configuração é criada ou atualizada, uma verificação é executada automaticamente para garantir a sintaxe e a integridade da carga.
Se ocorrerem alguns problemas, a operação retornará um aviso ou erros para ajudá-lo a corrigir a configuração.



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

Quando um método **canDeploy** é chamado, o processo valida a configuração e retorna o status de validação identificado pela ID exclusiva:

```
"ok" or "error"
```

Os possíveis erros são:

* **ERR_ENDPOINTCONFIG_100**: configuração de limite: url ausente ou inválido
* **ERR_ENDPOINTCONFIG_101**: configuração de limite: url malformado
* **ERR_ENDPOINTCONFIG_102**: configuração de limite: url malformado: wildchar no url não permitido em host:porta
* **ERR_ENDPOINTCONFIG_103**: configuração de limite: métodos HTTP ausentes
* **ERR_ENDPOINTCONFIG_104**: configuração de limite: nenhuma classificação de chamada definida
* **ERR_ENDPOINTCONFIG_107**: configuração de limite: contagem máxima de chamadas inválida (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuração de limite: contagem máxima de chamadas inválida (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configuração de limite: não é possível criar a configuração de ponto de extremidade: carga inválida
* **ERR_ENDPOINTCONFIG_112**: configuração de limite: não é possível criar a configuração de ponto de extremidade: esperando uma carga JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome de serviço inválido `<!--<given value>-->`: deve ser &#39;dataSource&#39; ou &#39;action&#39;


O aviso potencial é:

**ERR_ENDPOINTCONFIG_106**: configuração de limite: máx. de conexões HTTP não definidas: nenhuma limitação por padrão



## Casos de uso

Nesta seção, você encontrará os cinco principais casos de uso que podem ser executados para gerenciar a configuração de limite em [!DNL Journey Orchestration].

Para ajudá-lo em seus testes e configurações, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta Coleção Postman foi configurada para compartilhar a coleção Variável Postman gerada por meio de Integrações __[do Console de E/S do](https://console.adobe.io/integrations)Adobe > Testar > Baixar para Postman__, que gera um arquivo de Ambiente Postman com os valores de integrações selecionados.

Depois de baixado e carregado no Postman, é necessário adicionar três variáveis: `{JO_HOST}`,`{Base_Path}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL do gateway
* `{BASE_PATH}` : ponto de entrada para a API. O valor é &#39;/authoring&#39;
* `{SANDBOX_NAME}` : o cabeçalho **x-sandbox-name** (por exemplo, &#39;prod&#39;) correspondente ao nome da caixa de proteção onde as operações da API ocorrerão. Consulte a visão geral [das](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) caixas de proteção para obter mais informações.

Na seção a seguir, você encontrará a lista ordenada das chamadas da Rest API para executar o caso de uso.

Caso de uso n°1: **Criação e implantação de uma nova configuração de limite**

1. lista
1. create
1. canImplantação
1. implantação

Caso de uso n°2: **Atualizar e implantar uma configuração de limite ainda não implantada**

1. lista
1. get
1. update
1. canImplantação
1. implantação

Caso de uso n°3: **Desimplantar e excluir uma configuração de limite implantada**

1. lista
1. desimplantar
1. delete

Caso de uso n°4: **Exclua uma configuração de limite implantada.**

Em apenas uma chamada de API, você pode desimplantar e excluir a configuração usando o parâmetro forceDelete.
1. lista
1. delete, com forceDelete param

Caso de uso n°5: **Atualizar uma configuração de limite já implantada**

1. lista
1. get
1. update
1. desimplantar
1. canImplantação
1. implantação

