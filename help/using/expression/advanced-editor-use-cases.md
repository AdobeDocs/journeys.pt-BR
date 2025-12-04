---
product: adobe campaign
title: Uso do editor de expressão avançado
description: Saiba como criar expressões avançadas
feature: Journeys
role: Developer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 9%

---

# Exemplos de expressão avançada


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


O editor de expressão avançado pode ser usado para criar condições que permitem filtrar usuários em suas jornadas. Essas condições permitem direcionar os usuários no prazo, data, local, duração ou ações, como compra ou abandono de carrinhos, para que eles possam ser redirecionados na jornada.

>[!NOTE]
>
>Eventos começam com @, fontes de dados com #.

## Criação de condições em Eventos de experiência

O editor de expressão avançado é obrigatório para executar consultas em séries de tempo, como uma lista de compras ou cliques anteriores em mensagens. Essas consultas não podem ser executadas usando o editor simples.

Os eventos de experiência são recuperados da Adobe Experience Platform como uma coleção em ordem cronológica inversa, portanto:

* a primeira função retornará o evento mais recente
* a última função retornará a mais antiga.

Por exemplo, digamos que você queira direcionar os clientes com um abandono de carrinho nos últimos 7 dias para enviar uma mensagem quando o cliente estiver chegando perto de uma loja, com uma oferta nos itens desejados que estão na loja.

**Você precisa criar as seguintes condições:**

Primeiro de tudo, clientes-alvo que navegaram na loja online, mas não finalizaram o pedido nos últimos sete dias.

<!--**This expression looks for a specified value in a string value:**

`In ("addToCart", #{field reference from experience event})`-->

**Esta expressão procura todos os eventos para este usuário especificado nos últimos 7 dias:**

Em seguida, seleciona todos os eventos de adtocart que não se transformaram em uma completePurchase.

>[!NOTE]
>
>Para inserir campos na expressão rapidamente, clique duas vezes no campo no painel esquerdo do editor.

O carimbo de data e hora especificado está agindo como o valor de data e hora, o segundo é o número de dias.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Essa expressão retorna um valor booleano.

**Agora vamos criar uma expressão verificando se o produto está em estoque**

* No Inventário, essa expressão procura o campo de quantidade de um produto e especifica que ele deve ser maior que 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* À direita, os valores necessários são especificados, aqui, precisamos recuperar o local do armazenamento, que é mapeado do local do evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E especifique SKU, usando a função `first` para recuperar a interação &quot;addToCart&quot; mais recente:

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

A partir daí, você pode adicionar outro caminho na jornada para quando o produto não estiver na loja e enviar uma notificação com oferta de engajamento. Configure as mensagens de acordo e use dados de personalização para aprimorar o público-alvo da mensagem.

## Exemplos de manipulações de cadeias de caracteres com o editor de expressão avançado

**Em condições**

Essa condição recupera somente os eventos de geofence acionados em &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explicação: Esta é uma comparação de sequência estrita (diferencia maiúsculas de minúsculas), equivalente a uma consulta no modo simples que usa `equal to` com `Is sensitive` marcado.

A mesma consulta com `Is sensitive` desmarcado gerará a seguinte expressão no modo avançado:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**Em ações**

A seguinte expressão permite definir a ID do CRM em um campo de personalização de ação:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Explicação: Este exemplo usa as funções `substr` e `lastIndexOf` para remover chaves que delimitam a ID do CRM transmitida com um evento de inicialização de aplicativo móvel.

Para obter mais informações sobre como usar o editor de expressão avançado, assista a [este vídeo](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html?lang=pt-BR).
