---
product: adobe campaign
title: Referências de campo
description: Saiba mais sobre referências de campo em expressões avançadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: e4a003656058ac7ae6706e22fd5162c9e875629a
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 3%

---

# Referências de campo {#concept_fkj_ll5_dgb}

Uma referência de campo pode ser anexada a um evento ou grupo de campos. As únicas informações significativas são o nome do campo e seu caminho.

Se você estiver usando caracteres especiais em um campo, precisará usar aspas duplas ou aspas simples. Here are the cases when quotes are needed:

* o campo começa com caracteres numéricos
* o campo começa com o caractere &quot;-&quot;
* o campo contém qualquer coisa diferente de: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Por exemplo, se o campo for _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

In the expression, event fields are referenced with &quot;@&quot; and data source fields are referenced with &quot;#&quot;.

Uma cor de sintaxe é usada para distinguir visualmente os campos de eventos (verde) dos grupos de campos (azul).

## Valores padrão para referências de campo

Um valor padrão pode ser associado a um nome de campo. A sintaxe é a seguinte:

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>O tipo do campo e o valor padrão devem ser iguais. For example, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} será inválido porque o valor padrão é um número inteiro, enquanto o valor esperado deve ser uma cadeia de caracteres.

Exemplos:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

## Reference to a field within collections

The elements defined within collections are referenced using the specific functions `all`, `first` and `last`. Para obter mais informações, consulte [esta página](../expression/collection-management-functions.md).

Exemplo :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Referência a um campo definido em um mapa

### Função `entry` 

Para recuperar um elemento em um mapa, usamos a função de entrada com uma determinada chave. Por exemplo, ele é usado ao definir a chave de um evento, de acordo com o namespace selecionado. Consulte Seleção do namespace. Para obter mais informações, consulte [esta página](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

Nesta expressão, estamos obtendo a entrada da chave &#39;Email&#39; do campo &#39;IdentityMap&#39; de um evento. The ‘Email’ entry is a collection, from which we take the ‘id’ in the first element using ‘first()’. For more information, see [this page](../expression/collection-management-functions.md).

### Função `firstEntryKey` 

Para recuperar a primeira chave de entrada de um mapa, use o `firstEntryKey` .

Este exemplo mostra como recuperar o primeiro endereço de email dos assinantes de uma lista específica:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

Neste exemplo, a lista de assinaturas é nomeada `daily-email`. Email addresses are defined as keys in the `subscribers` map, which is linked to the subscription list map.

### Função `keys` 

Para recuperar todas as chaves de um mapa, use o `keys` .

Este exemplo mostra como recuperar, para um perfil específico, todos os endereços de email associados aos assinantes de uma lista específica:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Valores de parâmetros de uma fonte de dados (valores dinâmicos da fonte de dados)

Se você selecionar um campo de uma fonte externa de dados que requer um parâmetro para ser chamado, uma nova guia será exibida à direita para permitir que você especifique esse parâmetro. Consulte [esta página](../expression/expressionadvanced.md).

Para casos de uso mais complexos, se você quiser incluir os parâmetros da fonte de dados na expressão principal, poderá definir seus valores usando a palavra-chave _params_. A parameter can be any valid expression even from another data source that also includes another parameter.

>[!NOTE]
>
>Quando você define os valores dos parâmetros na expressão, a guia à direita desaparece.

Use a seguinte sintaxe:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nome exato do primeiro parâmetro da fonte de dados.
* **`<params-1-value>`**: o valor do primeiro parâmetro. Pode ser qualquer expressão válida.

Exemplo:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
