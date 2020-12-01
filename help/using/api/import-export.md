---
product: adobe campaign
solution: Journey Orchestration
title: Importar descrição da API de exportação
description: Saiba mais sobre a API de exportação de importação.
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 3%

---


# Trabalhar com a API Exportar-Importar

Exporte uma versão de jornada e todos os seus objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) com uma única chamada de API. A carga resultante da exportação pode ser usada para importar facilmente a jornada para outro ambiente (instância ou caixa de proteção).
Esse recurso permite que você gerencie suas viagens em várias instâncias ou para vários workflows de ambientes de teste.


## Recursos

A API Journey Orchestration Export-Import está descrita em um arquivo Swagger disponível [aqui](https://adobedocs.github.io/JourneyAPI/docs/).

Para usar essa API com sua instância do Journey Orchestration, é necessário usar o Console de E/S da Adobe. Você pode start seguindo esta [Introdução ao Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) do desenvolvedor do Adobe e, em seguida, usar as seções desta página.

Para testar e preparar sua integração, uma coleção do Postman está disponível [aqui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Fluxo de exportação-importação

Recomendamos seguir estas etapas para exportar e importar suas viagens através dos ambientes:

1. Crie um parâmetro de uma jornada no seu ambiente de start. [Mais informações aqui](https://docs.adobe.com/content/help/pt-BR/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verifique se a versão da jornada não apresenta erro. [Mais informações aqui](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Chame a API **/lista/viagens** para recuperar a jornada UID e o UID da sua versão mais recente. Se necessário, você pode ligar para **/viagens/`{uid}`/latest** para encontrar o UID da sua versão de viagem mais recente.
1. Chame a API **de exportação** com os parâmetros do ambiente do start (orgID e sandboxName).
1. Abra a carga de retorno e verifique os seguintes itens:
   * Se a jornada exportada contiver credenciais **** específicas, será necessário substituir essas credenciais por aquelas correspondentes ao novo ambiente.
   * Se sua jornada exportada contiver **eventos** que apontem para um schema **** XDM, será necessário atualizar manualmente a referência da ID do schema com a ID do schema do novo ambiente no nó xdmEntity se os valores das IDs forem diferentes. Esta atualização precisa ser feita para cada evento. [Mais informações aqui](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Se sua jornada contiver ações de email, sms ou push, talvez seja necessário atualizar o nome do modelo ou o nome do mobileApp se o nome no ambiente do público alvo for diferente daquele do ambiente do start.
1. Chame a API **Import** com os parâmetros do ambiente do público alvo (orgID e sandboxName). Observe que você pode chamar a API de importação quantas vezes desejar. O UUID e o nome de cada objeto contido na jornada são gerados cada vez que você chama a API de importação.
1. Depois que a Jornada for importada, você poderá publicá-la no aplicativo Journey Orchestration. Mais informações [aqui](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticação

### Configuração do acesso à API

O acesso à API do Journey Orchestration é configurado através das etapas abaixo. Cada uma dessas etapas está detalhada na documentação [da](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe I/O.

>[!CAUTION]
>
>Para gerenciar certificados no Adobe I/O, verifique se você tem direitos de administrador <b>do</b> sistema na organização ou uma conta [de](https://helpx.adobe.com/enterprise/using/manage-developers.html) desenvolvedor no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração ao [!DNL Journey Orchestration] Service** no Adobe I/O e configure-a. O acesso ao perfil do produto é necessário para o Journey Orchestration e o Adobe Experience Platform. Suas credenciais serão geradas (chave da API, segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias ao Adobe para verificar sua identidade e conceder acesso à API. Esta etapa está detalhada nesta [seção](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Troque seu JWT por um Token de acesso** por uma solicitação de POST ou pela interface do Developer Console. Esse Token de acesso deverá ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão segura de API de serviço a serviço da Adobe I/O, cada solicitação a um serviço de Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZAÇÃO>**: Esta é a ID pessoal da ORGANIZAÇÃO, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias:

   * &lt;ORGANIZAÇÃO> : sua instância de produção
   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a documentação [do](https://www.adobe.io/authentication.html)Adobe I/O).

* **&lt;ACCESS_TOKEN>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JWT por uma solicitação de POST.

* **&lt;API_KEY>**: sua chave de API pessoal. Ele é fornecido na Adobe I/O após a criação de uma nova integração ao [!DNL Journey Orchestration] Serviço.



## Descrição da API Exportar-Importar

Essa API permite exportar uma versão de jornada identificada por seu UID e todos os objetos relacionados (jornada, eventos, fontes de dados, grupos de campos, ações personalizadas) pelo seu uid.
A carga resultante pode ser usada para importar a versão da jornada em outro ambiente (caixa de proteção ou instância).

| Método | Caminho | Descrição |
|---|---|---|
| `[POST]` | /jornadaVersões/importação | Importar um conteúdo de versão de jornada resultante de uma exportação de versão de jornada |
| `[GET]` | /jornadaVersions/`{uid}`/export | Exportar uma versão de viagem |
| `[GET]` | /viagens/`{uid}`/mais recente | Obtenha a versão mais recente da jornada para uma jornada |
| `[POST]` | /lista/viagens | Lista dos metadados das viagens e das suas versões de viagem |


### Características de exportação e caldeiras

* A viagem deve ser válida antes da exportação.

* As credenciais não são exportadas e um espaço reservado (ou seja, INSERT_SECRET_HERE) é inserido na carga de resposta.
Após a chamada de exportação, você deve inserir manualmente as novas credenciais (correspondentes ao ambiente do público alvo) antes de importar a carga no ambiente do público alvo.

* Os seguintes objetos são exportados, mas nunca serão importados no ambiente do público alvo. Esses são recursos do sistema gerenciados automaticamente pelo Journey Orchestration. Não é necessário substituir &quot;INSERT_SECRET_HERE&quot;.
   * **DataProviders**:  &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos** de campo (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importação

* Durante a importação, os objetos de jornada são criados com um novo UID e um novo nome para garantir a exclusividade no ambiente do público alvo (instância ou caixa de proteção).

* Se a carga de importação contiver espaços reservados secretos, um erro será emitido. Você deve substituir as informações de credenciais antes da chamada de POST para importar a jornada.

## Aviso e erros

Os possíveis erros são:

* No tempo **de** exportação, se a versão de viagem não for válida: erro 500

* No tempo **de** importação, se a carga não for válida após modificações ou se as credenciais não estiverem bem definidas na carga: erro 400

* Após a etapa de importação, se a ID do Schema XDM para seus eventos não for válida no ambiente do público alvo, um erro será exibido no aplicativo Journey Orchestration. Nesse caso, não será possível publicar a viagem.