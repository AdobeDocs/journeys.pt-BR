---
title: Referências de campo
description: Saiba mais sobre referências de campo em expressões avançadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 61e269bc319407f48006486b96333385ef8b9c58

---



# Referências de campo {#concept_fkj_ll5_dgb}

Uma referência de campo pode ser anexada a um evento ou grupo de campos. A única informação significativa é o nome do campo e seu caminho.

Se você estiver usando caracteres especiais em um campo, precisará usar aspas duplas ou aspas simples. Estes são os casos em que as cotações são necessárias:

* o campo começa com caracteres numéricos
* o campo começa com o caractere &quot;-&quot;
* o campo contém qualquer outro elemento além de: _a_-_z_, _A_-_Z_, _0____-9, _ , -_

Por exemplo, se seu campo for _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

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
>O tipo do campo e o valor padrão devem ser os mesmos. Por exemplo, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: {2} será inválido porque o valor padrão é um número inteiro, enquanto o valor esperado deve ser uma string.

**Referência de um campo em coleções**

Os elementos definidos nas coleções são referenciados usando as funções específicas, primeiro e último. For more information, see [](../expression/collection-management-functions.md).

Exemplo :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Referência de um campo definido em um mapa**

Para recuperar um elemento em um mapa, usamos a função de entrada com uma determinada chave. Por exemplo, ele é usado ao definir a chave de um evento, de acordo com o namespace selecionado. Consulte Seleção do namespace. For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

Nesta expressão, estamos recebendo a entrada da chave &quot;Email&quot; do campo &quot;IdentityMap&quot; de um evento. A entrada &quot;Email&quot; é uma coleção, da qual retiramos a &quot;id&quot; no primeiro elemento usando &quot;first()&quot;. For more information, see [](../expression/collection-management-functions.md).

**Valores de parâmetro de uma fonte de dados (valores dinâmicos da fonte de dados)**

Se você selecionar um campo de uma fonte externa de dados que requer um parâmetro para ser chamado, uma nova guia será exibida à direita para permitir que você especifique esse parâmetro. Consulte [](../expression/expressionadvanced.md).

Para casos de uso mais complexos, se você quiser incluir os parâmetros da fonte de dados na expressão principal, poderá definir seus valores usando os _parâmetros_ de palavra-chave. Um parâmetro pode ser qualquer expressão válida mesmo de outra fonte de dados que também inclui outro parâmetro.

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
