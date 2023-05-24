---
product: adobe campaign
title: Funções de gerenciamento de coleções
description: Saiba mais sobre os tipos de dados nas funções de gerenciamento de coleções
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# Funções de gerenciamento de coleções {#collection-management-functions}

A linguagem de expressão também introduz um conjunto de funções para consultar coleções.

Essas funções são explicadas abaixo. Nos exemplos a seguir, vamos usar a carga do evento que contém uma coleção:

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**A função &quot;all(`<condition>`)&quot;**

A variável **[!UICONTROL all]** Esta função permite a definição de um filtro em uma determinada coleção usando uma expressão booleana.

```json
<listExpression>.all(<condition>)
```

Por exemplo, entre todos os usuários do aplicativo, você pode obter os usuários usando o IOS 13 (expressão booleana &quot;app used == IOS 13&quot;). O resultado dessa função é a lista filtrada que contém itens correspondentes à expressão booleana (exemplo: usuário do aplicativo 1, usuário do aplicativo 34, usuário do aplicativo 432).

Em uma atividade de Condição de fonte de dados, você pode verificar se o resultado da **[!UICONTROL all]** é nula ou não. Você também pode combinar isso **[!UICONTROL all]** com outras funções, como **[!UICONTROL count]**. Para obter mais informações, consulte [Atividade de Condição da fonte de dados](../building-journeys/condition-activity.md#data_source_condition).

**Exemplo 1:**

Queremos verificar se um usuário instalou uma versão específica de um aplicativo. Para isso, obtemos todos os tokens de notificação por push associados a aplicativos móveis para os quais a versão é 1.0. Em seguida, executamos uma condição com o **[!UICONTROL count]** para verificar se a lista retornada de tokens contém pelo menos um elemento.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

O resultado é true.

**Exemplo 2:**

Aqui usamos o **[!UICONTROL count]** função para verificar se há tokens de notificação por push na coleção.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

O resultado será true.

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Quando a condição do filtro no campo **all()** estiver vazia, o filtro retornará todos os elementos na lista. **No entanto, para contar o número de elementos de uma coleção, a função all não é necessária.**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

O resultado da expressão é **3**.

**Exemplo 3:**

Aqui verificamos se um indivíduo não recebeu nenhuma comunicação nas últimas 24 horas. Filtramos a coleção de eventos de experiência recuperados da fonte de dados ExperiencePlatform, usando duas expressões com base em dois elementos da coleção. Especificamente, o carimbo de data e hora do evento é comparado ao dateTime retornado pelo **[!UICONTROL nowWithDelta]** função.

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

O resultado será true se não houver evento de experiência correspondente às duas condições.

**Exemplo 4:**

Aqui, queremos verificar se um indivíduo foi iniciado pelo menos uma vez em um aplicativo nos últimos 7 dias, para acionar uma notificação por push convidando-o a iniciar um tutorial.

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** O só está disponível ao manipular coleções de eventos e **currentDataPackField**
>ao manipular coleções de fonte de dados. Ao processar coleções com **[!UICONTROL all]**, **[!UICONTROL first]** e **[!UICONTROL last]**, nós
>executar um loop em cada elemento da coleção, um por um. **[!UICONTROL currentEventField]** e **currentDataPackField**
>corresponde ao elemento que está sendo repetido.

**As funções &quot;first(`<condition>`)&quot; e &quot;last(`<condition>`)&quot;**

A variável **[!UICONTROL first]** e **[!UICONTROL last]** as funções também permitem a definição de um filtro na coleção, enquanto retornam o primeiro/último elemento da lista que atende ao filtro.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Exemplo 1:**

Essa expressão retorna o primeiro token de notificação por push associado aos aplicativos móveis para os quais a versão é 1.0.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

O resultado é &quot;token_1&quot;.

**Exemplo 2:**

Essa expressão retorna o último token de notificação por push associado aos aplicativos móveis para os quais a versão é 1.0.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

O resultado é &quot;token_2&quot;.

>[!NOTE]
>
>Os eventos de experiência são recuperados da Adobe Experience Platform como uma coleção em ordem cronológica inversa, portanto:
>
>* **[!UICONTROL first]** retornará o evento mais recente
>* **[!UICONTROL last]** retornará a mais antiga.


**Exemplo 3:**

Verificamos se o primeiro evento (mais recente) do Adobe Analytics com um valor diferente de zero para a ID de DMA tem um valor igual a 602.

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**A função &quot;at(`<index>`)&quot;**

A variável **[!UICONTROL at]** permite referenciar um elemento específico em uma coleção de acordo com um índice.
O índice 0 é o primeiro índice da coleção.

_`<listExpression>`.at(`<index>`)_

**Exemplo:**

Essa expressão retorna o segundo token de notificação por push da lista.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

O resultado é &quot;token_2&quot;.

**Outros exemplos**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
