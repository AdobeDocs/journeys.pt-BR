---
product: adobe campaign
title: Introdução às APIs do jornada
description: Saiba mais sobre APIs do jornada
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 3%

---

# Introdução às APIs do jornada

## Sobre APIs de limitação e limitação

Ao configurar uma fonte de dados ou uma ação, você estabelece uma conexão com um sistema para recuperar informações adicionais para usar em suas jornadas ou enviar mensagens ou chamadas de API.

As APIs do Jornada suportam até 5000 eventos por segundo, mas alguns sistemas externos ou APIs podem não ter uma taxa de transferência equivalente. Para evitar sobrecarga desses sistemas, você pode usar o **Limitação** e **Limitação** APIs para limitar o número de eventos enviados por segundo.

Toda vez que uma chamada de API é executada pelo jornada, ela passa pelo mecanismo de API. Se o limite definido na API for atingido, a chamada será rejeitada se você estiver usando a API de limitação ou colocada em fila e processada assim que possível na ordem em que foram recebidas se estiver usando a API de limitação.

Por exemplo, digamos que você tenha definido uma regra de limitação ou limitação de 100 chamadas por segundo para seu sistema externo. Seu sistema é chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela usará os 100 slots disponíveis e descartará ou colocará em fila os 100 slots restantes. Como a taxa máxima foi excedida, as outras 9 jornadas não terão mais nenhum slot. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falha.

>[!IMPORTANT]
>
>**Regras de limitação** são configuradas no nível da sandbox, para um endpoint específico (o URL chamado), mas globais para todas as jornadas da sandbox.
>
>**Regras de limitação** são configuradas apenas em sandboxes de produção, para um endpoint específico, mas globais para todas as jornadas em todas as sandboxes. Você pode ter apenas uma configuração de limitação por organização.

Para obter mais informações sobre como trabalhar com essas APIs, consulte estas seções:

* [Limitação da API](capping.md)
* [API de limitação](throttling.md)

Ambas as APIs também estão descritas em um arquivo Swagger disponível [here](https://adobedocs.github.io/JourneyAPI/docs/).

## Fontes de dados e capacidade de ações personalizadas {#capacity}

Para **fontes de dados externas**, o número máximo de chamadas por segundo é limitado a 15. Se esse limite for excedido, as chamadas adicionais serão descartadas ou enfileiradas, dependendo da API em uso. É possível aumentar esse limite para fontes de dados externas privadas entrando em contato com o Adobe para incluir o endpoint na  de lista de permissões, mas essa não é uma opção para fontes de dados externas públicas. * [Saiba como configurar fontes de dados](../datasource/about-data-sources.md).

>[!NOTE]
>
>Se uma fonte de dados usar uma autenticação personalizada com um terminal diferente daquele usado para a fonte de dados, será necessário entrar em contato com o Adobe para também incluir esse terminal na  de lista de permissões.

Para **ações personalizadas**, é necessário avaliar a capacidade da API externa do . Por exemplo, se o Journey Optimizer enviar 1000 chamadas por segundo e o sistema suportar apenas 100 chamadas por segundo, é necessário definir uma configuração de limitação ou limitação para que o sistema não fique saturado. [Saiba como configurar ações](../action/action.md)

## Configuração do acesso à API {#api}

Para usar essas APIs com o [!DNL Journey Orchestration] , é necessário usar o Console do AdobeI/O. [!DNL Journey Orchestration] O acesso à API é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada no [Documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você <b>Administrador do sistema</b> direitos sobre a organização ou [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital**, ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração para [!DNL Journey Orchestration] Serviço** no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para [!DNL Journey Orchestration] e Adobe Experience Platform. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Criar um JSON Web Token (JWT)** das credenciais geradas anteriormente e assine-as com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para o Adobe verificar sua identidade e conceder acesso à API. Esta etapa está detalhada neste [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um token de acesso** por meio de uma solicitação do POST ou da interface do Console do desenvolvedor. Esse Token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de Adobe I/O de serviço para serviço seguro, cada solicitação para um serviço da Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Esta é a ID da ORGANIZAÇÃO pessoal, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias. Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte <a href="https://www.adobe.io/authentication.html">Documentação do Adobe I/O</a>).

* **&lt;access_token>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JWT por meio de uma solicitação de POST.

* **&lt;api_key>**: sua Chave de API pessoal. Ele é fornecido no Adobe I/O após criar uma nova integração com o [!DNL Journey Orchestration] Serviço.
