---
product: adobe campaign
title: Importar descrição da API de exportação
description: Saiba mais sobre a API de exportação de importação.
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

Para usar essa API com sua instância do Journey Orchestration, é necessário usar o Console do Adobe I/O. Você pode começar seguindo este [Introdução ao Console do Desenvolvedor do Adobe](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e usar as seções nesta página.

Para testar e preparar sua integração, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Fluxo de exportação-importação

Recomendamos seguir essas etapas para exportar e importar suas jornadas entre ambientes:

1. Crie e defina um parâmetro para uma jornada no seu ambiente inicial. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verifique se a versão do jornada não tem erro. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Chame a API **/list/jornada** para recuperar a jornada UID e o UID da versão mais recente do jornada. Se necessário, você pode chamar **/jornada/`{uid}`/último** para encontrar o UID da versão mais recente do jornada.
1. Chame a API **export** com os parâmetros de ambiente de início (orgID e sandboxName).
1. Abra a carga de retorno e verifique os seguintes itens:
   * Se a jornada exportada contém **credenciais específicas**, é necessário substituir essas credenciais por aquelas correspondentes ao novo ambiente.
   * Se a jornada exportada contém **events** que apontam para um **XDM schema**, é necessário atualizar manualmente a referência da ID do schema com a ID do schema do novo ambiente no nó xdmEntity se os valores de IDs forem diferentes. Essa atualização precisa ser feita para cada evento. [Mais informações aqui](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Se a jornada contiver ações de email, sms ou push, talvez seja necessário atualizar o nome do modelo ou o nome do mobileApp se o nome no ambiente de destino for diferente daquele no ambiente de início.
1. Chame a API **Import** com os parâmetros de ambiente de destino (orgID e sandboxName). Observe que você pode chamar a API de importação quantas vezes desejar. A UUID e o nome de cada objeto contido na jornada são gerados toda vez que você chama a API de importação.
1. Depois que a Jornada for importada, você poderá publicá-la no aplicativo Journey Orchestration. Mais informações [aqui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticação

### Configuração do acesso à API

O acesso à API do Journey Orchestration é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada na [documentação do Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você tem os direitos de <b>Administrador do sistema</b> na organização ou uma [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração no  [!DNL Journey Orchestration]** Service no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para o Journey Orchestration e Adobe Experience Platform. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
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
   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a [documentação do Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JWT por meio de uma solicitação de POST.

* **&lt;api_key>**: sua Chave de API pessoal. Ele é fornecido no Adobe I/O após criar uma nova integração com o [!DNL Journey Orchestration] Serviço.



## Descrição da API Export-Import

Essa API permite exportar uma versão do jornada identificada por sua UID e todos os objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) por sua uid.
A carga útil resultante pode ser usada para importar a versão do jornada em outro ambiente (sandbox ou instância).

| Método | Path | Descrição |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importar um conteúdo de versão do jornada resultante de uma exportação de versão do jornada |
| `[GET]` | /journeyVersions/`{uid}`/exportar | Exportar uma versão do jornada |
| `[GET]` | /jornada/`{uid}`/mais recente | Obtenha a versão mais recente do jornada para uma jornada |
| `[POST]` | /list/jornada | Listar os metadados das jornadas e suas versões de jornada |


### Características de exportação e medidas de proteção

* A jornada deve ser válida antes da exportação.

* As credenciais não são exportadas e um espaço reservado (ou seja, INSERT_SECRET_HERE) é inserido no payload da resposta.
Após a chamada de exportação, você deve inserir manualmente as novas credenciais (correspondentes ao ambiente de destino) antes de importar a carga no ambiente de destino.

* Os seguintes objetos são exportados, mas nunca serão importados no ambiente de destino. Esses são recursos do sistema gerenciados automaticamente pelo Journey Orchestration. Não é necessário substituir &quot;INSERT_SECRET_HERE&quot;.
   * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos de campos**  (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importação

* Durante a importação, os objetos de jornada são criados com um novo UID e um novo nome para garantir a exclusividade no ambiente de destino (instância ou sandbox).

* Se a carga de importação contiver espaços reservados secretos, um erro será lançado. Você deve substituir as informações da credencial antes da chamada do POST para importar a jornada.

## Aviso e erros

Os possíveis erros são:

* Em **tempo de exportação**, se a versão de jornada não for válida : erro 500

* Em **tempo de importação**, se a carga não for válida após modificações ou se as credenciais não estiverem bem definidas na carga : erro 400

* Após a etapa de importação, se a ID do esquema XDM para seus eventos não for válida no ambiente de destino, um erro aparecerá no aplicativo Journey Orchestration. Não será possível publicar a jornada nesse caso.