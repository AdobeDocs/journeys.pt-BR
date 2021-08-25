---
product: adobe campaign
title: Limitação da descrição da API
description: Saiba mais sobre a API de limitação.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 4%

---

# Como trabalhar com a API de limitação

## Introdução

[!DNL Journey Orchestration]As APIs do são compatíveis com 5000 eventos/segundos, mas alguns sistemas externos ou APIs não poderiam ter uma taxa de transferência equivalente. É por isso que [!DNL Journey Orchestration] vem com um recurso dedicado chamado API de limitação para monitorar e limitar a taxa que impomos a sistemas externos.

Durante uma configuração de fonte de dados, você definirá uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas ou para uma definição de ação, você configurará a conexão de um sistema de terceiros para enviar mensagens ou chamadas de API. Sempre que uma chamada de API é executada pelo Jornada, a API de limitação é consultada, a chamada é enviada pelo mecanismo de API. Se houver um limite definido, a chamada será rejeitada e o sistema externo não será sobrecarregado.

Para fontes de dados externas, o número máximo de chamadas por segundo é definido como 15. Se o número de chamadas exceder 15 por segundo, as chamadas restantes serão descartadas. É possível aumentar esse limite para fontes de dados externas privadas. Entre em contato com o Adobe para incluir o ponto de extremidade na  de lista de permissões. Isso não é possível para fontes de dados externas públicas. Para saber mais sobre as práticas recomendadas e as medidas de proteção ao integrar sistemas externos, consulte esta [página](../about/external-systems.md).

Para saber mais sobre a ação ou a configuração da fonte de dados, consulte [Sobre ações](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) ou [Sobre fontes de dados](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## Recursos

>[!NOTE]
>
>A [!DNL Journey Orchestration] API de limitação é descrita em um arquivo Swagger disponível [aqui](https://adobedocs.github.io/JourneyAPI/docs/).

Para usar essa API com sua instância [!DNL Journey Orchestration], é necessário usar o Console do Adobe I/O. Você pode começar seguindo este [Introdução ao Console do Desenvolvedor do Adobe](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e usar as seções nesta página.

Para testar e preparar sua integração, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autenticação

### Configuração do acesso à API

[!DNL Journey Orchestration] O acesso à API é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada na [documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você tem os direitos de <b>Administrador do sistema</b> na organização ou uma [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração no  [!DNL Journey Orchestration]** Service no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para [!DNL Journey Orchestration] e Adobe Experience Platform. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para o Adobe verificar sua identidade e conceder acesso à API. Esta etapa está detalhada nesta [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um** Tokenes de acesso por meio de uma solicitação POST ou por meio da Interface do Console do Desenvolvedor. Esse Token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de Adobe I/O de serviço a serviço seguro, cada solicitação para um serviço do Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Esta é a ID da ORGANIZAÇÃO pessoal, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias :

   * &lt;organization> : sua instância de produção

   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://www.adobe.io/authentication.html">documentação do Adobe I/O</a>).

* **&lt;access_token>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JWT por meio de uma solicitação de POST.

* **&lt;api_key>**: sua Chave de API pessoal. Ele é fornecido no Adobe I/O após criar uma nova integração com o [!DNL Journey Orchestration] Serviço.



## Limitação da descrição da API

A API de limitação ajuda a criar, configurar e monitorar as configurações de limitação.

| Método | Path | Descrição |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obter uma lista das configurações de limite do ponto de extremidade |
| [!DNL POST] | /endpointConfigs | Criar uma configuração de limite de ponto de extremidade |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Implantar uma configuração de limite de ponto de extremidade |
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

Quando um método **canDeploy** é chamado, o processo valida a configuração e retorna o status de validação identificado por sua ID exclusiva:

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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome de serviço inválido  `<!--<given value>-->`: deve ser &#39;dataSource&#39; ou &#39;action&#39;


O possível aviso é:

**ERR_ENDPOINTCONFIG_106**: configuração de limitação: conexões HTTP máximas não definidas: sem limitação por defeito



## Casos de uso

Nesta seção, você encontrará os cinco principais casos de uso que podem ser executados para gerenciar a configuração de limitação em [!DNL Journey Orchestration].

Para ajudá-lo em seus testes e configuração, uma coleção Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta Coleção Postman foi configurada para compartilhar a coleção Variável Postman gerada por __[Integrações do console Adobe I/O](https://console.adobe.io/integrations) > Testar > Baixar para Postman__, que gera um arquivo de Ambiente Postman com os valores de integrações selecionados.

Após o download e o upload para o Postman, é necessário adicionar três variáveis: `{JO_HOST}`,`{Base_Path}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` :  [!DNL Journey Orchestration] URL do gateway
* `{BASE_PATH}` : ponto de entrada para a API. O valor é &#39;/authoring&#39;
* `{SANDBOX_NAME}` : o cabeçalho  **x-sandbox-name**  (por exemplo, &quot;prod&quot;) correspondente ao nome da sandbox onde as operações da API ocorrerão. Consulte a [visão geral das sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) para obter mais informações.

Na seção a seguir, você encontrará a lista ordenada Rest API calls para executar o caso de uso.

Caso de uso n°1: **Criação e implantação de uma nova configuração de limitação**

1. listar
1. criar
1. pode implantar
1. implantar

Caso de uso n°2: **Atualize e implante uma configuração de limitação ainda não implementada**

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

Caso de uso n°5: **Atualizar uma configuração de limitação já implementada**

1. listar
1. get
1. atualizar
1. cancelar implantação
1. pode implantar
1. implantar
