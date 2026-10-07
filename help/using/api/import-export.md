---
product: adobe campaign
title: Importar descrição da API de exportação
description: Saiba mais sobre a API de importação e exportação.
products: journeys
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 19%
---

# Trabalho com a API de importação/exportação

Exporte uma versão do jornada e todos os objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) com uma única chamada de API. A carga útil resultante da exportação pode ser usada para importar facilmente a jornada para outro ambiente (instância ou sandbox).
Esse recurso permite gerenciar as jornadas em várias instâncias ou para vários workflows de ambientes de teste.


## Recursos

A API Export-Import do Journey Orchestration está descrita em um arquivo Swagger disponível [aqui](https://adobedocs.github.io/JourneyAPI/docs/).

Para usar essa API com sua instância do Journey Orchestration, é necessário usar o console do Adobe I/O. Você pode começar seguindo esta [Introdução ao Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e depois usar as seções desta página.

Para testar e preparar sua integração, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Fluxo de importação/exportação

Recomendamos seguir estas etapas para exportar e importar suas jornadas entre ambientes:

1. Crie e atribua parâmetros a uma jornada no ambiente inicial. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verifique se a versão do jornada não tem erros. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Chame a API **/list/jornada** para recuperar a jornada do UID e a UID da versão mais recente do jornada. Se necessário, você pode ligar para **/jornada/`{uid}`/latest** para encontrar a UID da versão mais recente do jornada.
1. Chame a API **export** com seus parâmetros de ambiente inicial (orgID e sandboxName).
1. Abra a carga de retorno e verifique os seguintes itens:
   * Se sua jornada exportada contiver **credenciais específicas**, será necessário substituir essas credenciais pelas credenciais correspondentes ao novo ambiente.
   * Se sua jornada exportada contiver **eventos** que apontem para um **esquema XDM**, você precisará atualizar manualmente a referência da ID do esquema com a ID do novo ambiente no nó xdmEntity se os valores das IDs forem diferentes. Essa atualização precisa ser feita para cada evento. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Se sua jornada contiver email, SMS ou ações de push, talvez seja necessário atualizar o nome do modelo ou o nome do mobileApp se o nome no ambiente de destino for diferente do seu ambiente de início.
1. Chame a API **Import** com seus parâmetros de ambiente de destino (orgID e sandboxName). Observe que você pode chamar a API de importação quantas vezes desejar. A UUID e o nome de cada objeto contido na jornada são gerados sempre que você chama a API de importação.
1. Depois que a Jornada for importada, você poderá publicá-la no aplicativo do Journey Orchestration. Mais informações [aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticação

### Configuração do acesso à API

O acesso à API do Journey Orchestration é configurado de acordo com as etapas abaixo. Cada uma dessas etapas é detalhada na [documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você possui direitos de <b>administrador do sistema</b> na organização ou uma [conta de desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital** ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração para o serviço** do [!DNL Journey Orchestration] no Adobe I/O e configure-a. O acesso ao perfil de produto é necessário para o Journey Orchestration e o Adobe Experience Platform. Suas credenciais serão geradas (chave da API, segredo do cliente etc.).

>[!CAUTION]
>
>O método JWT para gerar tokens de acesso foi descontinuado. Todas as novas integrações devem ser criadas usando o [método de autenticação Servidor para Servidor do OAuth](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). A Adobe também recomenda migrar as integrações já existentes para o método OAuth.
>
>Leia as seguintes documentações importantes:
>[Guia de migração para seus aplicativos do JWT para o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Guia de implementação para aplicativos novos e antigos com OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Vantagens de usar o método de credenciais OAuth de servidor para servidor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)


Para estabelecer uma sessão de API segura e de serviço a serviço no Adobe I/O, cada solicitação para um serviço da Adobe deve incluir as informações abaixo no cabeçalho de autorização.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZAÇÃO>**: esta é a sua ID de ORGANIZAÇÃO pessoal, uma ID de ORGANIZAÇÃO é fornecida pela Adobe para cada uma das suas instâncias:

  * &lt;ORGANIZATION> : sua instância de produção

  Para obter o valor da ID de ORGANIZAÇÃO, consulte seu administrador ou contato técnico da Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a [documentação do Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>**: Seu token de acesso pessoal

* **&lt;API_KEY>**: sua chave de API pessoal. Ela é fornecida no Adobe I/O após criar uma nova integração com o serviço do [!DNL Journey Orchestration].



## Descrição da API Export-Import

Essa API permite exportar uma versão do jornada identificada por sua UID e todos os objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) por sua uid.
A carga resultante pode ser usada para importar a versão do jornada em outro ambiente (sandbox ou instância).

| Método | Caminho | Descrição |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importar um conteúdo de versão do jornada resultante de uma exportação de versão do jornada |
| `[GET]` | /journeyVersions/`{uid}`/export | Exportar uma versão do jornada |
| `[GET]` | /jornada/`{uid}`/latest | Obter a versão mais recente do jornada para uma jornada |
| `[POST]` | /list/jornada | Listar os metadados das jornadas e suas versões do jornada |


### Características de exportação e medidas de proteção

* A jornada deve ser válida antes da exportação.

* As credenciais não são exportadas e um espaço reservado (ou seja, INSERT_SECRET_HERE) é inserido na carga de resposta.
Após a chamada de exportação, você deve inserir manualmente as novas credenciais (correspondentes ao ambiente de destino) antes de importar a carga no ambiente de destino.

* Os seguintes objetos são exportados, mas nunca serão importados no ambiente de destino. Esses são recursos do sistema gerenciados automaticamente pela Journey Orchestration. Não é necessário substituir &quot;INSERT_SECRET_HERE&quot;.
  * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experience Platform&quot; (acppsDataProvider)
  * **Grupos de campos** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Importar características

* Durante a importação, os objetos do jornada são criados com o novo UID e um novo nome para garantir a exclusividade no ambiente de destino (instância ou sandbox).

* Se a carga de importação contiver espaços reservados secretos, ocorrerá um erro. Você deve substituir as informações de credencial antes da chamada POST para importar a jornada.

## Aviso e erros

Os possíveis erros são:

* No **horário de exportação**, se a versão do jornada não for válida: erro 500

* No **horário de importação**, se a carga não for válida após as modificações ou se as credenciais não estiverem bem definidas na carga: erro 400

* Após a etapa de importação, se a ID do esquema XDM dos seus eventos não for válida no ambiente de destino, um erro será exibido no aplicativo do Journey Orchestration. Nesse caso, não será possível publicar a jornada.