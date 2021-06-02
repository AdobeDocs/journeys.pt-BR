---
product: adobe campaign
title: Uso do editor de expressão avançado
description: Saiba como criar expressões avançadas
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Exemplos de expressão avançada

O editor de expressão Avançado pode ser usado para criar condições para permitir que você filtre usuários em suas jornadas. Essas condições permitem que você direcione aos usuários a hora, data, local, duração ou ações, como compra ou abandono de carrinhos, para que eles possam ser redirecionados na jornada.

>[!NOTE]
>
>Os eventos começam com @, fontes de dados com #.

## Criar condições nos eventos de experiência

O editor de expressão avançado é obrigatório para executar consultas em séries de tempo, como uma lista de compras ou cliques anteriores em mensagens. Essas consultas não podem ser executadas usando o editor simples.

Os eventos de experiência são recuperados do Adobe Experience Platform como uma coleção em ordem cronológica inversa, portanto:

* a primeira função retornará o evento mais recente
* a última função retornará a mais antiga.

Por exemplo, digamos que você queira direcionar os clientes com um abandono de carrinho nos últimos 7 dias para enviar uma mensagem quando o cliente estiver se aproximando de uma loja, com uma oferta sobre itens que ele queria que estivessem na loja.

**Você precisa criar as seguintes condições:**

Primeiro, clientes-alvo que navegaram na loja online, mas não finalizaram o pedido nos últimos 7 dias.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Essa expressão procura todos os eventos para esse usuário especificados nos últimos 7 dias:**

Em seguida, ele seleciona todos os eventos de addtocart que não foram transformados em completePurchase.

>[!NOTE]
>
>Para inserir campos na expressão rapidamente, clique duas vezes no campo no painel à esquerda do editor.

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

Essa expressão retorna um booleano.

**Agora vamos criar uma expressão verificando se o produto está em estoque**

* No Inventário, essa expressão busca o campo de quantidade de um produto e especifica que deve ser maior que 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* À direita, os valores necessários são especificados, aqui, precisamos recuperar o local do armazenamento, que é mapeado do local do evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E especifique o SKU, usando a função `first` para recuperar a interação mais recente &quot;addToCart&quot;:

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

A partir daí, é possível adicionar outro caminho na jornada para quando o produto não estiver na loja e enviar uma notificação com a oferta de envolvimento. Configure as mensagens adequadamente e use dados de personalização para aprimorar o público-alvo da mensagem.

## Exemplos de manipulações de sequência com o editor de expressão avançado

**Em condições**

Essa condição recupera apenas os eventos de geofence acionados em &quot;Arlington&quot;:

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explicação: Esta é uma comparação rigorosa de sequência de caracteres (diferencia maiúsculas de minúsculas), equivalente a uma consulta no modo simples que usa `equal to` com `Is sensitive` marcado.

A mesma consulta com `Is sensitive` desmarcada gerará a seguinte expressão no modo avançado:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**Em ações**

A seguinte expressão permite definir a ID do CRM em um campo de personalização de ação:

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

Explicação: Este exemplo usa as funções `substr` e `lastIndexOf` para remover chaves que incluem a ID do CRM passada com um evento de inicialização de aplicativo móvel.

Para saber mais sobre como usar o editor de expressão avançado, assista a [este vídeo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
