---
product: adobe campaign
title: Introdução às APIs de jornadas
description: Saiba mais sobre APIs de jornadas
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 89%

---

# Introdução às APIs de jornadas

## Sobre APIs de limite e limitação

Ao configurar uma fonte de dados ou uma ação, você estabelece uma conexão com um sistema para recuperar informações adicionais e usar em suas jornadas ou enviar mensagens ou chamadas de API.

As APIs de jornadas comportam até 5000 eventos por segundo, mas alguns sistemas externos ou APIs podem não ter uma taxa de transferência equivalente. Para evitar a sobrecarga desses sistemas, você pode usar as APIs de **Limite** e **Limitação** para limitar o número de eventos enviados por segundo.

Toda vez que uma chamada de API é executada pelas jornadas, ela passa pelo mecanismo da API. Caso o limite definido na API seja atingido, a chamada será rejeitada se estiver usando a API de limite ou enfileirada por até 6 horas e processada o mais rápido possível na ordem em que foi recebida, se estiver usando a API de limitação.

Por exemplo, digamos que você tenha definido uma regra de limitação ou limitação de 100 chamadas por segundo para o sistema externo. Seu sistema é chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela usará os 100 slots disponíveis e descartará ou colocará em fila os 100 slots restantes. Como a taxa máxima foi excedida, não restará nenhum slot para as outras 9 jornadas. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falhas.

>[!IMPORTANT]
>
>As **regras de limite** são configuradas no nível da sandbox para um ponto de acesso específico (o URL chamado), porém, são globais para todas as jornadas dessa sandbox.
>
>As **regras de limitação** são configuradas apenas em sandboxes de produção para um ponto de acesso específico, porém, são globais para todas as jornadas em todas as sandboxes. Você pode ter apenas uma configuração de limitação por organização.

Para obter mais informações sobre como trabalhar com essas APIs, consulte estas seções:

* [API de limite](capping.md)
* [API de limitação](throttling.md)

Ambas as APIs também estão descritas em um arquivo do Swagger disponível [aqui](https://adobedocs.github.io/JourneyAPI/docs/).

## Capacidade de ações personalizadas e fontes de dados {#capacity}

Para **fontes de dados externas**, o número máximo de chamadas por segundo é limitado a 15. Se esse limite for excedido, as chamadas adicionais serão descartadas ou enfileiradas, dependendo da API utilizada. É possível aumentar esse limite para fontes de dados externas privadas entrando em contato com a Adobe para incluir o ponto de acesso na lista de permissões, mas essa não é uma opção para fontes de dados externas públicas. * [Saiba como configurar fontes de dados](../datasource/about-data-sources.md).

>[!NOTE]
>
>Se uma fonte de dados usar uma autenticação personalizada com um ponto de acesso diferente daquele usado para a fonte de dados, também será necessário entrar em contato com a Adobe para incluir esse ponto de acesso na lista de permissões.

Para **ações personalizadas**, é necessário avaliar a capacidade de sua API externa. Por exemplo, se o Journey Optimizer envia 1000 chamadas por segundo e o sistema permite apenas 100 chamadas por segundo, é necessário definir uma configuração de limite ou limitação para não sobrecarregar o sistema. [Saiba como configurar ações](../action/action.md)

## Configuração do acesso à API {#api}

Para usar essas APIs com a sua instância do [!DNL Journey Orchestration], é necessário usar o console do Adobe I/O. O acesso à API do [!DNL Journey Orchestration] é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada na [documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você possui direitos de <b>administrador do sistema</b> na organização ou uma [conta de desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital** ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração para o serviço** do [!DNL Journey Orchestration] no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para o [!DNL Journey Orchestration] e a Adobe Experience Platform. Suas credenciais serão geradas (chave da API, segredo do cliente etc.).

>[!CAUTION]
>
>O método JWT para gerar tokens de acesso foi descontinuado. Todas as novas integrações devem ser criadas usando o [Método de autenticação de servidor para servidor OAuth](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). A Adobe também recomenda migrar as integrações já existentes para o método OAuth.
>
>Leia as seguintes documentações importantes:
>[Guia de migração para seus aplicativos do JWT para o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Vantagens de usar o método de credenciais OAuth de servidor para servidor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

Para estabelecer uma sessão de API segura e de serviço a serviço no Adobe I/O, cada solicitação para um serviço da Adobe deve incluir as informações abaixo no cabeçalho de autorização.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: esta é a ID de ORGANIZAÇÃO pessoal. Uma ID de ORGANIZAÇÃO é fornecida pela Adobe para cada uma das instâncias. Para obter o valor da ID de ORGANIZAÇÃO, consulte seu administrador ou contato técnico da Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://www.adobe.io/authentication.html">documentação do Adobe I/O</a>).

* **&lt;access_token>**: Seu token de acesso pessoal

* **&lt;API_KEY>**: sua chave de API pessoal. Ela é fornecida no Adobe I/O após criar uma nova integração com o serviço do [!DNL Journey Orchestration].
