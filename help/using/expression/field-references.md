---
product: adobe campaign
title: Referências de campo
description: Saiba mais sobre referências de campo em expressões avançadas
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 5%

---

# Referências de campo {#concept_fkj_ll5_dgb}

Uma referência de campo pode ser anexada a um evento ou grupo de campos. As únicas informações significativas são o nome do campo e seu caminho.

Se você estiver usando caracteres especiais em um campo, precisará usar aspas duplas ou aspas simples. Estes são os casos em que as aspas são necessárias:

* o campo começa com caracteres numéricos
* o campo começa com o caractere &quot;-&quot;
* o campo contém qualquer coisa diferente de: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Por exemplo, se o campo for _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Na expressão, os campos de evento são referenciados com &quot;@&quot; e os campos da fonte de dados são referenciados com &quot;#&quot;.

Uma cor de sintaxe é usada para distinguir visualmente os campos de eventos (verde) dos grupos de campos (azul).

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
>O tipo do campo e o valor padrão devem ser iguais. Por exemplo, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} será inválido porque o valor padrão é um número inteiro, enquanto o valor esperado deve ser uma cadeia de caracteres.

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

Os elementos definidos nas coleções são referenciados usando as funções específicas primeiro e último. Para obter mais informações, consulte [esta página](../expression/collection-management-functions.md).

Exemplo :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Referência de um campo definido em um mapa**

Para recuperar um elemento em um mapa, usamos a função de entrada com uma determinada chave. Por exemplo, ele é usado ao definir a chave de um evento, de acordo com o namespace selecionado. Consulte Seleção do namespace. Para obter mais informações, consulte [esta página](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

Nesta expressão, estamos obtendo a entrada da chave &#39;Email&#39; do campo &#39;IdentityMap&#39; de um evento. A entrada &quot;Email&quot; é uma coleção, da qual tiramos o &quot;id&quot; no primeiro elemento usando &quot;first()&quot;. Para obter mais informações, consulte [esta página](../expression/collection-management-functions.md).

**Valores de parâmetros de uma fonte de dados (valores dinâmicos da fonte de dados)**

Se você selecionar um campo de uma fonte externa de dados que requer um parâmetro para ser chamado, uma nova guia será exibida à direita para permitir que você especifique esse parâmetro. Consulte [esta página](../expression/expressionadvanced.md).

Para casos de uso mais complexos, se você quiser incluir os parâmetros da fonte de dados na expressão principal, poderá definir seus valores usando a palavra-chave _params_. Um parâmetro pode ser qualquer expressão válida mesmo de outra fonte de dados que também inclui outro parâmetro.

>[!NOTE]
>
>Quando você define os valores dos parâmetros na expressão, a guia à direita desaparece.

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
