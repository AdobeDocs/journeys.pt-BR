---
product: adobe campaign
title: Introdução às APIs de jornadas
description: Saiba mais sobre APIs de jornadas
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: ht
source-wordcount: '832'
ht-degree: 100%

---

# Introdução às APIs de jornadas

## Sobre APIs de limite e limitação

Ao configurar uma fonte de dados ou uma ação, você estabelece uma conexão com um sistema para recuperar informações adicionais e usar em suas jornadas ou enviar mensagens ou chamadas de API.

As APIs de jornadas comportam até 5000 eventos por segundo, mas alguns sistemas externos ou APIs podem não ter uma taxa de transferência equivalente. Para evitar a sobrecarga desses sistemas, você pode usar as APIs de **Limite** e **Limitação** para limitar o número de eventos enviados por segundo.

Toda vez que uma chamada de API é executada pelas jornadas, ela passa pelo mecanismo da API. Caso o limite definido na API seja atingido, a chamada será rejeitada se estiver usando a API de limite ou enfileirada por até 6 horas e processada o mais rápido possível na ordem em que foi recebida, se estiver usando a API de limitação.

Por exemplo, digamos que você tenha definido uma regra de limite ou limitação de 100 chamadas por segundo para seu sistema externo. Seu sistema é chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela usará os 100 slots disponíveis e descartará ou colocará em fila os 100 slots restantes. Como a taxa máxima foi excedida, não restará nenhum slot para as outras 9 jornadas. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falhas.

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
1. **Crie um JSON Web Token (JWT)** das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para a Adobe verificar sua identidade e conceder acesso à API. Essa etapa está detalhada nesta [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um token de acesso** por meio de uma solicitação POST ou da interface do Console do desenvolvedor. Esse token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de API segura e de serviço a serviço no Adobe I/O, cada solicitação para um serviço da Adobe deve incluir as informações abaixo no cabeçalho de autorização.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: esta é a ID de ORGANIZAÇÃO pessoal. Uma ID de ORGANIZAÇÃO é fornecida pela Adobe para cada uma das instâncias. Para obter o valor da ID de ORGANIZAÇÃO, consulte seu administrador ou contato técnico da Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://www.adobe.io/authentication.html">documentação do Adobe I/O</a>).

* **&lt;ACCESS_TOKEN>**: seu token de acesso pessoal que foi recuperado ao trocar o JWT por meio de uma solicitação POST.

* **&lt;API_KEY>**: sua chave de API pessoal. Ela é fornecida no Adobe I/O após criar uma nova integração com o serviço do [!DNL Journey Orchestration].
