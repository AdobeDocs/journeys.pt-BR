---
product: adobe campaign
solution: Journey Orchestration
title: Referências de campo
description: Saiba mais sobre referências de campo em expressões avançadas
translation-type: tm+mt
source-git-commit: e2f7c39e61118c42272f730cf5f688ee34d6a9c2
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 5%

---



# Referências de campo {#concept_fkj_ll5_dgb}

Uma referência de campo pode ser anexada a um evento ou grupo de campos. A única informação significativa é o nome do campo e seu caminho.

Se você estiver usando caracteres especiais em um campo, precisará usar aspas de duplo ou aspas simples. Estes são os casos em que as cotações são necessárias:

* os start de campo com caracteres numéricos
* o campo start com o caractere &quot;-&quot;
* o campo contém qualquer outro elemento além de: _a_-_z_, _A_-_Z_, _0_-___99, _ , -_

Por exemplo, se seu campo for _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Na expressão, os campos do evento são referenciados com &quot;@&quot; e os campos da fonte de dados são referenciados com &quot;#&quot;.

Uma cor de sintaxe é usada para diferenciar visualmente os campos de eventos (verde) dos grupos de campos (azul).

**Valores padrão para referências de campo**

Um valor padrão pode ser associado a um nome de campo. A sintaxe é a seguinte:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>O tipo do campo e o valor padrão devem ser os mesmos. Por exemplo, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: {2} será inválido porque o valor padrão é um número inteiro, enquanto o valor esperado deve ser uma string.

Exemplos:

```
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

**Referência de um campo em coleções**

Os elementos definidos nas coleções são referenciados usando as funções específicas, primeiro e último. Para saber mais, consulte [esta página](../expression/collection-management-functions.md).

Exemplo :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Referência de um campo definido em um mapa**

Para recuperar um elemento em um mapa, usamos a função de entrada com uma determinada chave. Por exemplo, ele é usado ao definir a chave de um evento, de acordo com a namespace selecionada. Consulte Seleção da namespace. For more information, see [this page](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

Nesta expressão, estamos recebendo a entrada da chave &quot;Email&quot; do campo &quot;IdentityMap&quot; de um evento. A entrada &quot;Email&quot; é uma coleção, da qual retiramos a &quot;id&quot; no primeiro elemento usando &quot;first()&quot;. For more information, see [this page](../expression/collection-management-functions.md).

**Valores de parâmetro de uma fonte de dados (valores dinâmicos da fonte de dados)**

Se você selecionar um campo de uma fonte externa de dados que requer um parâmetro para ser chamado, uma nova guia será exibida à direita para permitir que você especifique esse parâmetro. Consulte [esta página](../expression/expressionadvanced.md).

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. Um parâmetro pode ser qualquer expressão válida mesmo de outra fonte de dados que também inclui outro parâmetro.

>[!NOTE]
>
>Quando você define os valores de parâmetro na expressão, a guia à direita desaparece.

Use a seguinte sintaxe:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nome exato do primeiro parâmetro da fonte de dados.
* **`<params-1-value>`**: o valor do primeiro parâmetro. Pode ser qualquer expressão válida.

Exemplo:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
