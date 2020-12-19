---
product: adobe campaign
solution: Journey Orchestration
title: Uso do editor de expressão avançado
description: Saiba como criar expressões avançadas
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# Exemplos de expressão avançada

O Editor de expressões Avançadas pode ser usado para criar condições que permitam filtrar usuários em suas viagens. Essas condições permitem que você público alvo os usuários no horário, data, local, duração ou ações como compra ou abandono de carrinhos para que eles possam ser redirecionados na viagem.

>[!NOTE]
>
>Evento start com @, fontes de dados com #.

## Criação de condições para Eventos de experiência

O editor de expressões avançado é obrigatório para executar query em séries de tempo, como uma lista de compras ou cliques passados em mensagens. Tais query não podem ser executados usando o editor simples.

Os eventos de experiência são recuperados do Adobe Experience Platform como uma coleção em ordem cronológica inversa, portanto:

* a primeira função retornará o evento mais recente
* a última função retornará a mais antiga.

Por exemplo, digamos que você queira público alvo dos clientes com um abandono do carrinho nos últimos 7 dias para enviar uma mensagem quando o cliente estiver se aproximando de uma loja, com uma oferta nos itens que ele queria que estivessem armazenados.

**É necessário criar as seguintes condições:**

Primeiro, os clientes do público alvo que navegaram na loja online mas não finalizaram o pedido nos últimos 7 dias.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Esta expressão procura todos os eventos para este usuário especificados nos últimos 7 dias:**

Em seguida, seleciona todos os eventos do addtocart que não se transformaram em um completePurchase.

>[!NOTE]
>
>Para inserir campos na expressão rapidamente, clique com o duplo no campo no painel esquerdo do editor.

O carimbo de data e hora especificado está agindo como o valor de data e hora, o segundo é o número de dias.

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

Esta expressão retorna um booleano.

**Agora vamos construir uma expressão verificando se o produto está em estoque**

* No Inventário, essa expressão procura pelo campo de quantidade de um produto e especifica que ele deve ser maior que 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* À direita, os valores necessários são especificados, aqui, precisamos recuperar o local da loja, que é mapeado do local do evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E especifique SKU, usando a função `first` para recuperar a interação mais recente de &quot;addToCart&quot;:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

A partir daí você pode adicionar outro caminho na sua jornada para quando o produto não estiver na loja e enviar uma notificação com a oferta de envolvimento. Configure as mensagens de acordo e use dados de personalização para aprimorar o público alvo de mensagens.

## Exemplos de manipulações de sequência com o editor de expressão avançado

**Em condições**

Essa condição recupera somente os eventos de geofence acionados em &quot;Arlington&quot;:

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explicação: Esta é uma comparação rigorosa de sequência de caracteres (diferencia maiúsculas de minúsculas), equivalente a um query no modo simples que usa `equal to` com `Is sensitive` marcado.

O mesmo query com `Is sensitive` desmarcado gerará a seguinte expressão no modo avançado:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**Em ações**

A expressão a seguir permite definir a ID do CRM em um campo de personalização da ação:

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

Explicação: Este exemplo usa as funções `substr` e `lastIndexOf` para remover chaves que incluem a ID do CRM transmitida com um evento de inicialização do aplicativo móvel.

Para obter mais informações sobre como usar o editor de expressões avançado, assista [a este vídeo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
