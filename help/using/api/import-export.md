---
product: adobe campaign
title: Importar descrição da API de exportação
description: Learn more about the import export API.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 2%

---


# Trabalhar com a API Export-Import

Exporte uma versão do jornada e todos os seus objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) com uma única chamada de API. A carga útil resultante da exportação pode ser usada para importar facilmente a jornada para outro ambiente (instância ou sandbox).
Esse recurso permite gerenciar suas jornadas em várias instâncias ou para vários fluxos de trabalho de ambientes de teste.


## Recursos

A API Journey Orchestration Export-Import é descrita em um arquivo Swagger disponível [here](https://adobedocs.github.io/JourneyAPI/docs/).

Para usar essa API com sua instância do Journey Orchestration, é necessário usar o Console do Adobe I/O. Você pode começar seguindo este [Introdução ao Console do desenvolvedor do Adobe](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e use as seções nesta página.

Para testar e preparar sua integração, uma coleção Postman está disponível [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Export-Import flow

We recommend to follow these steps to export and import your journeys across environments:

1. Create and parameter a journey in your start environment. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verifique se a versão do jornada não tem erro. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Chame **/list/jornada** API para recuperar a jornada UID e o UID da versão mais recente do jornada. If needed, you can call **/journeys/`{uid}`/latest** to find the UID of your latest journey version.
1. Chame o **exportar** API com os parâmetros do ambiente de início (orgID e sandboxName).
1. Abra a carga de retorno e verifique os seguintes itens:
   * Se a jornada exportada contiver **credenciais específicas**, é necessário substituir essas credenciais por aquelas correspondentes ao novo ambiente.
   * Se a jornada exportada contiver **events** esse ponto **Esquema XDM**, é necessário atualizar manualmente a referência da ID do esquema com a ID do esquema do novo ambiente no nó xdmEntity se os valores de IDs forem diferentes. Essa atualização precisa ser feita para cada evento. [More info here](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * If your journey contains email, sms or push actions, you may have to update the template name or the mobileApp name if the name in the target environment is different from the one in your start environment.
1. Call the **Import** API with your target environment parameters (orgID and sandboxName). Observe que você pode chamar a API de importação quantas vezes desejar. The UUID and the name of each object contained in the journey are generated each time you call the import API.
1. Once the Journey is imported, you can publish it in the Journey Orchestration application. Mais informações [here](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticação

### Configuração do acesso à API

O acesso à API do Journey Orchestration é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada no [Documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você <b>Administrador do sistema</b> direitos sobre a organização ou [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital**, ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração para [!DNL Journey Orchestration] Serviço** no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para o Journey Orchestration e Adobe Experience Platform. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Create a JSON Web Token (JWT)** from the credentials previously generated and sign it with your private key. O JWT codifica todas as informações de identidade e segurança necessárias para o Adobe verificar sua identidade e conceder acesso à API. Esta etapa está detalhada neste [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um token de acesso** por meio de uma solicitação do POST ou da interface do Console do desenvolvedor. Esse Token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de Adobe I/O de serviço para serviço seguro, cada solicitação para um serviço da Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Esta é a ID da ORGANIZAÇÃO pessoal, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias :

   * &lt;organization> : sua instância de produção
   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte [Documentação do Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>**: Your personal access token, that was retrieved when exchanging your JWT through a POST request.

* **&lt;API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.



## Descrição da API Export-Import

This API lets you export a journey version identified by its UID and all the related objects (journey, events, data sources, field groups, custom actions) by its uid.
The resulting payload can be used to import the journey version in another environment (sandbox or instance).

| Método | Path | Descrição |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importar um conteúdo de versão do jornada resultante de uma exportação de versão do jornada |
| `[GET]` | /journeyVersions/`{uid}`/exportar | Export a journey version |
| `[GET]` | /journeys/`{uid}`/latest | Obtenha a versão mais recente do jornada para uma jornada |
| `[POST]` | /list/jornada | List the metadata of the journeys and their journey versions |


### Características de exportação e medidas de proteção

* The journey must be valid before export.

* The credentials are not exported and a placeholder (i.e INSERT_SECRET_HERE) is inserted in the response payload.
Após a chamada de exportação, você deve inserir manualmente as novas credenciais (correspondentes ao ambiente de destino) antes de importar a carga no ambiente de destino.

* Os seguintes objetos são exportados, mas nunca serão importados no ambiente de destino. Esses são recursos do sistema gerenciados automaticamente pelo Journey Orchestration. Não é necessário substituir &quot;INSERT_SECRET_HERE&quot;.
   * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos de campos** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importação

* Durante a importação, os objetos de jornada são criados com um novo UID e um novo nome para garantir a exclusividade no ambiente de destino (instância ou sandbox).

* Se a carga de importação contiver espaços reservados secretos, um erro será lançado. Você deve substituir as informações da credencial antes da chamada do POST para importar a jornada.

## Aviso e erros

The potential errors are:

* At **export time**, if the journey version is not valid : error 500

* Em **tempo de importação**, se a carga não for válida após modificações ou se as credenciais não estiverem bem definidas na carga : erro 400

* After the import step, if the XDM Schema ID for your events is not valid in the target environment, an error appears in the Journey Orchestration application. It will not be possible to publish the journey in such case.